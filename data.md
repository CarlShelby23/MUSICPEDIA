# Documentación de la Base de Datos (Esquema, Scripts SQL y Procedures)

La documentación de la base de datos se encuentra en el archivo `Reporte_AppMusicpedia_Amador_Andrade_Flores_May.pdf` y abarca desde el diseño conceptual hasta la implementación de procedimientos que garantizan la integridad y el correcto funcionamiento de la aplicación.

## Modelo y Esquema Relacional

### Modelo Entidad-Relación Extendido
Se presenta un diagrama que describe las entidades principales (**Artista, Álbum, Canción, Artistas Grupales, Integrante_Grupo, Género y Colaboración**) y sus relaciones. Cada entidad está claramente definida, lo que permite comprender cómo se relacionan los datos dentro de **Musicpedia**.

### Esquema Relacional Detallado
La documentación especifica la creación de cada tabla:

- **Tabla Artista:**  
  Con un campo ID autoincrementable y un nombre obligatorio. Se explica cómo se distinguen los artistas individuales de los grupales mediante tablas adicionales.

- **Tabla Álbum:**  
  Incluye atributos como título y fecha de lanzamiento, y mantiene una relación foránea con la tabla **Artista**, con restricciones de eliminación y actualización en cascada.

- **Tabla Canciones:**  
  Detalla campos para título, descripción, duración y asociaciones con artistas y álbumes, garantizando la unicidad de la información mediante índices y restricciones.

- **Tablas de Relaciones y Auxiliares:**  
  Se explican las tablas que gestionan los integrantes de un grupo, los géneros asociados a una canción y las colaboraciones entre artistas, asegurando la integridad referencial en cada caso.

## Descripción de los Scripts SQL

### Creación y Configuración de Tablas
Cada script SQL es acompañado de una explicación sobre:

- La elección de tipos de datos.
- Las restricciones aplicadas (**PRIMARY KEY, UNIQUE, FOREIGN KEY** con **ON DELETE/UPDATE CASCADE**) para preservar la integridad de los datos.
- La creación de índices secundarios para optimizar consultas, por ejemplo, en el nombre de los artistas o en el título de las canciones.

## Procedures y Lógica de Negocio

La documentación detalla numerosos **procedimientos almacenados** que encapsulan la lógica de negocio de la aplicación. Entre ellos destacan:

### Procedimientos para Artistas

- **Agregar Artista Individual:**  
  Utiliza una transacción que inserta el nombre en la tabla **Artista**, recupera el ID generado y posteriormente inserta detalles como nacionalidad y fecha de nacimiento en la tabla específica. Este proceso asegura que ambas operaciones se realicen de forma atómica.

- **Modificar Atributos de Artistas:**  
  Se incluyen procedimientos para actualizar la nacionalidad y la fecha de nacimiento. Cada procedimiento valida previamente la existencia del artista (usando consultas **COUNT**) y, en caso de error, utiliza **SIGNAL** para generar mensajes personalizados.

### Procedimientos para Artistas Grupales

- **Agregar y Modificar Grupo:**  
  Permiten insertar un nuevo grupo (registrando el nombre y la fecha de creación) y actualizar el año de creación, asegurando la coherencia entre la tabla **Artista** y la tabla **Grupo**.

- **Gestión de Integrantes:**  
  Procedimientos que permiten agregar o eliminar integrantes de un grupo, con validaciones que evitan la inserción de integrantes en grupos inexistentes.

### Procedimientos para Álbumes y Canciones

- **Insertar, Eliminar y Modificar Álbumes:**  
  Se describen las operaciones para gestionar álbumes, con especial énfasis en la actualización de títulos y fechas de lanzamiento, y en la eliminación que respeta las relaciones foráneas.

- **Gestión de Canciones y Colaboraciones:**  
  Los procedimientos para canciones incluyen la inserción de canciones individuales y colaborativas, actualización de atributos (**título, descripción, duración y género**) y eliminación.  
  En el caso de las colaboraciones, se maneja la relación entre dos artistas, garantizando que la colaboración se registre correctamente y que los cambios se propaguen de forma consistente.

## Validaciones y Control de Errores

Cada **procedure** incorpora mecanismos de validación que:

- Verifican la existencia de registros antes de realizar actualizaciones o eliminaciones.
- Utilizan transacciones para asegurar que las operaciones complejas se ejecuten de forma completa y sin dejar la base de datos en un estado inconsistente.
- Emplean **SIGNAL** para gestionar errores personalizados, lo que permite notificar de forma clara al usuario o al sistema ante intentos de modificar datos no existentes o duplicados.

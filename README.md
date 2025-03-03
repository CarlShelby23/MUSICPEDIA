# Musicpedia

Musicpedia es un sistema integral diseñado para gestionar información musical de manera eficiente. El proyecto integra dos grandes áreas: un frontend enfocado en la experiencia del usuario y una base de datos robusta que garantiza la integridad y la correcta gestión de la información. La aplicación facilita la administración de artistas, álbumes, canciones y colaboraciones, ofreciendo tanto una interfaz intuitiva como un backend sólido.

## Descripción General

El sistema se estructura en dos componentes principales:

### Frontend

Se encarga de la interacción con el usuario. La interfaz está diseñada para ser intuitiva y funcional, permitiendo una navegación sencilla a través de menús, formularios y tablas que muestran la información en tiempo real.

### Base de Datos

Asegura la persistencia y la integridad de la información musical. Se ha desarrollado un modelo relacional detallado y se han implementado scripts SQL y procedimientos almacenados que gestionan las operaciones de inserción, modificación y eliminación de datos, manteniendo la coherencia de la información.

## Documentación del Frontend

La documentación del frontend explica minuciosamente el diseño y la funcionalidad de la interfaz de la aplicación.

### Estructura y Organización de la Interfaz

#### Menú Principal y Barra Lateral

La aplicación cuenta con un menú principal que incorpora una barra lateral a la izquierda. Esta barra ofrece accesos directos a distintos módulos como la gestión de artistas, álbumes, canciones y colaboraciones, lo que facilita la navegación constante por las funciones del sistema.

#### Distribución de la Pantalla

La interfaz se divide en dos zonas principales:

- **Zona de Opciones (Paneles):** Ubicada a la izquierda, donde se encuentran los formularios y menús contextuales para agregar o modificar información.
- **Zona de Datos (Tablas):** Localizada a la derecha, muestra las tablas conectadas a la base de datos, permitiendo visualizar y consultar de manera inmediata la información registrada.

### Funcionalidades y Pantallas

#### Gestión de Artistas

- **Artistas Individuales:** Permite agregar nuevos artistas ingresando datos como nombre, nacionalidad y fecha de nacimiento. También posibilita eliminar o modificar registros mediante su identificador único.
- **Artistas Grupales:** Además de registrar un grupo, se pueden gestionar sus integrantes, permitiendo la adición, eliminación o modificación de datos de cada miembro.

#### Gestión de Álbumes y Canciones

- **Álbumes:** La aplicación ofrece una pantalla para la creación de álbumes, en la que se deben incluir datos como el título, fecha de lanzamiento y la relación con el artista propietario.
- **Canciones y Colaboraciones:** Se dispone de formularios para agregar canciones, donde se especifican el título, descripción, duración y género. En el caso de colaboraciones, se gestiona la interacción entre dos artistas, registrando detalles como la fecha y la descripción de la colaboración.

### Prototipos y Evaluación de Usabilidad

#### Diseño Visual e Interacción

El diseño se basa en una estética minimalista que utiliza íconos, botones y tablas para lograr una interfaz limpia y fácil de usar.

#### Flujo de Tareas y Pruebas de Usabilidad

Se han definido flujos de interacción que guían al usuario en tareas comunes (por ejemplo, agregar un artista o un álbum). Además, se han aplicado metodologías de evaluación (como el SUS – System Usability Scale) para medir la satisfacción del usuario y detectar áreas de mejora.

## Documentación de la Base de Datos

La documentación de la base de datos describe detalladamente la estructura, las relaciones y los procedimientos que aseguran el correcto funcionamiento del sistema.

### Modelo y Esquema Relacional

#### Diagrama Entidad-Relación Extendido

Se presenta un diagrama que identifica las principales entidades del sistema (**Artista, Álbum, Canción, Artistas Grupales, Integrante_Grupo, Género y Colaboración**) y las relaciones entre ellas, facilitando la comprensión de cómo se integran los datos en Musicpedia.

#### Esquema Relacional Detallado

Se explica la creación de cada tabla:

- **Tabla Artista:** Incluye un campo ID autoincrementable y un nombre obligatorio. Se diferencian los artistas individuales de los grupales mediante tablas específicas.
- **Tabla Álbum:** Contiene atributos como título y fecha de lanzamiento, con una relación foránea que vincula cada álbum a su artista correspondiente. Se aplican restricciones de eliminación y actualización en cascada para mantener la integridad referencial.
- **Tabla Canciones:** Define campos para el título, descripción, duración y las asociaciones necesarias con artistas y álbumes. Se aseguran la unicidad y consistencia de la información a través de índices y restricciones.
- **Tablas Auxiliares:** Administran relaciones como los integrantes de grupos, la asignación de géneros a las canciones y las colaboraciones entre artistas.

### Scripts SQL y Procedimientos Almacenados

#### Creación y Configuración de Tablas

Cada script SQL está acompañado de explicaciones sobre la elección de tipos de datos, la definición de restricciones (como `PRIMARY KEY`, `UNIQUE` y `FOREIGN KEY` con `ON DELETE/UPDATE CASCADE`) e índices secundarios para optimizar las consultas.

#### Procedimientos Almacenados (Procedures)

Se han desarrollado procedimientos que encapsulan la lógica de negocio del sistema:

- **Para Artistas:** Procedimientos que permiten agregar, modificar o eliminar tanto artistas individuales como grupales, asegurando que las operaciones se realicen de forma atómica y validando la existencia de registros.
- **Para Álbumes y Canciones:** Procedimientos que gestionan la inserción, actualización y eliminación de álbumes y canciones, incluyendo validaciones que garantizan la consistencia de los datos.

### Validaciones y Control de Errores

Se implementan mecanismos para verificar la existencia de registros antes de realizar operaciones y se utilizan transacciones para asegurar que las operaciones complejas se ejecuten de forma completa. Además, se emplea la instrucción `SIGNAL` para gestionar errores personalizados y notificar al usuario en caso de inconsistencias.

## Conclusión

Musicpedia combina una experiencia de usuario optimizada con una infraestructura de datos sólida. Mientras el frontend se centra en facilitar una navegación intuitiva y en presentar la información de manera clara, la base de datos se encarga de mantener la integridad y la coherencia de toda la información musical. Esta integración permite desarrollar un sistema eficiente, escalable y seguro para la gestión de contenido musical, adaptándose tanto a las necesidades de los administradores como a las expectativas de los usuarios finales.

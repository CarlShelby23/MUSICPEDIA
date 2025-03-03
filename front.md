# Documentación del Frontend (Pantallas de la Aplicación)

## Estructura y Organización de la Interfaz

### Menú Principal y Barra Lateral
La aplicación cuenta con un menú principal que integra una barra lateral izquierda. En esta barra se ubican las opciones para acceder a distintos módulos: gestión de artistas, álbumes, canciones y colaboraciones. Esta estructura facilita la navegación y permite que el usuario tenga siempre a la vista las acciones disponibles.

### Distribución de Paneles y Tablas
La interfaz divide la pantalla en dos zonas principales:

- **Zona de Opciones (Paneles):** En el lado izquierdo se cargan los formularios y menús contextuales para realizar operaciones (por ejemplo, agregar o modificar información).
- **Zona de Datos (Tablas):** En el lado derecho se muestran las tablas que se conectan a la base de datos, permitiendo visualizar de manera inmediata la información existente.

Esta distribución favorece la interacción simultánea entre la edición de datos y la consulta visual.

## Detalle de las Pantallas y Funcionalidades

### Gestión de Artistas

#### Artistas Individuales
Se presentan pantallas específicas para la gestión de artistas individuales, donde el usuario puede:

- Agregar un artista, ingresando datos como nombre, nacionalidad y fecha de nacimiento.
- Eliminar o modificar la información de un artista utilizando su ID.

#### Artistas Grupales
La interfaz para artistas grupales no solo permite registrar el grupo, sino que además incorpora funcionalidades para:

- Agregar integrantes al grupo.
- Eliminar integrantes o modificar datos del grupo.

### Gestión de Álbumes y Canciones

#### Álbumes
Se incluye una pantalla para agregar nuevos álbumes, donde se deben proporcionar datos como el título, la fecha de lanzamiento y el ID del artista propietario.

#### Canciones y Colaboraciones
La documentación detalla pantallas para:

- Agregar canciones individuales, especificando título, descripción, duración, asociación a álbumes y selección de género.
- Administrar colaboraciones, que implican la interacción entre dos artistas, mostrando formularios para ingresar la descripción, fecha de colaboración y vincular la canción resultante.

## Prototipos y Evaluación de Usabilidad

### Diseño Visual y Elementos Interactivos
Se describen los elementos gráficos como íconos, botones y tablas. El diseño se basa en una estética minimalista que busca la simplicidad y facilidad de uso, siguiendo principios de usabilidad (como los heurísticos de Nielsen) para asegurar que la experiencia del usuario sea intuitiva.

### Flujo de Tareas y Pruebas de Usabilidad
La documentación incluye un protocolo de evaluación en el que se detalla:

- Las tareas a realizar (por ejemplo, agregar un artista o un álbum).
- Los pasos a seguir por los usuarios, junto con la descripción de cada interacción.
- La aplicación de cuestionarios (como el **SUS – System Usability Scale**) para medir la satisfacción y detectar áreas de mejora.

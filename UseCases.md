Tabla de permisos de usuario
----------------------------
| Acción | [Currante](https://www.youtube.com/watch?v=kWrjYdD0Tg0) | Jefe de proyecto | [BOFH](http://www.benavent.org/bofh/) |
| :------------- | :-----------: | :-----------: | :-------: |
| Edición       | Archivos de proyectos en los que participa. | - | Todos los archivos y proyectos |
| Creación      | Nuevos archivos en proyectos en los que participa    | Nuevos proyectos | - |
| Borrado       | Archivos en los proyectos en los que participa | Proyectos propios y todos los archivos de proyectos propios | Todos los proyectos y archivos |
| Consulta de archivos| Archivos y proyectos en los que aparece como colaborador | Todos los proyectos y archivos de proyectos propios | - |
|Consulta de usuarios | Participantes en proyectos en los que participa | Todos los usuarios | - |
| Administración de cuentas | Modificación de cuenta propia | Agregar colaboradores a un proyecto | Modificación de permisos de otras cuentas y creación de nuevas cuentas |
| Sistema       | - | - | Arranque y parada del sistema |

###Permisos de usuario
Los niveles de usuario son cumulativos. 
Un BOFH cuenta con todos los permisos de Jefe de proyecto y un jefe de proyecto con todos los permisos de Currante.

Currante < Jefe de proyecto < BOFH

###Administración de cuentas
El BOFH es el único perfil capaz de crear otras cuentas de usuario, de cualquier nivel deseado. También puede promocionar o degradar otros usuarios.

Los jefes de proyectos pueden dar y retirar permisos de participación en los proyectos que administran.

###Creación y borrado de archivos
Los usuarios son capaces de solicitar al servidor subir un nuevo archivo a un proyecto en el que participen. Inmediatamente se creará en el servidor un *log* en el que figura el creador, la fecha de creación y el título y comentario de la versión inicial.

También pueden solicitar desde el cliente el borrado de un archivo en un proyecto en el que participan. El archivo será eliminado junto con todas las versiones almacenadas y el *log*.

Los administradores no necesitan participar en un proyecto para añadir o borrar archivos del sistema.

###Edición
Solo es posible editar un archivo que ningún otro usuario del sistema esté usando. 
Un usuario editando un archivo puede solicitar las últimas cinco versiones del archivo editado al servidor.
La edición termina cuando el usuario sube una versión al servidor, o descarta los cambios.

Cada nueva versión es acompañada por un título y un comentario. Los títulos y comentarios se almacenan en un *log* que puede ser consultado por cualquier usuario con acceso al archivo desde el cliente.

###Consultas
Desde la aplicación cliente se pueden solicitar al servidor listas de proyectos, de archivos dentro de un proyecto, y de listas de usuario. Se aplican los siguientes filtros y claves de orden.

| Filtro            | Archivo | Proyecto | Usuario |
| :---------------- | :-----: | :------: | :-----: |
| Nombre            | Sí      | Sí       | Sí      |
| Fecha de creación | Sí      | Sí       | Sí      |
| Fecha de última edición |Sí | Sí       | -       |
| Extensión         | Sí      | -        | -       |
| Creador           | Sí      | Sí       | -       |
| Colaboradores     | Sí      | Sí       | -       |
| Nivel de usuario  | -       | -        | Sí      |


###Arranque del sistema
Cuando el programa es iniciado en el lado del servidor, busca una configuración anterior y reanuda el servicio.
En caso de no encontrar una configuración anterior, solicita al usuario que especifique un directorio de trabajo 
y que cree una primera cuenta de administrador.

El sistema podrá detenerse remotamente desde una aplicación cliente con permisos de administrador.

Tabla de permisos de usuario
----------------------------
| Acción | [Currante](https://www.youtube.com/watch?v=kWrjYdD0Tg0) | Jefe de proyecto | [BOFH](http://www.benavent.org/bofh/) |
| :------------- | :-----------: | :-----------: | :-------: |
| Edición       | Archivos de proyectos en los que participa. | - | Todos los archivos y proyectos |
| Creación      | Nuevos archivos en proyectos en los que participa    | Nuevos proyectos | Nuevas cuentas de usuario |
| Borrado       | Archivos en los que figura como creador | Proyectos propios y todos los archivos de proyectos propios | Todos los proyectos y archivos |
| Consulta      | Archivos y proyectos en los que aparece como colaborador | Todos los proyectos y archivos de proyectos propios | - |
| Administración de cuentas | Modificación de cuenta propia | Agregar colaboradores a un proyecto | Modificación de permisos de otras cuentas |
| Sistema       | - | - | Arranque y parada del sistema |

###Permisos de usuario
Los niveles de usuario son cumulativos. 
Un BOFH cuenta con todos los permisos de Jefe de proyecto, y un jefe de proyecto con todos los permisos de Currante.

Currante < Jefe de proyecto < BOFH

###Edición
Solo es posible editar un archivo que ningún otro usuario del sistema esté usando. 
Un usuario editando un archivo puede solicitar las últimas cinco versiones del archivo editado al servidor.
La edición termina cuando el usuario sube una versión al servidor, o descarta los cambios.

###Consultas
Desde la aplicación cliente se pueden solicitar al servidor listas de proyectos y de archivos dentro de un proyecto, filtrados por:
* Autor/Últimos 5 editores/ Propietario / Colaboradores
* Fecha de la última versión
* Nombre del archivo/proyecto

###Arranque del sistema
Cuando el programa es iniciado en el lado del servidor, busca una configuración anterior y reanuda el servicio.
En caso de no encontrar una configuración anterior, solicita al usuario que especifique un directorio de trabajo 
y que cree una primera cuenta de administrador.
El sistema podrá detenerse remotamente desde una aplicación cliente con permisos de administrador.

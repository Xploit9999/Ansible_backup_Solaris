## Descripcion del playbook

* Este playbook tiene como objetivo realizar las copias de seguridad de sistemas operativos Solaris10/11 sobre sistemas de archivos ZFS/UFS.

### Requerimiento antes de usar el playbook

* No hay como tal requerimiento ya que todo se hace con modulos del community general collection. 

### Modo de Uso del Playbook

* Tener creado nuestro inventario con los servidores en el que se va a ejecutar el playbook. Tener en cuenta la version del interprete de python, ya que en los sistemas de operativos Solaris dependiendo de su version viene por defecto python 2.7, version que es aceptable para la ejecutacion de ansible pero que en los Solaris 11.4 viene python3 pero su version 3.4, cosa que no funciona en ansible ya que se solicita que se desde la 3.6+. Por lo que en el mismo inventario se le puede indicar con que interprete se ejecute para evitar estos conflictos con ansible o tambien se le puede indicar como extra vars. En este proyecto deje a modo de ejemplo un archivo llamado inventario.ini como referencia.

* En el directorio **/vars/main.yml** encontrara las variables que son modificables de acuerdo al entorno en el cual se va a ejecutar el playbook.
```
---    
pool: rpool
fs: /backups # <- Puede modificarle el nombre del filesystem en el que se alojara los backups.
nfs: 192.168.124.1:/backups  # <- Puede modificarle el recurso nfs que se usara
snapshot: rpool@archive  
...
```

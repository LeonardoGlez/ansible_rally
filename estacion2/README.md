# Estación 2
## Administración de Servidores

La Organización requiere que la Administración de Servidores ocurra de forma acelerada para poder cumplir con la creciente demanda de servicios y atender los requerimientos de la Línea de Negocios en tiempo y forma.

Por medio de Ansible Tower se deberán automatizar los siguientes requerimientos solicitados por el área aplicativa en los equipos node1, node2 y node3, generando plantillas de trabajo para los siguientes puntos: 


### Playbook para la Gestión de Usuarios
1. Creación de los usuarios ops1, ops2 y ops3 con las siguientes características:

| Usuario |  Grupo adicional | Home Directory | Permisos Home Directory      | Privilegios de sudo sin preguntar contraseña |
| ------- | ----------------- | -------------- | ---------------------------- | ------------------------------------------- |
| ops1    | dbadmin          | /home/dbadmin  | u:rxw                        | No
| ops2    | dbadmin          | /home/dbadmin  | u:rwx                        | No
| ops3    | webadmin         | /home/webadmin | u:rwx                        | Si, para el grupo webadmin



### Playbook para la Gestión de Software para Bases de Datos

2. Se requiere la instalación de Mariadb 10.5 de acuerdo a la [documentación](mariadb_install/README.md) o también puedes reutilizar un rol de ansible para Mariadb como [este](https://galaxy.ansible.com/bertvv/mariadb)


EXTRA BONUS

### Playbook para la Gestión de Software para Desarrollo

3. Se requiere la instalación de GIT y clonar el repositorio https://github.com/brenescoto/webapp.git en la ruta /home/dev-repos/ en los 3 nodos.
4. Se requiere la apertura de puertos 8080/tcp y 9095/tcp en firewalld.



### Tips

Existen varias formas de resolver esta segunda vuelta, aqui te dejamos algunos tips:


1. Usando Loops (Bucles). Ref [Bucles](https://ansible.github.io/workshops/exercises/ansible_rhel/1.5-handlers/README.es.html) sección Bucles Simples.

   Toma en cuenta que los Home Directories no existen, deberás crearlos y asignar permisos. (módulo file)
   
   Para permitir al grupo webadmin el uso de sudo sin contraseña, puedes usar el módulo copy:
   
   ```bash
     - name: Modify sudo config to allow webadmin users sudo without a password
       copy:
         content: "%webadmin ALL=(ALL) NOPASSWD: ALL"
         dest: /etc/sudoers.d/webadmin
         mode: 0440
    ```
  
2. Considera el módulo get_url para descargar https://downloads.mariadb.com/MariaDB/mariadb_repo_setup si sigues la documentación de instalación de MariaDB.
   
   Si te decides por usar el rol de MariaDB puedes hacer fork y ejecutar el Example Playbook bajo la ruta ansible-role-mariadb/molecule/default/converge.yml

EXTRA BONUS

3. Considera instalar git con yum.

   Considera el módulo git de ansible para el clonado del repo.

Arrancamos!!

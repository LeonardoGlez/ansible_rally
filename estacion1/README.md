# Estación 1
## Despliegue y configuración de una aplicación NodeJS

La Organización requiere el despliegue de una aplicación NodeJS en los ambientes DEV y PROD. Por medio de Ansible Tower se deberá automatizar el despliegue considerando los siguientes requerimientos:

1. nodo1 corresponde al ambiente DEV, nodo2 y nodo3 a PROD.

2. El estándar para Web Server permitido por la organización es Apache Web Server.

3. Apache Wer Server debe instalarse y configurarse para que el servicio quede up & running.

4. Instalar y habilitar nodejs.

5. Para asegurar la estandarización de los ambientes, el mismo archivo hello.js debe usarse para ambos ambientes

# Extra Bonus 

Extra 1. El contenido del sitio debe indicar cuál ambiente se esta presentando (DEV o PROD).

Extra 2. Se agregará al stack de software standard para Web Server el uso de Nginx, por lo que la plantilla de trabajo debe permitir elegir una de las dos opciones antes de su ejecución.


## Tips

Existen varias formas de resolver esta primer vuelta, aqui te dejamos algunos tips:


- Recuerda que no es necesario partir de cero, podemos partir de playbooks que ya hacen algo similar. Revisa las [git branches](https://ansible.github.io/workshops/exercises/ansible_rhel/2.6-workflows/README.es.html) del ejercicio, puedes hacer un fork :)

1. Puedes usar variables de Inventario para taggear los nodos (ejemplo variable stage: dev, stage: prod)
Ref. [Aqui](https://ansible.github.io/workshops/exercises/ansible_rhel/2.7-wrap/README.es.html)

3. Tal vez convenga usar roles :) Ref. [Roles](https://ansible.github.io/workshops/exercises/ansible_rhel/1.7-role/README.es.html)

Extra Bonus. 

Extra 1.Usar variables jinja2 dentro del archivo index.html con el módulo template. Ref. [Templates](https://ansible.github.io/workshops/exercises/ansible_rhel/1.6-templates/README.es.html).


Extra 2. Uso de Survey (Encuestas) en Tower. Ref. [Surveys](https://ansible.github.io/workshops/exercises/ansible_rhel/2.4-surveys/README.es.html).
Arrancamos!!

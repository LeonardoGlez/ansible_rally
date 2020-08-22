# Bienvenidos al Rally Virtual de Ansible

En sus marcas, listos, fuera!!

# Instrucciones

Cada equipo contará con un entorno preconfigurado con acceso a los siguientes hosts:

| Role                         | Inventory name |
| -----------------------------| ---------------|
| Ansible Control Host & Tower | ansible        |
| Managed Host 1               | node1          |
| Managed Host 2               | node2          |
| Managed Host 2               | node3          |

Ansible Tower ya está instalado y preconfigurado con el inventario "Workshop Inventory" con los node1,node2,node3 listos para usar.

Accesa al ambiente asignado a tu equipo [Acceso a ambientes](https://tinyurl.com/redhat-rally) 

Los nodos cuentan con direcciones IP públicas, se pueden consultar desde Tower en 
```
INVENTORIES / Workshop Inventory / HOSTS , variable ansible_host
```
O conectándose por SSH al control host en el archivo 
```
cat /home/student<X>/lab_inventory/hosts (modificando <X> por el número de su equipo). 
```

## Estación 1 Despliegue y Soluciones

### Despliegue y configuración de una aplicación NodeJS

La Organización requiere el despliegue de una aplicación NodeJS en los ambientes DEV y PROD. Se deben considerar los siguientes puntos:

1. nodo1 y nodo2 corresponden al ambiente DEV y el nodo3 a PROD.

2. El software estándard para Web Server permitido por la organización es Apache Web Server y Nginx, por lo que la plantilla de trabajo debe permitir elegir una de las dos opciones antes de su ejecución.

3. Al realizar la elección del software, debe realizarse su instalación y configuración para que el servicio quede up & running.

4. Para asegurar la estandarización de los ambientes, el mismo archivo hello.js debe usarse para ambos ambientes

  Extra Bonus. El contenido del sitio debe indicar cuál ambiente se esta presentando (DEV o PROD)


## Tips

Existen varias formas de resolver esta primer vuelta, aqui te dejamos algunos tips:

- Uso de un Workflow para orquestación.
Ref. [Workflows](https://ansible.github.io/workshops/exercises/ansible_rhel/2.6-workflows/)

- Recuerda que no es necesario partir de cero, podemos partir de playbooks que ya hacen algo similar. Revisa las [git branches](https://ansible.github.io/workshops/exercises/ansible_rhel/2.6-workflows/)  puedes hacer un fork :)

1. Puedes usar variables de Inventario para taggear los nodos (ejemplo variable stage: dev, stage: prod)
Ref. [Aqui](https://ansible.github.io/workshops/exercises/ansible_rhel/2.7-wrap/)

2. Uso de Survey en Tower. Ref. [Surveys](https://ansible.github.io/workshops/exercises/ansible_rhel/2.4-surveys/)

3. Tal vez convenga usar roles :) Ref. [Roles](https://ansible.github.io/workshops/exercises/ansible_rhel/1.7-role/)

Extra Bonus. Usar variables jinja2 dentro del archivo index.html con el módulo template. Ref. [Templates](https://ansible.github.io/workshops/exercises/ansible_rhel/1.6-templates/)

# Bienvenidos al Rally Virtual de Ansible
![speed](Icon-Red_Hat-Transportation-Speedometer-A-Red-RGB.png)

En sus marcas, listos, fuera!!

# Instrucciones

Cada equipo debe contar con una cuenta git para almacenar en un repositorio sus playbooks.

Cada equipo tiene con un entorno preconfigurado con acceso a los siguientes hosts:

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
```bash
cat /home/student<X>/lab_inventory/hosts (modificando <X> por el número de su equipo). 
```

Los proyectos usados en Tower harán referencia al git repo del equipo.

Siempre puedes consultar el [Workshop](https://ansible.github.io/workshops/exercises/ansible_rhel/README.es.html) para dudas.

- [Estación 1 Despliegue y Soluciones](estacion1/README.md)
- [Estación 2 Servidores](estacion2/README.md)
- [Estación 3 Seguridad](estacion3/README.md)
- [Estación 4 Redes y Soporte](estacion4/README.md)



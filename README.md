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
```bash
cat /home/student<X>/lab_inventory/hosts (modificando <X> por el número de su equipo). 
```

- [Estación 1 Despliegue y Soluciones](estacion1/README.md)



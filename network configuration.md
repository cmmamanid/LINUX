### Coniguración de red GNS3 VM
#### Problema en gns3:

Configurar manualmente adaptador eth0

![Screenshot_1 jpg](https://user-images.githubusercontent.com/68193499/88803693-7b1a0080-d172-11ea-8075-4ec6d0df607e.png)

eth0 is not configured. Please manually configure by selecting the 'Network' entry in the menu.

Damos click en OK e ingresamos al shell:

![Screenshot_2 jpg](https://user-images.githubusercontent.com/68193499/88804603-caacfc00-d173-11ea-9d5b-765489fb7e43.png)


verificamos la ip actual del adaptador:
```
gns3@gns3vm:~$ ifconfig
```
en caso no visualizemos el adaptador eth0, procedemos a habilitarlo, configurar una dirección IP para la interface eth0 y definimos la ruta por defecto (IP de nuestra puerta de enlace):

```
gns3@gns3vm:~$ sudo ifconfig eth0 up
gns3@gns3vm:~$ sudo ifconfig eth0 192.168.1.5 netmask 255.255.255.0
gns3@gns3vm:~$ sudo route add default gw 192.168.1.1 eth0

```
procedemos a validar la configuración y listo:
```
gns3@gns3vm:~$ ifconfig
gns3@gns3vm:~$ ping 8.8.8.8
```




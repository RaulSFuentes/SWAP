# Práctica 3  

## Nginx 

Instalo una nueva máquina, llamada raullb, la cuál instalo con ssh pero sin apache.   

Seguidamente instalo nginx y cambio su configuración:      


![](https://github.com/RaulSFuentes/SWAP2015/blob/master/practica3/imagenes/1.png) 

Ahora compruebo el balanceado haciendo peticiones a mis dos máquinas:     

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/practica3/imagenes/2.png)

Ahora modificamos otra vez la configuración del nginx:

* Indicamos que la primera máquina es más potente y la cargamos más:


![](https://github.com/RaulSFuentes/SWAP2015/blob/master/practica3/imagenes/3.png)

* Ahora hacemos que todas las peticiones que vengan de la misma IP se dirijan a la misma máquina servidora final:


![](https://github.com/RaulSFuentes/SWAP2015/blob/master/practica3/imagenes/4.png)

* Por último damos persistencia de múltiples peticiones HTTP:

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/practica3/imagenes/5.png)
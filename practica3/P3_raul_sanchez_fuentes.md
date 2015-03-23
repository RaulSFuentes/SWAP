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

Para acabar he vuelto a modificar la configuración del nginx para hacer lo que nos dice el ejemplo de la práctica:

** “”Cada siete peticiones, cinco vayan a la maquina1 y otra a cada unas de las restantes máquinas del grupo (la segunda es el mismo balanceador pero con un servidor web adicional configurado en otro puerto). Además, si ocurre un error, la petición se pasará al siguiente servidor, hasta que se consiga servir o todos den error... También hemos establecido que el segundo servidor espere hasta tres intentos fallidos de conexión antes de dar por considerado ese servidor como no operativo, y esperará 30 segundos entre fallos.””:

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/practica3/imagenes/6.png)

Vemos como balancea:   

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/practica3/imagenes/7.png)   



## Haproxy   

Configuramos haproxy:   


![](https://github.com/RaulSFuentes/SWAP2015/blob/master/practica3/imagenes/8.png) 



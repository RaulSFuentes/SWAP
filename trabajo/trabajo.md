# Trabajo Final

## Instalación de la máquina servidora

Primeramente vamos a proceder a instalar el servidor en azure, para ello muestro unas capturas de pantalla. En ellas se muestran los pasos a seguir para obtener nuestro servidor.   

Para crear una nueva máquina iremos a la parte inferior izquierda y pincharemos sobre nuevo. Seguidamente iremos a proceso -> máquina virtual -> de la galería: 

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/1.png)

Una vez ya estamos en esta pantalla buscaremos el sistema operativo que deseemos. En mi caso utilizaré la versión Ubuntu Server 15.04: 

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/2.png)

El siguiente paso será introducir el nombre de la máquina, el usuario, su contraseña y los procesadores y memoria ram para la máquina: 

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/3.png)

Aquí introduciremos el nombre de DNS para nuestro servicio, yo lo he llamado swapraul. También he habilitado dos puertos, uno que viene por defecto para el ssh y otro ftp que utilizaremos más adelante:

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/4.png)

Y por último confirmamos:

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/5.png)

Vemos como ya tengo creada la máquina: 

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/6.png)

Y ahora muestro los datos de esta:

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/7.png)


Ahora instalaremos Openssl puesto que la versión actual del Portal de administración de Azure solo acepta claves públicas SSH que estén encapsuladas en un certificado X509.  

Introduciremos estos comandos para crear la clave y darle permisos:   

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/8.png)
![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/9.png)


Y ya estaremos dentro de nuestra máquina virtual mediante ssh:

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/10.png)


## Instalación del servidor Ejabberd


Dado que se encuentra en los repositorios oficiales pasaré a instalarlo mediante apt-get install ejabberd: 

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/11.png)


Una vez ya lo tenemos instalado pasaremos a configurarlo. Para ello modificaremos el fichero de configuración que se encuentra en /etc/ejabberd/ejabberd.yml.

Lo primero será indicarle la dirección para el DNS:

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/12.png)

Comprobamos que el puerto por el que escucha el servidor es el 5222: 
 
![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/13.png)

Indicamos quien será el administrador:

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/14.png)

Ahora para crear usuarios introduciremos este comando en un terminal como superusuario "ejabberdctl register <usuario> <servidor> <contraseña>".   

Primeramente creamos el usuario administrador:   

![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/15.png)

Falta la contraseña al final.   

* Para eliminar un usuario bastaría con seguir el siguiente patrón: "sudo ejabberdctl unregister usuario".   

Con esto ya tendríamos creado nuestro servidor ejabberd.   

* Para la administración del servidor tenemos la posibilidad de acceder mediante html gracias a cuando abrimos el puerto 5280. Para ello introduciremos en nuestro navegador: "http://servidor.es:5280/admin".   

Habremos de sustituir servidor.es por nuestro dominio, en mi caso swapraul.cloudapp.net. Y este sería el aspecto de la zona de control de usuarios: 


![](https://github.com/RaulSFuentes/SWAP2015/blob/master/trabajo/imagenes/16.png)








  
 






** Bibliografía

* https://azure.microsoft.com/es-es/documentation/articles/virtual-machines-linux-tutorial/

* https://wiki.debian.org/es/Ejabberd_Configuration

* https://azure.microsoft.com/es-es/documentation/articles/virtual-machines-linux-use-ssh-key/


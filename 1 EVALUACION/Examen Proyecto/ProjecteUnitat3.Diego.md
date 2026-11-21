# PROJECTE UNITAT 3
# INSTAL·LACIÓ I PARAMETRITZACIÓ DE SISTEMES ERP

`DE: DIEGO DE LEON NAVARRO`
---
## INDICE

1. [PREPARACION](#preparacion-del-proyecto)
2. [EJERCIOS](#exercicios-del-proyecto)

---

### PREPARACION DEL PROYECTO

- Accedemos a el **One Drive** y cogemos la **VDI** y la **OVA** de las ubicaciones dichas en la guia del proyecto.

- Creamos las **2** maquinas: 

![](IMGPREPARACION/MaquinasCreadas.png)

- Ahora procedemos a crear las redes privadas de las maquinas:

###### **`WINDOWS 10:`**

`ADAPTADOR 1:`

El primer adaptador lo ponemos en **NAT**:

![alt text](IMGPREPARACION/ADAPTADO1WIN.png)

`ADAPTADOR 2:`

El segundo adaptador lo ponemos en **RED INTERNA** y le ponemos el nombre asignado en la practica:

![alt text](IMGPREPARACION/ADAPTADOR2WIN.png)

###### **`UBUNTU:`**

`ADAPTADOR 1:`

El primer adaptador lo ponemos en **NAT**:

![alt text](IMGPREPARACION/ADAP1UBUNTU.png)

`ADAPTADOR 2:`

El segundo adaptador lo ponemos en **RED INTERNA** y le ponemos el nombre asignado en la practica:

![alt text](IMGPREPARACION/ADAP2UBUNTU.png)

- Y ahora le ponemos las **IP's** correspondientes:

`IP UBUNTU:`

![](IMGPREPARACION/UBUNTUIP.png)

`IP WINDOWS:`

![](IMGPREPARACION/IPWIND.png)

### EXERCICIOS DEL PROYECTO

#### Ejercicio 1: INSTALACION Y CONFIGURACION DE ODOO 16

1. Iniciamos la instalacion en el **Windows** y empezamos la instalacion de **Odoo** y tenemos que marcar **PostreSQL**:

![](IMGEJ1/SelecccionarSERVICIOS.png)

2. Ahora completamos los damos que pide la instalacion de la siguiente manera: 

![](IMGEJ1/ConfPost.png)

3. Ahora assignamos la ruta de la **INSTALACION DE ODOO** a la ruta asignada:

![](IMGEJ1/rutaOdoo.png)  

4. Despues de hacer la instalacion tenemos que ir a comprobar/cambiar la configuracion de este fichero que esta en la siguiente ruta -> `c:\\OdooDiego\server\odoo.conf` y cambiamos lo siguiente:
   
   - Cambiar la clave maestra:
    
    ![](IMGEJ1/claveMaestraCONF.png)

    - Cambiar el puerto http a `EDAD +2 *2 = 4040`:
    
    ![](IMGEJ1/HTTP.png)

5. Comprobamos el Usuario de PostgreSQL

Buscamos **SQL Shell** y vamos a hacer lo siguiente:

- Como hemos hecho la instalacion correctamente y hemos cambiado el puerto en el archivo de configuracion nos sale la informacion guardada menos en la contraseña de esta manera: 
  
![](IMGEJ1/accesoalSQL.png)

> Si sale `postgres-#` significa que has establecido conexion.

- Hacemos el comando de crear un usuario y ponemos la ninformacion puesta en la instalacion y veremos como da error por que ya existe, de esta manera: 
  
![](IMGEJ1/yaExiste.png)

6. Iniciar Odoo y comprobar el puerto 4040

- Hacemos `WIN + R` para acceder a los **servicios.msc** y reiniciamos el `Odoo server` :
  
![](IMGEJ1/Reiniciar.png)

- Ahora accedemos a nuestro navegador y accedemos a la pagina con los puertos **4040**:
  
![](IMGEJ1/funciona1.png)

> Si nos fijamos en la URL vemos como estamos en el puerto **4040**.

- Para acceeder a Odoo desde **UBUNTU** tenemos que abrir una nueva regla a el **firewall** de **Windows** y al finalizar la regla al comprobar que funciona vemos como accedemos: 
![](IMGEJ1/accediendoDesdeUbuntu.png)

#### Ejercicio 2. ACCEDER Y CREAR UNA EMPRESA 

1. Accedemos a nuestro navegador y accedemos a la pagina con los puertos **4040** y ponemos los siguientes datos:
  
![](IMGEJ2/InicioDeSesion1.png)

Al completar esto creamos la Empresa.

2. Ahora comprobamos que la empresa se llama como hemos asignado antes:

![](IMGEJ2/nomEmpresa1.png)

> La ruta para llegar aqui es `Ajuses\Empresas\Compañias`.

3. Iniciamos sesion con el ADMINISTRADOR
   
- Cerramos la sesion y accedemos con el usuario:

![](IMGEJ2/inicioSesion.png)

4. Ahora iniciamos sesion desde el **CLIENTE `UBUNTU`**:

![](IMGEJ2/clienteAccediendo.png)

5. Y desde el cliente comprobamos el nombre de la empresa:

![](IMGEJ2/NOMBDESDEELclIENYE.png)

#### Ejercicio 3. PARAMETRICAACIÓN DE LA EMPRESA EN ODOO

1. Cambiamos el nombre de la compañia: 

- Entramos en Odoo con usu admin -> Ajustes -> Empresas -> Cambiamos el nombre:

![](IMGEJ3/CambioNombreEmpresa1.png) 

2. Cambiamos el nombre y el idioma del usuario admin de esta manera:

![](IMGEJ3/CambioAdminUsu1.png)

3. Instalamos el modulo de empleados :
   
- Nos dirigimos a Apps y buscamos `EMPLEATS` ya que esta en catalan y descargamos este: 

![](IMGEJ3/DescargarEmpleats.png) 

> la primera APP es la que tenemos que instalar.

- Al activar la APP vemos que al acceder a el menu vemos como lo tenemos instalado, de esta manera:

![](IMGEJ3/EmpleatsDescargados.png)

4. Instalamos el modulo de ventas:
   
- Nos dirigimos a Apps y buscamos `VENDES` ya que esta en catalan y descargamos este: 

![](IMGEJ3/DescargarVentas.png)

- Y despues de la instalacion comprobamos que esta instalado: 
  
![](IMGEJ3/comprobamosVendes.png) 

> Nos fijamos como estamos en la seccion de ***Vendes***.

5. Dar permisos de Admin a MARC DEMO:

- Nos vamos a ajustes de usuario y accedemos dentro de MARC DEMO de esta manera:

![](IMGEJ3/DentroDeMarc.png)

- Ahora buscamos `PERMISOS DE ACCESO`:

![](IMGEJ3/PermisosMarc.png) 

> Vemos como en **RECURSOS HUMANOS** tenemos los permisos de ADMIN.

6. Permitir que MARC DEMO solo pueda acceder a sus documentos de ventas:

- Entramos a los permisos de MARC DEMO como anteriormente y buscamos ventas, y le asignamos `USUARIO: SOLO DOCUMENTOS PROPIOS` de esta manera:

![](IMGEJ3/PermisosVentasMARC.png)

- Comprobamos que se han cambiado los permisos, haciendo 2 presupuestos, 1 asignado a marc y otro a otro cliente:

- PRESUPUESTO DE MARC:

![](IMGEJ3/MARCPRESUPUESTO.png)

- PRESUPUESTO DE OTRO CLIENTE:

![](IMGEJ3/FACTURAOTROCLIENTE.png)

- ENTRAMOS CON MARC Y COMPROBAMOS QUE SOLO SALEN DE MARC:

Para esto cerramos sesion con el Admin y iniciamos sesion con: 
**usuario:** demo.
**contraseña:** demo.

![](IMGEJ3/VENDESDEMARC.png)

7. Instalamos el MODULO OCA

- Nos instalamos del **ONE DRIVE** el **OCA** y ahora creamos una carpeta de custom_addons para poder añadir el **OCA**

![](IMGEJ3/creadciondeCustoms.png)

- Ahora tenemos que modificar el archivo de odoo.conf para que lea el path nuevo que hemos creado:

![](IMGEJ3/pathModificado.png)

- Como la version del **OCA** no era la correcta hemos tenido que instalar una de internet que es esta -> [LINK](https://github.com/OCA/account-financial-tools.git)

- Seguido de descargarlo lo descomprimimos y lo movemos dentro del path creado de esta manera: 

![](IMGEJ3/PegadaDeOCA.png)
> EL MANIFEST.PY QUE NECESITAMOS SOLO ESTE EN ESA CARPETA, ASI QUE SOLO COPIAMOS ESA.

- Reiniciamos el Odoo y accedemos a Odoo y actualizamos las aplicaciones y buscamos el modulo que hemos insertado `ACCOUNT - MISSING MENUS` :

![](IMGEJ3/instalamosAccountMissing.png)

- Y comprobamos como ya lo tenemos instalado:

![](IMGEJ3/comproInsaladoAccount.png)

8. Instalamos el MODULO de WHATSAPP

- Ahora si que lo podemos instalar del **ONE DRIVE** ya que es la misma version (16) y cogemos la unica carpeta que tiene y la ponemos en el path que hemos creado para la **OCA**:
  
![](IMGEJ3/WhasCarp.png)

- Debemos reiniciar el servicio Odoo despues de esto y acceder como desarollador otra vez y buscar Whatsapp en APP's: 

![](IMGEJ3/WhasActivar.png)

- Comprobamos que se ha intalado:

![](IMGEJ3/Whatsapp%20activo.png)
> La instalacion de este servicio da errores secundarios ya que necesita dependencias que no estan en el ONEDRIVE.

- Si nos metemos en contactos y buscamos a algun contacto que tenga movil nos sale el icono de Whatsapp, asi queda: 

![](IMGEJ3/WASCONTACTO.png)

#### Ejercicio 4. CREACION DE PAGINA WEB EN ODOO

1. Accedemos a Apps y buscamos WebSite:

![](IMGEJ4/InstalandoWeb.png)

2. Instalamos y comprobamos que esta instalada:
   
- Se nos va a abrir una pagina de configuracion para nuestor sitio web, como esta :

![](IMGEJ4/PaginaConfiguracion.png)

- Y completamos el formulario que nos hace, en este formulario nos pregunta lo siguiente:
  - **Tipo de Web**
  - **Nombre del Sitio**
  - **Idioma**
  - **Objetivo**

- Luego seleccionamos una plantilla (no es necesario, pero ahora tiempo), y la configuramos:
  
![](IMGEJ4/CustoPaginaDe0.png)

- Vamos a configurarla de esta manera para que quede asi (como pide el enunciado):

![](IMGEJ4/PaginaCostumizada.png)

>He accedido desde el UBUNTU para que veamos que se puede acceder y que no hay ningun tipo de problema.

#### Ejercicio 5. PONER UN PRODUCTO EN LA WEB

1. Para esto necesitamos una APP de comercio asi que vamos a instalar Website_sale:

![](IMGEJ5/InstalarServicio.png)

2. Vamos a acceder a la pagina de ventas:

- Para esto tenemos que entrar a nuestro **Sitio Web** y veremos como aparece **Comercio Electronico** al lado de **Site**, ahi sera donde **crearemos/organizaremos** nuestros **productos**:
  
![](IMGEJ5/Site.png)

- Si le damos a las 3 rayas de nuestro Sitio Web vemos como sale Botiga, y si accedemos ahi esta la tienda de productos:

![](IMGEJ5/BotigaSinCrearProducto.png)  

3. Vamos a crear un producto, para eso vamos a acceder a **Comercio Electronico** y a **Productes**, y aqui dentro veremos lo siguiente:
   
![](IMGEJ5/Productos.png)

- Estando aqui vamos a crear un Producto, asi que le damos a crear que aparece arriba a la izquierda y ponemos lo siguiente:

![](IMGEJ5/CreandoElProducto.png)

- Ahora accedemos a la tienda para comprobar que se ha creado correctamente: 
  
![](IMGEJ5/CreadoCorrectamente.png)

#### Ejercicio 6. ACCEDER DESDE EL CLIENTE DE UBUNTU 

> [!NOTE]
> Yo he habilitddo el Firewall de Windows, creando una regla y haciendo el siguiente comando para hacer privada la Red Interna
> ![](IMGEJ6/FIREWALL.png)

1. Buscamos en el navegador de UBUNTU `http://IP_SERVER:4040`

![](IMGEJ6/AccediedoDesdeElCliente.png)

- Ahora que estamos dentro le damos a las 3 rayas y nos vamos a **BOTIGA** y ahi buscamos nuestro producto **DiegoExer5**, y comprobamos que funciona:
  
![](IMGEJ6/ProductoDesdeElCliente.png)

#### Ejercicio 7. ACCEDIENDO CON MARC DEMO DESDE EL CLIENTE

1. Cerramos sesion en el cliente y iniciamos sesion con MARC DEMO:

![](IMGEJ7/IniciarSesionDemo.png)

2. Una vez dentro accedemos a -> Ventas y ahi nos saldras todos los presupuestos que tiene MARC DEMO ya que esos son los permisos que le hemos dado a el usuario:

![](IMGEJ7/VentasMarcDemo.png)
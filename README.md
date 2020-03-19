# AngularWebFrontCRUD

Esta aplicación fue construida para hacer parte de un desarrollo de microservicios, donde se construyó tanto el servicio de CRUD como el FRONT de manera  

# Funcionamiento de la aplicación 

El objetivo de la aplicación demo Web CRUD con MongoDB es generar un sistema de control de transacciones diarias por cliente de los establecimiento de la compañia Efecty, esta aplicación tiene tres pantallas principales de interacción con el usuario.

La primera de ellas como se puede observar en la imagen inferior, consiste en la página de bienvenida al sistema, que le muestra al usuario dos botones, con las dos funcionalidades principales, las cuales son observar las transacciones realizadas y agregar una nueva transacción.

<img width="960" alt="efecty menu" src="https://user-images.githubusercontent.com/45157348/77029483-cec94180-6969-11ea-9efe-f00a2e024919.PNG">

La siguiente parte es al seleccionar la opción de agregar una nueva transacción, donde se puede observar la pantalla con un formulario que obtiene los datos principales de control de una transacción, los cuales son: nombre, apellido, cedula, fecha de la transacción, dirección de residencia, ciudad, valor y tipo de transacción. Aquí lo que se espera es que los cajeros de las sedes de Efecty, registren los datos y mantengan en control las transacciones realizadas por los clientes de la empresa.

<img width="948" alt="efecty 2" src="https://user-images.githubusercontent.com/45157348/77028673-7b55f400-6967-11ea-989e-d9d1a9b40d12.PNG">

Por último, se observa la siguiente opción del menu de bienvenida que es el de observar el historial de transacciones, dentro de esta pantalla se pueden observar las distintas transacciones que se han realizado en el sistema con su información pertinente, además de presentar la funcionalidad de eliminar una transacción por medio del boton borrar, donde elimina completamente todo el registro de la transacción.

<img width="958" alt="efecty lista" src="https://user-images.githubusercontent.com/45157348/77029486-cf61d800-6969-11ea-842b-41a76b10814a.PNG">


# Despliegue en OpenShift desde IBM Cloud shell: 🚀

### Haga 'login' a IBM Cloud desde la línea de comando

_Inicialmente debe acceder al shell de IBM Cloud desde el siguiente link:_
```
https://cloud.ibm.com/shell
```
_1.	Inicie sesión desde la consola de IBM Cloud Shell, para hacerlo utilizamos el siguiente comando:_

```
ibmcloud login --sso
```
_Al digitar el comando anterior nos aparece una pregunta la cual debemos responder con una **Y**_

_En este momneto nos pide un codigo de seguridad, el cual debemos obtener en el siguiente link y pegarlo en la consola de IBM Cloud Shell._
```
https://identity-2.us-south.iam.cloud.ibm.com/identity/passcode
```
_Al digitar el comando anterior nos aparecera una pregunta en la cual debemos indicar el numero perteneciente a la cuenta en la que se va a trabajar._

_2.	Configure el entorno de trabajo. Es necesario asignar (target) la region y el grupo de recursos, en donde esta desplegado el cluster de Open Shift, que vamos a utilizar en el ejercicio.

Para esto debe colocar el siguiente comando en la terminal._
```
ibmcloud target -r us-east -g openshift-workshop
```
_De este modo tenemos el 'login' en IBM Cloud y el ingreso por linea de comando al cluster de Open Shift, para iniciar para el despliegue de la aplicación._


### Acceda el cluster de Open Shift (ROKS) desplegado en IBM Cloud 📦


_3.	Inicie sesión e ingrese desde la CLI de OpenShift al clúster en el que se va a trabajar._

_Para ingresar al clúster que tengamos aprovisionado en nuestra cuenta de IBM Cloud se deben realizar los siguientes pasos:_

_•	Ingresar a la plataforma de IBM cloud con sus credenciales de inicio de sesión, lo puede hacer desde el siguiente link:_

```
https://cloud.ibm.com/
```

_•	Diríjase al resource list._
_Primero debe dar clic en el navigation menu y luego donde dice Resource list, como se puede ver en la siguiente imagen:_

<img width="696" alt="7" src="https://user-images.githubusercontent.com/60987042/76996077-da434b00-691e-11ea-92be-558da48f7d97.PNG">


_•	Diríjase a la sección de clústers y dar clic en el que se desea acceder._

_•	Se da clic en el botón OpenShift web console._

### Haga 'login' en el cluster de Open Shift (ROKS) desde la linea de comando 📦

_•	Ahora en la parte superior derecha se da clic sobre el ID del correo con el que ingresamos y luego en la sección que dice Copy Login Command._

<img width="144" alt="1" src="https://user-images.githubusercontent.com/60987042/76917049-53479180-6890-11ea-91a1-b2c2c9213729.PNG">

_•	Y por último volvemos a la terminal que se estaba utilizando pegamos y damos enter._

### Cree un nuevo proyecto en Open Shift para desplegar las aplicaciones 📦

_4.	Cree un nuevo proyecto en el cluster de la siguiente manera:_
```
oc new-project <projectname>
```
_**Nota:** Para el **projectname** coloque **openshift + las iniciales de su nombre y apellido.**_

_5.	Acceda al proyecto que acabo de crear de la siguiente manera:_

```
oc project <projectname>
```

## Despliegue Aplicación Hello World en Angular 📦

_6.	Clone el repositorio de la aplicación que se desea desplegar._

_**App de hello Word en angular:** https://github.com/emeloibmco/AngularHelloWorld_


_7.	Desde el Shell de IBM cloud digite el comando:_

```
Git clone <url_repositorio>
```
_8.	Dirigirse desde a esta carpeta con el comando:_

_•	Para la carpeta del proyecto Hello word:_
```
cd AngularHelloWorld
```
_9.	Para desplegar la aplicación en OpenShift es necesario escribir el siguiente comando:_
```
npx nodeshift --strictSSL=false --dockerImage=nodeshift/ubi8-s2i-web-app --imageTag=10.x --build.env OUTPUT_DIR=dist/angular-web-app --expose
```
_El resultado de este comando va a ser una respuesta de este tipo, que nos indica que 
la aplicación se desplego correctamente._

<img width="865" alt="2" src="https://user-images.githubusercontent.com/60987042/76918560-9441a500-6894-11ea-954f-62c8076b8903.PNG">

_10.	Para poder acceder al la URL de la aplicación y realizar la verificación de la misma debemos:_

_•Acceder a IBM cloud._

_•Dirigirse al resource list._

_•Dirigirse a la sección de clusters._

_•Ingresar al cluster que lleva por nombre openshift.311._

_•Ingrese a la sección de openshift web console._

_•Buscar el proyecto que creo con sus iniciales y buscar la aplicación que se desplego._

![11](https://user-images.githubusercontent.com/60987042/77017977-f9a39d80-6949-11ea-8b26-4b301e9490f2.png)

_Y por último solo faltaría dar clic en el link que lo llevara a la aplicación desplegada._


![12](https://user-images.githubusercontent.com/60987042/77018166-89494c00-694a-11ea-9f7e-f05d109631d0.png)


_De esta forma se daría por terminado el despliegue de la aplicación angular en openshift._


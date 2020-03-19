# AngularWebFrontCRUD

# GUIA DE INSTALACIÓN Y DESPLIEGUE DE APP ANGULAR EN OPENSHIFT

_Para el desarrollo de este proyecto se tiene como base el desarrollo de una aplicación basada en el lenguaje de programación angular y su posterior despliegue en un **Cluster de OpenShift** que se encuentra alojado en **IBM Cloud**._

## Despliegue en OpenShift desde IBM Cloud shell: 🚀

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

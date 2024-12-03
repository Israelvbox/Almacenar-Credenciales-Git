# Autenticación por HTTPS contra Git en Línea de Comando

## Proposito del documento

Este documento describe los pasos a seguir de como autentificar en git mediante https. 
Git usa dos métodos para ello: ssh y https. El más usual es ssh ya que usa criptografía asimétrica para autenticación (sin contraseña). Sin embargo, si la salida del puerto TCP 22 no está permitida, no se puede usar este método y se tiene que optar por HTTPS, que usa el puerto TCP 443, que está permitido habitualmente. 
Para hacer uso de este segundo método, es necesario proporcionar manualmente el usuario y la contraseña de git (gitlab/github...) cada vez, lo cuál puede ser un problema a la hora de usar de forma contínua git en línea de comandos.
Para solucionar esto, git dispone de "credentials.helper", que permite guardar en caché los datos de autenticación. El tiempo durante el que están vigentes estos datos se puede configurar en git, pero si lo que se quiere es que nunca más pida usuario y contraseña manualmente, se puede usar el argumento "store", quedando el comando a ejecutar así:
git config credentials.helper store
lo que creará un archivo llamado .git-credentials o bien .git-credentials-NOMBRE_REPOSITORIO. 
Este archivo está en texto plano, así que cualquiera que tenga acceso a dicho directorio podrá verlo. Hay que tenerlo en cuenta a la hora de usar este método.

## Instrucciones tecnicas

Clonar el Repositorio
	Descripción breve del proceso de clonado del repositorio utilizando la URL HTTPS proporcionada.
	Información sobre la introducción de credenciales.
  Acceder al Repositorio
	Detalles sobre cómo acceder a la carpeta del repositorio clonado.
	Instrucciones para navegar a la ruta del repositorio.
Configurar Git para Almacenar Credenciales
	Explicación de cómo configurar Git para almacenar credenciales dentro del repositorio.
	Introducción del comando específico utilizado para esta configuración.
	Detalle sobre las opciones y parámetros del comando.
Realizar un Push para Crear el Archivo de Credenciales
	Proceso para realizar un push o una operación similar que requiera autenticación.
	Creación del archivo de credenciales al introducir las credenciales solicitadas.
	Confirmación de que no será necesario introducir las credenciales nuevamente para este repositorio.

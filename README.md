# Autenticación por HTTPS contra Git en Línea de Comando

## Proposito del documento

Este documento describe los pasos a seguir de como autentificar en git mediante https. 
Git usa dos métodos para ello: ssh y https. El más usual es ssh ya que usa criptografía asimétrica para autenticación (sin contraseña). Sin embargo, si la salida del puerto TCP 22 no está permitida, no se puede usar este método y se tiene que optar por HTTPS, que usa el puerto TCP 443, que está permitido habitualmente. 
Para hacer uso de este segundo método, es necesario proporcionar manualmente el usuario y la contraseña de git (gitlab/github...) cada vez, lo cuál puede ser un problema a la hora de usar de forma contínua git en línea de comandos.
Para solucionar esto, git dispone de "credentials.helper", que permite guardar en caché los datos de autenticación. El tiempo durante el que están vigentes estos datos se puede configurar en git, pero si lo que se quiere es que nunca más pida usuario y contraseña manualmente, se puede usar el argumento "store", quedando el comando a ejecutar así:
git config credentials.helper store
lo que creará un archivo llamado .git-credentials o bien .git-credentials-NOMBRE_REPOSITORIO. 
Este archivo está en texto plano, así que cualquiera que tenga acceso a dicho directorio podrá verlo. Hay que tenerlo en cuenta a la hora de usar este método.

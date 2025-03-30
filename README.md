# Docker
Instalación de docker Ubuntu/Windows 
Para instalar Docker en Ubuntu 24.04.2, puedes seguir los siguientes pasos. Este proceso utiliza el repositorio oficial de Docker para garantizar que obtienes la versión más reciente y estable.

## Pasos para instalar Docker en Ubuntu 24.04.2:
1. Actualiza los paquetes de tu sistema:
Abre una terminal y ejecuta el siguiente comando para asegurarte de que tu sistema esté actualizado:

	    sudo apt update
   		sudo apt upgrade -y

2. Instala los paquetes necesarios para permitir la instalación desde un repositorio HTTPS:

	 	sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

3. Añadir la clave GPG de Docker:
   
   Docker utiliza una clave GPG para verificar la autenticidad del repositorio. Ejecute este comando para añadirla:

   		curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
4. Agregar el repositorio de Docker:
   
	Ahora debes añadir el repositorio oficial de Docker a las fuentes de apt para que puedas instalarlo:

		echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

5. Actualiza nuevamente los paquetes disponibles:

   		sudo apt update

6. Instalar Docker:
   
	Ahora puedes instalar Docker con el siguiente comando:

		sudo apt install docker-ce docker-ce-cli containerd.io -y
	Este comando instala el Docker Engine, el CLI de Docker y el containerd, que es el runtime utilizado por Docker.

7. Verificar la instalación:
	Una vez instalado Docker, puedes verificar que se haya instalado correctamente ejecutando:

		sudo docker --version

	Deberías ver algo como:

		Docker version 24.0.x, build xxxxx

8. (Opcional) Ejecutar Docker sin sudo:
   
	Por defecto, Docker requiere permisos de superusuario para ejecutarse. Si deseas ejecutarlo como un usuario normal (sin usar sudo), agrega tu usuario al grupo docker:

		sudo usermod -aG docker $USER

 9. Para que los cambios tomen efecto, es recomendable cerrar sesión y volver a iniciarla o ejecutar el siguiente comando:
		
		newgrp docker

10. Verificar el estado de Docker:
    
	Para comprobar que Docker se está ejecutando correctamente, puedes ejecutar el siguiente comando para verificar el estado del servicio:

		sudo systemctl status docker
	Si Docker está funcionando correctamente, deberías ver algo como:

		Active: active (running) since ...

11. Ejecutar un contenedor de prueba:
		Para asegurarte de que todo funciona correctamente, puedes ejecutar el siguiente comando que descargará y ejecutará el contenedor hello-world, que es un contenedor de prueba oficial 		de Docker:

		sudo docker run hello-world
		
	Si todo está bien, deberías ver un mensaje diciendo que Docker está instalado correctamente.

### ¡Listo! Docker debería estar instalado y funcionando en tu Ubuntu 24.04.2.




















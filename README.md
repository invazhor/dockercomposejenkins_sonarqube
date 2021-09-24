# Docker Compose para Jenkins y Sonarcube
Docker-compose creado con motivos educacionales en el contexto del Curso DevSecOps 2021 USACH.

## Requisitos
#### Debe tener instalado docker-compose



## Iniciar
#### Crear la nueva red comun para los dos servicios
```bash
docker network create jenkinsnet
```
#### Descargar los archivos
```bash
git clone https://github.com/invazhor/dockercomposejenkins_sonarqube.git
```
#### Para iniciar el contenedor Jenkins ingresar al directorio 
```bash
cd dockercomposejenkins_sonarqube/Jenkins
docker-compose up
```

#### Para iniciar el contenedor Sonarqube ingresar al directorio 
```bash
cd dockercomposejenkins_sonarqube/Sonarqube
docker-compose up -d
```
## Comandos utiles
Para inspeccionar la configuración de red creada y validar que los contenedores esten atachados a esta red
```bash
docker network inspect jenkinsnet
```
Para ingresar al contenedor de Jenkins e instalar app necesarias para testing de red y comunicaciones.
```bash
docker exec -it jenkins /bin/bash
```
Instalar aplicación Ping para pruebas de comunicación ICMP
```bash
apt-get update
apt-get install iputils-ping
```
Instalar utilidades de red para configuraciones
```bash
apt-get install net-tools
```
Detener contenedores (sin eliminar)
```bash
docker-compose stop
```
Pruebas de comunicación entre contenedores
```bash
docker exec -it <Docker-ID-Origen> ping <Docker-ID-Destino>
```

## Contribuciones
Puede realizar mejoras al docker compose básico.


## License
[MIT](https://choosealicense.com/licenses/mit/)

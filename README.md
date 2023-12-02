# Dockerización de Aplicación NestJS y GitHub Actions

## Descripción
Este repositorio demuestra cómo Dockerizar una aplicación NestJS y configurar un flujo de trabajo en GitHub Actions para construir y desplegar contenedores de Docker.

## Pasos por seguir

### 1. Crear Repositorio

Crea un repositorio público o privado en GitHub. [Enlace al Repositorio](https://github.com/Byotony/docker-9no)
![Alt text](img/Screenshot_1.png)

### 2. Preparar el Código Fuente

Luego solo realizamos el commit del código a utilizar
![Alt text](img/Screenshot_3.png)

### 4. Configurar Secrets en GitHub

Crea los secrets DOCKER_USER y DOCKER_PASSWORD en la sección de Secrets de tu repositorio en GitHub.
![Alt text](img/Screenshot_4.png)
![Alt text](img/Screenshot_5.png)
![Alt text](img/Screenshot_6.png)


### 5. Configurar Token de Docker Hub

Utiliza tu usuario y clave (token) de Docker Hub para llenar los secrets DOCKER_USER y DOCKER_PASSWORD.
Crea un Token en Docker (con el nombre Github-Actions) y copia este Token generado en el secret DOCKER_PASSWORD.
![Alt text](img/Screenshot_7.png)
![Alt text](img/Screenshot_8.png)
![Alt text](img/Screenshot_9.png)


#### 6. Dockerizar la Aplicación

Dockeriza tu aplicación NestJS (preferiblemente un servicio REST o GraphQL sin dependencias).
![Alt text](img/Screenshot_10.png)
![Alt text](img/Screenshot_11.png)

#### 7. Verificar Construcción y Funcionamiento

Asegúrate de que la imagen puede ser compilada con el siguiente comando:
bash
docker login
docker build -t byotony/webhooks:latest .
Verifica el funcionamiento de la aplicación.
![Alt text](img/Screenshot_13.png)
![Alt text](img/Screenshot_14.png)

Tambien hacemos el push

![Alt text](img/Screenshot_15.png)

Y ya para terminar hacemos el commit para que se hagan los builds automáticamente cuando realizemos un commit nuevo al repositorio.

![Alt text](img/Screenshot_16.png)

### 8. Crear Action Docker Image
Configura un flujo de trabajo en GitHub Actions para generar la imagen Docker utilizando el archivo docker-image.yml.

![Alt text](img/Screenshot_17.png)


# Evidencias

Ya tenemos el actions creado para realizar builds automáticos.
![Alt text](img/Screenshot_18.png)

Ahora lo progamos realizando un commit nuevo a nuestro repositorio
![Alt text](img/Screenshot_19.png)

Y cuando lo guardamos, se estará gerenando un build nuevo automáticamente.
![Alt text](img/Screenshot_20.png)

Proceso de build.
![Alt text](img/Screenshot_21.png)

Build terminado, proceso sin errores. 
![Alt text](img/Screenshot_22.png)



# Montar y usar sonarqube para analizar un proyecto
## Usamos docker para hacer pull de la imagen de sonarqube
```bash
docker pull sonarqube
```
## Creamos el contenedor y usamos la imagen que acabamos de bajar
```bash
docker run -d --name sonarqube -p 9000:9000 sonarqube
```
## Accedemos a la interfaz de sonaqube a través de localhost:9000
El usuario y la contraseña por defecto es admin admin

<img width="550" alt="Screenshot 2024-05-14 at 8 39 36 PM" src="https://github.com/juanosorio0219/sonarqube-jab/assets/80568091/64d30bd3-6837-4ba9-ac02-1d3e868d2736">

Creamos un proyecto local

<img width="497" alt="Screenshot 2024-05-14 at 8 42 23 PM" src="https://github.com/juanosorio0219/sonarqube-jab/assets/80568091/2001b804-d763-4ccf-bef9-41a77d8ba37f">

<img width="700" alt="Screenshot 2024-05-14 at 8 42 42 PM" src="https://github.com/juanosorio0219/sonarqube-jab/assets/80568091/befbc380-8455-4150-8bdf-7bedfe611a91">
<img width="436" alt="Screenshot 2024-05-14 at 8 43 00 PM" src="https://github.com/juanosorio0219/sonarqube-jab/assets/80568091/e4f20fc0-c015-4210-8982-d4f142adf0cb">
<img width="712" alt="Screenshot 2024-05-14 at 8 43 16 PM" src="https://github.com/juanosorio0219/sonarqube-jab/assets/80568091/d7ce0ff8-5108-43f9-8b0d-6903e9f63084">
<img width="1302" alt="Screenshot 2024-05-14 at 8 43 51 PM" src="https://github.com/juanosorio0219/sonarqube-jab/assets/80568091/013fda81-46f5-40ab-9725-6e61d6e35297">

## Hacemos la revisión de nuestro proyecto
En este caso usé un proyecto de Spring Boot, creado con maven
```bash
mvn clean verify sonar:sonar \
  -Dsonar.projectKey=philanthropy-back \
  -Dsonar.projectName='philanthropy-back' \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_1653f3b5cb1f4e04642480bddb32adcfbf456465
```

<img width="1232" alt="Screenshot 2024-05-14 at 8 48 48 PM" src="https://github.com/juanosorio0219/sonarqube-jab/assets/80568091/cc9f2f8f-0103-4493-a25f-93b7515f38ee">
<img width="1335" alt="Screenshot 2024-05-14 at 8 49 40 PM" src="https://github.com/juanosorio0219/sonarqube-jab/assets/80568091/cc057ce9-fdd5-4049-a8b7-834bce86b7bf">




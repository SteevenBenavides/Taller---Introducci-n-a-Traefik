# Taller---Introducci-n-a-Traefik

Pantallazos Solicitados:

Paso 1. Verificar requisitos: Ejecutar en la terminal docker --version y docker compose version. 
Pantallazo: salida de la terminal con las versiones de Docker y Docker Compose.

<img width="398" height="111" alt="Pantallazo1" src="https://github.com/user-attachments/assets/6b728806-34df-4244-a88a-0a54afec6219" />

Paso 2. Levantar Traefik: Crear la configuración mínima y ejecutar docker compose up -d para iniciar Traefik.
Pantallazo: salida de docker compose ps mostrando que Traefik está corriendo.
<img width="1288" height="338" alt="Pantallazo2" src="https://github.com/user-attachments/assets/db87c8af-9e11-4e9a-88fc-22b6a7f1cadf" />

Paso 3. Acceder al dashboard de Traefik: Abrir en el navegador la URL http://localhost:8080/dashboard/.
Pantallazo: captura del dashboard de Traefik abierto en el navegador.
<img width="1284" height="635" alt="Pantallazo3" src="https://github.com/user-attachments/assets/89dac8c0-433a-47ec-b653-4f65e7659eee" />

Paso 4. Desplegar la aplicación de ejemplo: Levantar el servicio de prueba (whoami) para que Traefik lo detecte.
Pantallazo: terminal mostrando que el servicio de prueba se levantó correctamente.
<img width="1292" height="260" alt="Pantallazo4" src="https://github.com/user-attachments/assets/c9a310ab-b52c-4c32-95c7-0c414b2c9339" />

Paso 5. Probar acceso a la aplicación: Acceder en el navegador a http://whoami.localhost o ejecutar curl http://whoami.localhost.
Pantallazo: evidencia de la respuesta de la aplicación (hostname o IP del contenedor).
<img width="391" height="398" alt="Pantallazo5" src="https://github.com/user-attachments/assets/f6eaf9c4-ccc1-4e7c-8976-672a7845401b" />

Paso 6. Revisar routers en el dashboard: Ir al dashboard de Traefik a la sección HTTP Routers y confirmar que aparece whoami.localhost.
Pantallazo: captura del dashboard mostrando el router creado para la aplicación.
<img width="1293" height="642" alt="Pantallazo6" src="https://github.com/user-attachments/assets/7b3efc35-7004-4aff-9a6e-56cfc6a30fa0" />


Preguntas:

¿Qué ventaja aporta enrutar por host (dominio) vs por puerto?: Enrutar por host es mejor porque todas las apps pueden ir por el mismo puerto
y se diferencian con el dominio. En cambio, por puerto toca darle un número distinto a cada app y eso se vuelve enredado.

¿Qué diferencia hay entre labels en los servicios y usar archivos de configuración?: Los labels se usan dentro del servicio para que ya traiga
su propia regla y Traefik lo detecte fácil. Los archivos de configuración sirven más cuando las reglas son grandes o se quieren manejar todas en un solo lugar.

¿Cómo se entera Traefik de que había servicios nuevos?: Traefik se da cuenta de los nuevos servicios porque está conectado al Docker y escucha cuando se levantan contenedores.
Así actualiza solo su configuración sin que uno tenga que hacer nada.

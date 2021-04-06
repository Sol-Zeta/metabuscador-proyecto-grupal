
## Requisitos del proyecto
<br>

Se pide desarrollar una aplicación web de búsqueda y gestión de `ofertas laborales en Madrid / ofertas de empleo freelance / cursos sobre desarrollo web` .
Dicha app deberá contemplar las siguientes vistas y funcionalidades:
<br>
<br>

### Menú
<br>
Estará presente en todas las vistas de la app.

Tendrá los siguientes enlaces:

- Inicio : `/`
- Registrarse : `/registro`
- Ingresar : `/ingresar`
- Salir : `/salir` (redirige a `/`)
- Favoritos : `/favoritos`

<br>
<br>

### Vista inicial (home)
<br>

`/` : Vista de inicio de la app. Tendrá como mínimo un input de texto y un botón para efectuar la búsqueda. Una vez realizada la misma, se mostrará debajo una lista de "tarjetas" que contengan los datos más relevantes de cada resultado y un botón para guardar cada una de ellas en `favoritos`.  
Cada vez que se realice una nueva búsqueda, los resultados anteriores dejarán de mostrarse. 


#### Sobre guardar en favoritos:
El botón para guardar en favoritos se muestra solo en el caso de que el usuario esté logueado. Si no lo está, el botón no se muestra. 
<br>
<br>

### Vista registro
<br>

<strong>`/registro`</strong> : Registro de usuario nuevo. Tendrá como mínimo un formulario de email y contraseña como credenciales de entrada a la app. Además, deberá ofrecer la alternativa de identificación mediante Google, Facebook u otro proveedor de autenticación a elección.
<br>
<br>

### Vista ingresar
<br>

<strong>`/ingresar`</strong> : Validación de credenciales, abrir sesión y redirección **home**.
(!!!! acá podríamos agregar la opción de recuperar contraseña ;-) con Nodemailer + JWT si les parece importante)
<br>
<br>

### Vista favoritos
<br>

<strong>`/favoritos`</strong> : Mostrará los resultados seleccionados por el usuario como favoritos, del mismo modo en que se muestran los resultados de búsqueda. Cada "tarjeta" tendrá un botón para borrar la selección de favoritos. Esta vista será privada y solo se podrá acceder si el usuario está logueado. 

<br>
<br>

### Notas adicionales
<br>

Sobre el control de acceso
La aplicación debe estar protegida a entradas indebidas de usuarios no registrados (o autorizados por un proveedor externo), de manera que el endpoint asociado a la zona privada (`/favoritos`) comprobará si la sesión está abierta, y en caso contrario redireccionará al área `login` de la app.
<br>
<br>

Para el `login` con credenciales email y contraseña, deberá hacerse mediante JWT. Para la parte de login con uno o más proveedores de terceros deberá hacerse mediante `OAuth` (con o sin Firebase, a elegir; en cualquier caso, con un proveedor OAuth será suficiente).

<br>
<br>

### Sobre el modelo de datos
<br>

El almacenamiento y la búsqueda de los datos, se realizará de la siguiente manera:

Toda la información relativa a los `usuarios` de la plataforma (credenciales y otras cuestiones de acceso, así como la asociación de favoritos a usuarios) se almacenará en una base de datos relacional SQL.

Los datos de las búsquedas provendrán del scrapping de al menos dos webs distintas que deberán seleccionarse previo análisis.

El modelo de datos dependerá de la información que pueda recogerse de las plataformas elegidas. 

<br>
<br>

### Sobre la UX/UI
<br>

La aplicación debe ser `mobile-first`.

Se valorará positivamente que además sea `PWA` (progressive web app), si bien esto último es totalmente opcional.
<br>
<br>

### Sobre los recursos de terceros

Se permite (y recomienda, si con ello se minimiza el tiempo de desarrollo y se acelera así el de entrega) el `uso de cualquier recurso de terceros` (librerías, paquetes npm, etc.) además del código propio.
<br>
<br>

### Sobre la metodología

Durante el desarrollo del proyecto completo, se seguirá una metodología ágil tipo SCRUM.

Esto implicará el establecimiento de un backlog de tareas, un sprint con sus story points y reparto de tareas.

_Opcionalmente, se valorará positivamente aplicar TDD (e2e y pruebas unitarias)._

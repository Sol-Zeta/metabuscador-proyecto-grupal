
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
- Salir : `/salir`
- Favoritos : `/favoritos`

<br>
<br>

### Vista inicial (home)
<br>

`/` : Vista de inicio de la app. Tendrá como mínimo un input de texto y un botón para efectuar la búsqueda. Una vez realizada, se mostrará debajo una lista de "tarjetas" que contengan los datos más relevantes de cada resultado y un botón para guardar cada una de ellas en favoritos.  
Cada vez que se realice una nueva búsqueda, los resultados anteriores dejarán de mostrarse. 

#### !!!! Sobre las tarjetas de resultados:
 Información sugerida: 
 - Título
 - Imagen representativa (!!!! en mi experiencia personal, es un dolor de estómago almacenar imágenes en Mongo y en el caso de SQL, en su momento yo no lo pude hacer y luego no lo volví a intentar, si tenemos claros los pasos a seguir para alcanzar dicho objetivo, lo pondría, sino, evaluaría las probabilidades de éxito de este punto, aunque creo que es muy útil saber hacerlo)
 - Fecha de publicación (si corresponde)
 - Empresa, cliente o proveedor del curso
 - Duración en horas (para los cursos)
 - Requisitos u otra información relevante para cualquiera de las 3 apps. 
 - Botón para añadir a favoritos (!!!! ver siguiente comentario)

#### !!!! Sobre guardar en favoritos:
- Opción 1: 
Si el usuario está logueado, se almacenarán sus selecciones en base de datos. En caso de que el usuario no esté logueado, la app deberá redirigir a /ingresar
- Opción 2: el botón para guardar en favoritos se muestra solo en el caso de que el usuario esté logueado. Si no lo está, el botón no se muestra. 
- Opción 3 (la más sencilla, pero también la menos parecida a un caso real): La vista inicial debe ofrecer la posibilidad de registrarse o loguearse. En este caso, el input de búsqueda y los resultados de la misma forman parte de una nueva vista privada a la que solo se puede acceder estando logueado. 
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
<br>
<br>

### Vista salir
<br>

<strong>`/salir`</strong> : Cierre de sesión y redirección a **home**.

<br>
<br>

### Vista favoritos
<br>

<strong>`/favoritos`</strong> : Mostrará los resultados seleccionados por el usuario como favoritos, del mismo modo en que se muestran los resultados de búsqueda. Cada "tarjeta" tendrá un botón para borrar la selección de favoritos. Esta vista será privada y solo se podrá acceder si el usuario está logueado. 

<br>
<br>

#### Notas adicionales
<br>
Sobre el control de acceso
La aplicación debe estar protegida a entradas indebidas de usuarios no registrados (o autorizados por un proveedor externo), de manera que el endpoint asociado a la zona privada (`/favoritos`) comprobará si la sesión está abierta, y en caso contrario redireccionará al área `login` de la app.
<br>
<br>

Para el `login` con credenciales email y contraseña, deberá hacerse mediante JWT (el cifrado es opcional). Para la parte de login con uno o más proveedores de terceros deberá hacerse mediante OAuth (con o sin Firebase, a elegir; en cualquier caso, con un proveedor OAuth será suficiente).

<br>
<br>

#### Sobre el modelo de datos
<br>

El almacenamiento y la búsqueda de los datos, se realizará de la siguiente manera:

!!!! Toda la información relativa a los `usuarios` de la plataforma (credenciales y otras cuestiones de acceso, así como la asociación de favoritos a usuarios) se almacenará en una base de datos relacional SQL.

!!!! Los datos de las búsquedas provendrán del scrapping de al menos dos webs distintas que deberán seleccionarse previo análisis de las posibilidades de hacer scrapping y la relevancia de los datos que se puedan obtener. 


El objetivo será en todo momento que no se replique información, dando prioridad a OMDB si ya dispone de los datos de una película, y si no es así, complementarla con una base de datos local.

<br>
<br>

### Sobre la UX/UI
<br>

La aplicación debe ser `mobile-first` y (!!!!) `SPA` (single page application), de manera que no haya en ningún momento recarga de página, y solo se carguen y rendericen aquellos contenidos mínimos necesarios con cada cambio de endpoint.

Se valorará positivamente que además sea `PWA` (progressive web app), si bien esto último es totalmente opcional.
<br>
<br>

#### Sobre los recursos de terceros

Se permite (y recomienda, si con ello se minimiza el tiempo de desarrollo y se acelera así el de entrega) el `uso de cualquier recurso de terceros` (librerías, paquetes npm, etc.) además del código propio.
<br>
<br>

!!!! Sobre la metodología

Durante el desarrollo del proyecto completo, se seguirá una metodología ágil tipo SCRUM, aplicando además TDD (!!!!!!) desde el comienzo hasta el final.

Esto implicará el establecimiento de un backlog de tareas, un sprint con sus story points y reparto de tareas, así como la creación de tests unitarios (!!!!!) desde el principio y, a ser posible, la realización de tests e2e al final.(!!!!!!)


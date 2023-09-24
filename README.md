KariPics - README
En esta guía, te proporcionaremos las instrucciones necesarias para poner en funcionamiento la aplicación KariPics. Si bien la aplicación es completamente funcional, es importante tener en cuenta un detalle particular en la forma en que abordamos un problema específico.

Instrucciones de Configuración
Antes de ejecutar la aplicación, es esencial realizar algunas configuraciones iniciales, como la creación de la base de datos, la migración de datos y la carga de datos iniciales en PostgreSQL (PSQL). También hemos incluido un usuario administrador con información ficticia pero memorable para propósitos de prueba.

Sigue estos pasos:

Creación de la Base de Datos: Ejecuta el siguiente comando para crear la base de datos:

lua
Copy code
rails db:create
Migración de Datos: Realiza la migración de datos con el siguiente comando:

undefined
Copy code
rails db:migrate
Carga de Datos Iniciales (Seed): Carga los datos iniciales, incluyendo el usuario administrador, con el siguiente comando:

undefined
Copy code
rails db:seed
Validación de Imagen de Avatar
Un detalle importante a tener en cuenta es la validación de la imagen de avatar al crear una cuenta a través del botón de registro. Sin embargo, hemos encontrado una limitación en la carga de imágenes a través de la carga inicial de datos (seed) para el usuario administrador.

Para abordar esta limitación, hemos realizado la siguiente modificación en el archivo ./app/models/user.rb: hemos comentado la línea 8, que valida que el avatar no sea nulo o vacío en el momento de la creación de un usuario.

Nota: La descomentación de la línea 8 en ./app/models/user.rb se debe realizar manualmente antes de iniciar la aplicación.

Proceso de Trabajo
El orden recomendado de trabajo es el siguiente:

Ejecuta rails db:create para crear la base de datos.
Realiza la migración de datos con rails db:migrate.
Carga los datos iniciales con rails db:seed.
Manualmente, descomenta la línea 8 en el archivo ./app/models/user.rb para habilitar la validación de la imagen de avatar.
Inicia el servidor con rails s.
Crea una cuenta de usuario dentro del sitio accediendo a http://127.0.0.1:3000.
¡Listo! Con estos pasos, deberías poder utilizar la aplicación KariPics sin problemas.
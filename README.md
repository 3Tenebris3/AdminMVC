# AdminMVC

# MVC NodeJS / Mongodb / MVC 

## VIDEO
[VIDEO ADMIN-MVC](https://udlaec-my.sharepoint.com/:f:/g/personal/joaquin_nunez_udla_edu_ec/Eq9lSQfWxQRNmXe7SxEUIX8BaHqDhOzmNfOKNd2EVVy94g?e=CTjaGE)

## Descripcion
El programa se encuentra publicado en la rama MASTER


Se ha replicado de manera eficiente y eficaz el proyecto desarrollado en MVC.NET usando NodejJS y MongoDB, que utiliza una base de datos. Se proyecta basicamente un CRUD
La arquitectura de la aplicación se basa en el patrón Modelo-Vista-Controlador (MVC). Aquí está la explicación de cada sección del código:

1. **index.js (Entrada principal de la aplicación):**
   - Importa y configura los módulos necesarios (Express, Handlebars, Path, Method-Override).
   - Inicializa la aplicación Express.
   - Carga la configuración de la base de datos desde './database'.
   - Configura las vistas utilizando Handlebars como motor de plantillas.
   - Define middlewares para procesar datos en las solicitudes (urlencoded, methodOverride).
   - Establece variables globales (aunque actualmente no se están utilizando).
   - Define las rutas de la aplicación (en este caso, solo se está utilizando './routes/index').
   - Sirve archivos estáticos desde el directorio 'public'.
   - Inicia el servidor y escucha en el puerto especificado.

2. **database.js (Configuración de la base de datos):**
   - Importa Mongoose (una biblioteca de modelado de objetos MongoDB para Node.js).
   - Define la URL de conexión a la base de datos MongoDB.
   - Establece parámetros de conexión.
   - Conecta a la base de datos utilizando la URL y los parámetros proporcionados.
   - Muestra mensajes en la consola indicando si la conexión fue exitosa o si ocurrió un error.

3. **loans-controller.js (Controlador para la lógica de préstamos):**
   - Importa el modelo 'Loan' y el módulo 'all' desde las rutas.
   - Define un objeto 'controller' que contendrá funciones relacionadas con la lógica de préstamos.
   - `generateFines`: Calcula multas para todos los prestatarios. Itera sobre la lista de prestatarios y calcula la diferencia entre la fecha de entrega y la fecha de finalización del préstamo. Si la diferencia es negativa, calcula la multa utilizando la variable 'fine' y actualiza el campo 'fine' en el objeto del préstamo.
   - `getAllBorrowers`: Recupera todos los prestatarios de la base de datos, ordenados por fecha de inicio descendente. Luego, calcula las multas para cada prestatario y renderiza la vista 'index' con la lista de prestatarios y sus multas.

4. **loans.js (Modelo de datos):**
   - Define el esquema de datos para los préstamos utilizando Mongoose.
   - Cada préstamo tiene propiedades como usuario, ítem, fecha de inicio, fecha de finalización, fecha de entrega, estado, etc.
   - Exporta el modelo 'Loan' basado en el esquema.

5. **Routes/index.js (Manejo de rutas):**
   - Utiliza Express Router para gestionar las rutas.
   - Importa el controlador 'loans-controller' que contiene funciones para manejar las solicitudes relacionadas con los préstamos.
   - Define una ruta GET para la raíz ('/') que llama a la función `getAllBorrowers` del controlador.

6. **index.hbs (Vista):**
   - Define la apariencia de la página web utilizando el motor de plantillas Handlebars.
   - Muestra una tabla que presenta información sobre los préstamos, como usuario, ítem, fechas, estado y multa.
   - Utiliza lógica Handlebars para iterar sobre la lista de prestatarios y mostrar la información en la tabla.

En resumen, la aplicación sigue el patrón Modelo-Vista-Controlador (MVC). La vista (`index.hbs`) se encarga de la presentación, el modelo (`loans.js`) maneja la estructura de datos y la interacción con la base de datos, y el controlador (`loans-controller.js`) contiene la lógica de la aplicación y gestiona las solicitudes del cliente. Las rutas (`Routes/index.js`) conectan las solicitudes del cliente con las funciones adecuadas del controlador, el archivo `index.js` actúa como el controlador principal, `database.js` maneja la configuración de la base de datos, y `loans-controller.js` contiene funciones específicas para la lógica relacionada con los préstamos. 

## Tecnologias Utilizadas

* [ASP.NET](https://docs.microsoft.com/en-us/dotnet/framework/)
* [Node JS](https://nodejs.org/es/docs/)
* [MongoDB](https://docs.mongodb.com/)
* [Heroku](https://www.heroku.com/)

## Deployment on Heroku

https://fines-app-nodejs.herokuapp.com

# Contact
* Student e-mail: `joaquin.nunez@udla.edu.ec`

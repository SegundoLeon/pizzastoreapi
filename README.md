# API en NodeJS con swagger-autogen para Watson Assistant

Este proyecto pretende servir de guia para construir una API REST con NodeJS y Express, y para generar un documento OpenAPI v3.0 en formato .json utilizando la librería swagger-autogen. Este ultimo archivo permitirá crear una Extension Personalizada en Watson Assistant para realizar consultas en esta API desde las acciones de nuestro asistente.

### Publicar API y generar definición del servicio
Sigua los siguientes pasos para probar esta API en su entorno local:

Descarge este codigo y abralo con Visual Code u otro editor
Instale las dependencias del proyecto desde una terminal:

```bash
$ npm install
```

Luego debes publicar esta API en tu nube favorita y actualizar la URL en el archivo swagger.js. 


> Note: En este caso se creo una aplicacion en Heroku conectada a este repositorio GitHub y configurada para realizar un despliegue automatico. Aqui la ruta donde se encuentra publicada: [https://infobaseapi.herokuapp.com/](https://infobaseapi.herokuapp.com/)


Ahora vamos a generar el archivo .json con la definicion del servicio. Para ello ejecutamos el siguiente comando en la terminal:

```bash
$ node swagger
```

Finalmente comprobamos con el explorador del editor que se ha generado el archivo: swagger-output.json. 


### Configurar Extension Personalizada en Watson Assistant

Pasos para crear una extension:
- Dentro de Watson Assistant seleccionar la opcion "Integrations" desde la barra laterial izquierda
- Hacer clic en el boton "Build custom extension"

![Build custom extension](https://raw.githubusercontent.com/SegundoLeon/pizzastoreapi-swagger-autogen/main/assets/extension.png)

- En el paso "Get started" hacer clic en el boton "Next"
- En el paso "Basic information" ingresar un nombre y una descripcion, y luego seleccionar "Next"
- En el paso "Import OpenAPI" subir el archivo .json que generaste anteriormente
- Luego en el paso "Review extension" seleccionar "Finish"

Pasos para agregar la extension a tu asistente:
- Ubica tu extension y haz clic en la opcion "Add +"
- Seleciona la opcion "Add" de la ventana emergente
- Luego selecciona el boton "Next" en el paso "Get started"
- Haz clic en el boton "Next" en el paso "Authentication"
- Luego selecciona el boton "Finish", y
- Finalmente haz clic en el boton "Close"

![Resultado](https://raw.githubusercontent.com/SegundoLeon/pizzastoreapi-swagger-autogen/main/assets/resultado.png)


### Utilizar la Extension Personalizada en Watson Assistant

Creamos un nuevo asistente con una accion y en uno de sus pasos utilizamos la extension para comprabar que estamos enviando y recibiendo informacion desde nuestro API.

Pasos para utilizar la extensión dentro de una accion:

- Cree una accion, por ejemplo de nombre: "Quiero ordenar una pizza"
- Cree un paso para conocer la pizza preferida por el cliente
- Cree un segundo paso para confirmar el pedido
- Cree un tercer paso para enviar el pedido a la API. En la seccion "And then" seleccione la opcion "Use an extension"
- En la ventana "Extension setup" seleccione la extension agregada anteriormente; luego seleccione la operacion "/bills POST"; despues, en el parametro "producto" seleccione el paso donde el usuario seleccionó el nombre de la pizza; y luego seleccione "Apply".
- Comprobamos que la acción esta funcionando correctamente.

![Configurar acción](https://raw.githubusercontent.com/SegundoLeon/pizzastoreapi-swagger-autogen/main/assets/accion.png)


### Informacion complementaria:

- [Documentacion de swagger-autogen: OpenAPI 3.x](https://www.npmjs.com/package/swagger-autogen#openapi-3x)
- [OpenAPI Specification](https://swagger.io/specification/)
- [Swagger Editor con el ejemplo de Petstore](https://editor.swagger.io/)
- [Autogenerated documentation API with OpenAPI and Swagger for NodeJS and Express](https://dev.to/luizcalaca/autogenerated-documentation-api-with-openapi-and-swagger-for-nodejs-and-express-31g9)
- [Cómo documentar API con Swagger & Node js & Express](https://www.youtube.com/watch?v=rIWGcxnVIA8)
- [Forma fácil de desplegar una App Express en Heroku utilizando Visual Code](https://www.youtube.com/watch?v=QU6b-leGxy4)
- [Deploy Proyecto web con Heroku CLI](https://www.youtube.com/watch?v=6WcBSNxEow8)
- [Como crear y probar tu API de manera sencilla](https://www.youtube.com/watch?v=AWcm56_eNZg)
- [Online Markdown Editor](https://dillinger.io/)
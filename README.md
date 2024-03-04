# Comenzando

Se deberán crear colecciones, carpetas y pedidos, usar scripts para manipular variables y 
generar assertions significativas y por último generar un reporte HTML con los resultados de sus ejecuciones. Para esta tarea utilizaran la API contenida en el siguiente [link](https://gorest.co.in/). Esta API consta de un listado de usuarios los cuales pueden generar posts y también comentar estos posts.


# Pre requisitos
- Postman
- Jenkins

# Flujo
Listar todos los comentarios y quedarse con el último de la lista.
Identificar en qué post se encuentra ese comentario y ver todos los comentarios en ese post.
Crear un nuevo comentario en este post, e implementar una validación de esquema de la respuesta.
Ver todos los comentarios en ese post nuevamente y confirmar que aparezca el recién creado.
Modificar el nuevo comentario creado recientemente.
Ver todos los comentarios en ese post nuevamente y confirmar que aparezca la modificación.
Borrar ese comentario.
Confirmar que este no aparezca en el listado de todos los comentarios del post.
Ejecutar este flujo utilizando un archivo CSV que proporcione 5 iteraciones de datos. El archivo CSV deberá contener el nombre y mail del usuario que creará el nuevo comentario.

# Tener en cuenta que:
Todos los pedidos deberán contar con assertions significativas.
Es obligatorio el uso de variables del tipo que crean convenientes.
Se tendrá que utilizar un archivo CSV para la ejecución del flujo.
Nota: Para evitar errores es recomendable exportar los archivos con las variables de ambiente y las variables globales, e incluirlas en la carpeta del proyecto.


# Testing
   # Request
   - GetComments
        URL: https://gorest.co.in/public/v2/comments
        Se valida que no este vacio el array. 

   - PostComment
        URL: https://gorest.co.in/public/v2/posts/{{idPost}}/comments
        Se valida que el status code sea de exito, 201.

   - PatchComment      
        URL: https://gorest.co.in/public/v2/comments/{{idComment}}
        Se valida que el status code sea de exito, 200 y que el nombre
        del comentario sea el que se actualizo.       

   - DeleteComment
        URL: https://gorest.co.in/public/v2/comments/{{idComment}}
        Se valida que el status code sea de exito, 204 y que el elemento
        eliminado no se encuentre.

# Variables
   - idPost
   - idComment
   - name
   - email

# Ejecución
   Para ejecutar se hicieron las siguientes integraciones, se puede ejecutar de forma local o desde la nube en el build

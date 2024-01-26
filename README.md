# Working-with-Amazon-DynamoDB

Usaremos Amazon DynamoDB para almacenar y administrar la informacion del Menu. Usar base de datos, simplifica la administracion de datos porque puedes realizar una consultar, ordenar, editar e indexar datos facilmente.
Usaremos la Linea de comandos de AWS (AWS CLI) y AWS SDK para Python (Boto3) para trabajar con DynamoDB.
En un siguiente repositorio, utilizaremos llamadas a la API desde el sitio web de la cafeteria para recuperar y actualizar dinamicamente los datos almacenados en una tabla de DynamoDB.

Previamente hemos creado algunos recursos en nuestra cuenta de AWS:
- Instancia de AWS Cloud9(IDE)
- Instancia de EC2 para crear codigo y ejecutar comandos a traves de la CLI de AWS.

Al final nuestra arquitectura deberia quedar como la siguiente imagen
![Arquitectura Final](https://github.com/mhcuenca/Working-with-Amazon-DynamoDB/blob/main/DYNAMO1.JPG)
<h1>Escenario</h1>
La pagina web de la cafeteria funciona y hubo un aumento en el numero de clientes. Varios Clientes mencionaron que seria útil que el sitio web tuviera actualizado el menú. De este modo, podrian utilizar el menú para comprobar la disponibilidad de los alimentos antes de ir a la cafeteria.

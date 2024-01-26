# Working-with-Amazon-DynamoDB

Usaremos Amazon DynamoDB para almacenar y administrar la informacion del Menu de una Cafeteria. Usar base de datos, simplifica la administracion de datos porque puedes realizar una consultar, ordenar, editar e indexar datos facilmente.
Usaremos la Linea de comandos de AWS (AWS CLI) y AWS SDK para Python (Boto3) para trabajar con DynamoDB.
En un siguiente repositorio, utilizaremos llamadas a la API desde el sitio web de la cafeteria para recuperar y actualizar dinamicamente los datos almacenados en una tabla de DynamoDB.

Previamente hemos creado algunos recursos en nuestra cuenta de AWS:
- Instancia de AWS Cloud9(IDE)
- Instancia de EC2 para crear codigo y ejecutar comandos a traves de la CLI de AWS.

Al final nuestra arquitectura deberia quedar como la siguiente imagen
![Arquitectura Final](https://github.com/mhcuenca/Working-with-Amazon-DynamoDB/blob/main/DYNAMO1.JPG)
<h1>Escenario</h1>
La pagina web de la cafeteria funciona y hubo un aumento en el numero de clientes. Varios Clientes mencionaron que seria útil que el sitio web tuviera actualizado el menú. De este modo, podrian utilizar el menú para comprobar la disponibilidad de los alimentos antes de ir a la cafeteria.
Para cumplir con el requerimiento de actualizar dinamicamente el Menu. Almacenaremos la información en DynamoDB, para recuperar la información de la tabla crearemos un script que recupere todos los artículos del inventario de la tabla y otro script (como prueba de concepto) que utilice un nombre de producto para recuperar un único registro.

Utilizaremos la CLI de AWS y el SDK para Python para configurar y crear una tabla DynamoDB, cargar registros en la tabla y extraer datos de la tabla.

<h1>Preparando el Entorno</h1>
Importaremos algunos archivos e instalaremos algunos paquetes en el ambiente de AWS Cloud9. Buscamos el servicio Cloud9 y seleccionamos *Cloud9 Instance* y clic en Open IDE.

![cLOUD9](https://github.com/mhcuenca/Working-with-Amazon-DynamoDB/blob/main/DYNAMO2.JPG)

Descargamos y extraemos los archivos que necesitaremos para nuestro entorno. Ejecutaremos el siguiente comando en la terminal.
	
`wget https://aws-tc-largeobjects.s3.us-west-2.amazonaws.com/CUR-TF-200-ACCDEV-2-91558/03-lab-dynamo/code.zip -P /home/ec2-user/environment`

![](https://github.com/mhcuenca/Working-with-Amazon-DynamoDB/blob/main/Dynamo3.JPG)

Debería ver que el archivo code.zip se ha descargado en la instancia de AWS Cloud9 y que ahora se encuentra en el panel de navegación izquierdo. Extraiga el archivo ejecutando el siguiente comando
`unzip code.zip`
Esta acción extrae los archivos de code.zip. En el panel Entorno de la izquierda, ahora debería ver una nueva carpeta llamada recursos y Python_3.
Ejecutaremos un script que actualice la version de Python instalada en Cloud9, tambien actualizara la versión de AWS CLI. Cambiamos los permisos del script y luego ejecutamos.

`chmod +x ./resources/setup.sh && ./resources/setup.sh`

En el terminal de AWS Cloud9 Bash, ejecute el siguiente comando `pip show boto3`

![](https://github.com/mhcuenca/Working-with-Amazon-DynamoDB/blob/main/Dynamo4.JPG)




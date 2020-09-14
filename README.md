# desafio2MostrarFeriados

API a utilizar: https://nolaborables.com.ar/api/v2/feriados/2019


Utilizando la API dada, crear una página web que tenga un input (con el que vamos a poder ingresar un año), y un botón “Mostrar feriados”. Cuando hacemos click en el botón, tenNemos que mostrar una tabla con todos los feriados del año ingresado en el input.


Para cambiar el año en la API, hay que cambiar el número 2019 que se encuentra al final, por cualquier otro año válido. La API solo acepta los años entre 2011 y 2019 (inclusives).

1. Descaga el archivo comprimido en la clase 2 llamado 
    "desafioClase2.zip" y lo descomprimimos, abrimos con el 
    editor de código que usas sublime o Vsual Studio Code
2. Entramos en el archivo app.js
3. Copiamos la url de la api 
    https://nolaborables.com.ar/api/v2/feriados/ 
4. Creamos una función "prepararFeriados"

 ![Image of Yaktocat](https://github.com/luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/4.png)

5. Dentro vamos a capturar por el id #a una caja de texto 
    para obtener como valor el año a consultar los no laborables y la 
    guadamos en una variable.

 ![Image of Yaktocat](https://github.com/luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/5.png)

6. Declaramos otra variable y guardamos la url de nuestra API

 ![Image of Yaktocat](https://github.com/luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/6.png)

7. Usamos un método fetch dentro colocamos como parámetro 
    la variable de la url

 (https://github.com/luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/7.png)

8. usamos el método then para indicar  que vamos a usar en 
la función anterior que usaremos un archivo json

 (https://github.com//luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/8.png)

9. De nuevo usamos otro método then ahora para hacer un 
    callback y pasamos como parámetro el archivo recibido antes y vamos a guardar 
    los valores en el arreglo vacío que den bemos declarar como global.  

 (https://github.com/luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/9.png)

10. Creamos el evento load para capturar la clase principal
    usando la propiedad innerHTML dentro de ella añadimos 
    una etiqueta <label> con un valor "Año a consultar: y un <input> 
    para que ingresen el año, en otra línea fuera del innerHTML
    capturamos el botón y le agregamos un evento click que 
    va a llamar una función prepaparFeriados


 (https://github.com/luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/10.png)

11. Creamos una función para mostrar los datos, allí vamos a 
    capturar por la clase "card-group" y le pasamos por cada 
    iteración que realice una card que va a contener un sub-título
    con el día y mes y dos párrafos para agregar motivo y tipo y 
    usamos un ternario para escribir cada mes, lo puedes hacer con if


 (https://github.com/luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/11.png)

12. Ya puedes hacer la prueba ejecutando tu live server para ejecutar tu servidor local

 (https://github.com/luisNavasArg/desafio2MostrarFeriados/blob/master/imagenes/12.png)
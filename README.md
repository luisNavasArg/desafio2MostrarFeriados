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
5. Dentro vamos a capturar por el id #a una caja de texto 
    para obtener el año a consultar los no laborables y la 
    guadamos en una variable.
6. Declaramos otra variable y guardamos la url de nuestra API
7. Usamos un método fetch dentro colocamos como parámetro 
    la variable de la url
8. usamos el método then para indicar  que vamos a usar en 
la función anterior que usaremos un archivo json 
9. De nuevo usamos otro método then ahora para hacer un 
    callback y guardamos en una variable datos la información 
    del archivo recibido antes y dentro vamos guardando dentro 
    del arreglo.      
10. Creamos el evento load para capturar la clase principal
    usando la propiedad innerHTML dentro de ella añadimos 
    una etiqueta con un valor "Año a consultar: y un input 
    para que ingresen el año, en otra línea fuera del innerHTML
    capturamos el botón y le agregamos un evento click que 
    va a llamar una función prepaparFeriados
11. Creamos una función para mostrar los datos, allí vamos a 
    capturar por la clase "card-group" y le pasamos por cada 
    iteración que realice una card que va a contener un sub-título
    con el día y mes y dos párrafos para agregar motivo y tipo y 
    usamos un ternario para escribir cada mes, lo puedes hacer con if 
12. Ya puedes hacer la prueba ejecutando tu live server para ejecutar tu servidor local
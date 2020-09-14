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

  	const prepararFeriados =(ev)=>{
  		ev.preventDefault();
	};

5. Dentro vamos a capturar por el id #a una caja de texto 
    para obtener como valor el año a consultar los no laborables y la 
    guadamos en una variable.

 	const prepararFeriados =(ev)=>{
  		ev.preventDefault();
		let a = document.querySelector("#a").value;
	};

6. Declaramos otra variable y guardamos la url de nuestra API

	const prepararFeriados =(ev)=>{
		ev.preventDefault();
		let a = document.querySelector("#a").value;
		let url = `https://nolaborables.com.ar/api/v2/feriados/${a}`;
	};

7. Usamos un método fetch dentro colocamos como parámetro 
    la variable de la url

    const prepararFeriados =(ev)=>{
		ev.preventDefault();
		let a = document.querySelector("#a").value;
		let url = `https://nolaborables.com.ar/api/v2/feriados/${a}`;
		fetch(url);
	
	};

8. usamos el método then para indicar  que vamos a usar en 
la función anterior que usaremos un archivo json

	const prepararFeriados =(ev)=>{
		ev.preventDefault();
		let a = document.querySelector("#a").value;
		let url = `https://nolaborables.com.ar/api/v2/feriados/${a}`;
		fetch(url)
		.then(res=>res.json());
		
	};

9. De nuevo usamos otro método then ahora para hacer un 
    callback y pasamos como parámetro el archivo recibido antes y vamos a guardar 
    los valores en el arreglo vacío que den bemos declarar como global.  

    let api = [];
    const prepararFeriados =(ev)=>{
		ev.preventDefault();
		let a = document.querySelector("#a").value;
		let url = `https://nolaborables.com.ar/api/v2/feriados/${a}`;
		fetch(url)
		.then(res=>res.json())
		.then((datos)=>{	
			 api=[...datos]; 
			 mostrarApi(api);
	});
	
};

10. Creamos el evento load para capturar la clase principal
    usando la propiedad innerHTML dentro de ella añadimos 
    una etiqueta <label> con un valor "Año a consultar: y un <input> 
    para que ingresen el año, en otra línea fuera del innerHTML
    capturamos el botón y le agregamos un evento click que 
    va a llamar una función prepaparFeriados

    window.addEventListener("load",()=> {
		document.querySelector(".principal").innerHTML+=`
			<form class="form-inline">
				<div class="form-group mb-2">
					<label for="a" class="sr-only">Año a consultar: </label>
					<input class="form-control" type="text" id="a">
					<button class="button btn-secondary">Mostrar Feriados</button> 
				</div>
			</form>
		`;
		document.querySelector(".button").addEventListener("click", 
		prepararFeriados);
	});


11. Creamos una función para mostrar los datos, allí vamos a 
    capturar por la clase "card-group" y le pasamos por cada 
    iteración que realice una card que va a contener un sub-título
    con el día y mes y dos párrafos para agregar motivo y tipo y 
    usamos un ternario para escribir cada mes, lo puedes hacer con if


    const mostrarApi=(a)=>{
		a.forEach((a)=>{
				document.querySelector(".card-group").innerHTML+=`
			<div class="col-3 m-3">
				<div class="card bg-primary text-white">
					<div class="card-head">
						<h2 class="text-center">Día: ${a.dia} <br> Mes: ${
																	a.mes == 1 ? "Enero" : 
																	a.mes == 2 ? "Febrero" : 
																	a.mes == 3 ? "Marzo" : 
																	a.mes == 4 ? "Abril":
																	a.mes == 5 ? "Mayo":
																	a.mes == 6 ? "Junio":
																	a.mes == 7 ? "Julio":
																	a.mes == 8 ? "Agosto":
																	a.mes == 9 ? "Septiembre":
																	a.mes == 10 ? "Octubre":
																	a.mes == 11 ? "Noviembre":
																	"Diciembre"
																	}</h2>		
					</div>
					<div class="card-body">
						<p>${a.motivo}</p>
					</div>
					<div class="card-footer">
						<p>${a.tipo}</p>
					</div>
				</div>
			</div>
		`;
		});
	};


12. Ya puedes hacer la prueba ejecutando tu live server para ejecutar tu servidor local

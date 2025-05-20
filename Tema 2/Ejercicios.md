**2.2.1. Predecir el resultado**. Analiza el siguiente código y **trata de adivinar** qué se imprimirá en la consola sin ejecutarlo. Rellena la tabla con las salidas que se producen:

```javascript
console.log(a); // LÍNEA 1
var a = 10; 
console.log(a); // LÍNEA 2

let b = 20;
console.log(b); // LÍNEA 3

const c = 30;
console.log(c); // LÍNEA 4

// Prueba de re-declaración
var a = 50;  
console.log(a); // LÍNEA 5

let b = 60; // LÍNEA 6
console.log(b);  // LÍNEA 7

c = 40; // LÍNEA 8
console.log(c); // LÍNEA 9

// Bloques y ámbito
if (true) {
    var d = 100;
    let e = 200;
    const f = 300;
}

console.log(d); // LÍNEA 10
console.log(e); // LÍNEA 11
console.log(f); // LÍNEA 12

function test() {
    var g = 400;
    let h = 500;
    const i = 600;
}

test();
console.log(g); // LÍNEA 13
console.log(h); // LÍNEA 14
console.log(i); // LÍNEA 15
```

**2.4.2. ⭐ Correción de errores:** Analiza el siguiente código y corrige todos los errores:

```javascript
let numero = 50;
let textoNumero = toString(numero); 

let cadena = "100px";
let numeroConvertido = Number(cadena); 

let decimal = "3.14";
let numeroEntero = parseInt decimal; 

let resultado1 = "5" - 2; 
let resultado2 = "10" + 2; 

let numero2 = Number("Hola123");
```


**2.7.7.**. Crea una página web con un input que pida al usuario una tarea y pulsando un botón lo añada a una lista de tareas empleando `ul` y `li`. Te proporcionamos la página HTML sobre la que hacer cambios:

```html
<!DOCTYPE html>
<html lang="es">
<body>
    <h1>Lista de Tareas</h1>
    <input type="text" id="tarea" placeholder="Escribe una tarea...">
    <button onclick="agregarTarea()">Añadir Tarea</button>

    <ul id="listaTareas"></ul>

    <script>
        // Escribe tu código aquí
    
    </script>
</body>
</html>
```

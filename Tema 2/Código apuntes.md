# Tema 2. El lenguaje Javascript

# 2.1. Sentencias en Javascript

```javascript
let nombre = "Ana";  // Sentencia de declaración
console.log(nombre);  // Sentencia de ejecución
```

# 2.2. Bloques en Javascript

```javascript
{
  let mensaje = "Hola, mundo!";
  console.log(mensaje);
}
```

# 2.4. Variables y asignación 

## 2.4.1. Variables

### Diferencias entre var, let y const

#### 1. Declaraciones con `var`

```javascript
var nombre = "Ana";
console.log(nombre); // Ana

var nombre = "Luis"; // Se puede redeclarar 
console.log(nombre); // Luis

if (true) {
  var edad = 30;  // Se declara dentro del bloque
}
console.log(edad); // ⚠️ 30 (¡pero se puede acceder fuera del bloque!)
```

```javascript
var texto = "He sido declarada FUERA del bloque";
var function miFuncion() {
  var texto = "He sido declarada DENTRO de una función"
  return;
}
console.log(texto); // ⚠️ "He sido declarada FUERA del bloque" 
```

#### 2. Declaraciones con `let`
```javascript
let ciudad = "Madrid";
console.log(ciudad); // Madrid

ciudad = "Barcelona"; // ✅ Se puede reasignar
console.log(ciudad); // Barcelona

if (true) {
  let edad = 25;
  console.log(edad); // 25 (Está dentro del bloque)
}
console.log(edad); // ❌ Error: edad no está definida fuera del bloque
```

#### 3. Declaraciones con `const`
```javascript
const PI = 3.1416;
console.log(PI); // 3.1416

PI = 3.15; // ❌ Error: No se puede reasignar un valor a una constante
```


# 2.9. Decisiones

## 2.9.1. `if` y `else`

```javascript
let nota = 85;

if (nota >= 90) {
  console.log("Sobresaliente");
} else if (nota >= 75) {
  console.log("Aprobado");
} else {
  console.log("Insuficiente");
}
```

## 2.9.2. `switch`

```javascript
let dia = "lunes";

switch (dia) {
  case "lunes":
    console.log("Inicio de la semana.");
    break;
  case "sábado":
  case "domingo":
    console.log("Es fin de semana.");
    break;
  default:
    console.log("Día normal.");
}
```

## 2.9.4. Cortocircuito lógico

```javascript
let usuario = "José";
// Solo se ejecuta si 'nombre' tiene valor
usuario && console.log(`Bienvenido, ${usuario}!`);

let edad = 0 || 18; // 0 es falso, así que devuelve 18
console.log(edad); // 18

// Asignación de valores por defecto
let configuracion = opciones || "Configuración por defecto";
```


# 2.10. Bucles

## 2.10.1. Bucle `for`

```javascript
for (let i = 0; i < 10; i++) {
  console.log("Número", i);
}
```

## 20.10.2. Bucle `while`

```javascript
let suma = 0;
let contador = 1;

while (contador <= 100) {
  suma += contador; // Suma los números del 1 al 100
  contador++;
}

console.log(`La suma total es: ${suma}`);
```

## 2.10.3. Bucle `do...while`

```javascript
let numero;

do {
  numero = Math.floor(Math.random() * 10); // Genera un número aleatorio del 0 al 9
  console.log(`Número generado: ${numero}`);
} while (numero !== 5);

console.log("¡Se generó el número 5!");
```

## 2.10.4. Bucle `for...of`

```javascript
let estudiantes = ["José", "María", "Luis", "Ana"];

for (let estudiante of estudiantes) {
  console.log(`Hola, ${estudiante}!`);
}
```

## 2.10.5. `for...in`

```javascript
const persona = { nombre: "Ana", edad: 25 };
for (let clave in persona) {
  console.log(clave, ":", persona[clave]);
}
// Muestra "nombre: Ana" y "edad: 25".
```

## 2.10.6. Control avanzado con `break` y `continue`

```javascript
for (let i = 0; i < 5; i++) {
  if (i === 3) break;   // Sale del bucle en 3
  if (i === 1) continue; // Salta la iteración 1
  console.log(i);
}
// La salida sería: 0, 2
```


# 2.13. Conceptos necesarios para desarollar páginas interactivas en Javascript


## 2.13.1. Introducción a Funciones

```javascript
function sumar(a, b) {
  console.log("¡Hola desde 'sumar'");
  return a + b; // Devuelve la suma de los parámetros
}
// Cómo invocarla
sumar(5, 4); 
```

```javascript
let multiplicar = function (a, b) {
  return a * b;
};

console.log(multiplicar(5, 6)); // 30
```

```javascript
const dividir = (a, b) => a / b;

console.log(dividir(10, 2)); // 5
```


## 2.13.2. Introducción a Objetos


### 1. Creación de un objeto literal
```javascript
const coche = {
    marca: "Toyota",
    modelo: "Corolla",
};
console.log(coche.marca); // Imprime "Toyota"
```

### 2. Creación con `new Object()`
```javascript
const coche = new Object();
coche.marca = "Toyota";
coche.modelo = "Corolla";
console.log(coche.marca); // Imprime "Toyota"
```

### 3. Acceso a las propiedades de los objetos

```javascript
const persona = {
    nombre: "Ana",
    edad: 28,
    ciudad: "Barcelona"
};
console.log(persona.nombre); // Imprime "Ana"
console.log(persona.edad);   // Imprime 28
```

```javascript
const usuario = {
    "nombre completo": "Luis Pérez",
    edad: 35
};
console.log(usuario["nombre completo"]); // Imprime "Luis Pérez"
```

## 2.13.3. Eventos

### Cómo programar eventos en JavaScript

#### 1. Integrarlo en atributos HTML (NO RECOMENDADO)
```html
<button onclick="alert('¡Hola!')">Haz clic</button>
```

#### 2. Usar `addEventListener` (RECOMENDADO)
```html
<button id="miBoton">Haz clic</button>

<script>
  document.getElementById("miBoton").addEventListener("click", function() {
      alert("¡Evento con addEventListener!");
  });
</script>
```

#### 3. Usar una función en el JavaScript
```html
<button id="boton">Haz clic</button>

<script>
  function mostrarMensaje() {
      alert("¡Evento con función!");
  }
  
  document.getElementById("boton").onclick = mostrarMensaje;
</script>
```

## 2.13.4. Arrays

### Cómo crear un array  

```javascript
// Usando corchetes []
let numeros = [1, 2, 3, 4, 5];

// Usando new Array() (poco recomendado)
let frutas = new Array("Manzana", "Pera", "Banana");

// Array mixto con diferentes tipos de datos
let mixto = [10, "Hola", true, { nombre: "Ana" }];
```

### Acceder a los elementos de un array  

```javascript
let colores = ["Rojo", "Verde", "Azul"];
console.log(colores[0]); // "Rojo"
console.log(colores[1]); // "Verde"
console.log(colores[2]); // "Azul"
```


### Tareas comunes para manipular arrays  

#### 1. Agregar y eliminar elementos  
```javascript
let frutas = ["Manzana", "Pera"];

// Agregar al final
frutas.push("Naranja");  // ["Manzana", "Pera", "Naranja"]

// Eliminar el último
frutas.pop();  // ["Manzana", "Pera"]

// Agregar al inicio
frutas.unshift("Banana");  // ["Banana", "Manzana", "Pera"]

// Eliminar el primero
frutas.shift();  // ["Manzana", "Pera"]
```

#### 2. Recorrer un array con un bucle 
```javascript
let numeros = [10, 20, 30, 40];

for (let i = 0; i < numeros.length; i++) {
    console.log(numeros[i]);
}

// O bien con forEach 
numeros.forEach(num => console.log(num));
```

#### 3. Buscar elementos en un array 
```javascript
let nombres = ["Ana", "Luis", "Carlos"];

console.log(nombres.includes("Luis")); // true
console.log(nombres.indexOf("Carlos")); // 2
console.log(nombres.indexOf("Pedro")); // -1 (no está)
```

#### 4. Convertir arrays a cadenas y viceversa 
```javascript
let palabras = ["Hola", "mundo"];
let frase = palabras.join(" ");  // "Hola mundo"

let texto = "Rojo,Verde,Azul";
let colores = texto.split(",");  // ["Rojo", "Verde", "Azul"]
```

## 2.13.5. Procedimiento para crear páginas web sencillas y modificarlas con Javascript

```html
<!DOCTYPE html>
<html lang="es">
<body>

    <h1 id="titulo">Contador: 0</h1>
    <button id="boton">Incrementar</button>

    <script>
        // Acceder a los elementos
        let titulo = document.getElementById("titulo");
        let boton = document.getElementById("boton");

        // Inicializar contador
        let contador = 0;

        // Agregar evento al botón
        boton.addEventListener("click", function() {
            contador++;  // Incrementar el contador
            titulo.textContent = "Contador: " + contador; // Actualizar el texto

            titulo.style.color = "red"; // Cambia el color del texto a rojo
        });
    </script>

</body>
</html>
```

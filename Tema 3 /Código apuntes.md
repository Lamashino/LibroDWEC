# Tema 3. Objetos predefinidos del lenguaje

# 3.1. Arrays

## 3.1.1. Cómo crear un array  

```javascript
// Usando corchetes []
let numeros = [1, 2, 3, 4, 5];
let frutas = ['manzana', 'banana', 'cereza'];

// Usando new Array() (poco recomendado)
let frutas = new Array("Manzana", "Pera", "Banana");
let numeros = new Array(1, 2, 3, 4, 5);

// Se pueden mezclar los tipos de los elementos
let mixto = [10, "Hola", true, { nombre: "Ana" }];

// Array vació que se puede rellenar después
let vacio = []

// Usando un constructor con un único argumento:
//  - Se crea un array con ese número de posiciones vacías
let vacio = new Array(5); // Crea un array de 5 posiciones vacías

// Arrays multidimensionales
let matriz = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
```

## 3.1.2. Acceder/modificar los elementos de un array  

```javascript
let colores = ["Rojo", "Verde", "Azul"];
colores[1] = 'Violeta';
console.log(colores[0]); // "Rojo"
console.log(colores[1]); // "Violeta"
console.log(colores[2]); // "Azul"

// Acceso en arrays multidimensionales
let matriz = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
console.log(matriz[1][2]); // 6
```

## 3.1.4. Recorrer un array

```javascript
  let frutas = ['manzana', 'banana', 'cereza'];

  // Bucle for
  for (let i = 0; i < frutas.length; i++) {
    console.log(frutas[i]);
  }

  // forEach
  frutas.forEach((fruta, indice) => {
      console.log(`${indice}: ${fruta}`);
  });
```


# 3.2. Conjuntos

## 3.2.1. Creación de un Set

```javascript
let frutas = new Set();

// Agregar elementos
frutas.add("manzana");
frutas.add("naranja");
frutas.add("plátano");

// Verificar si un elemento existe
console.log(frutas.has("naranja")); // true
console.log(frutas.has("kiwi"));    // false

// Eliminar un elemento
frutas.delete("manzana");
console.log(frutas); // Set(2) {'naranja', 'plátano'}

// Obtener el tamaño del conjunto
console.log(frutas.size); // 2

// Vaciar el conjunto
frutas.clear();
console.log(frutas.size); // 0
```

## 3.2.3. Recorrer un Set

### Usando `forEach()`
```javascript
// Usando `forEach()`
let numeros = new Set([10, 20, 30]);
numeros.forEach(num => console.log(num));

// Usando `for...of`
for (let num of numeros) {
  console.log(num);
}
```

## 3.2.4. Conversión entre Set y Array

```javascript
// Convertir Set → Array
let conjunto = new Set([1, 2, 3, 4]);
let array = [...conjunto];
console.log(array); // [1, 2, 3, 4]

// Convertir Array → Set
let arrayDuplicados = [1, 2, 2, 3, 4, 4, 5];
let conjuntoSinDuplicados = new Set(arrayDuplicados);
console.log([...conjuntoSinDuplicados]); // [1, 2, 3, 4, 5]
```

# 3.3. Mapas

## 3.3.1 Creación de un `Map`

```javascript
let mapa = new Map();

// Agregar elementos
mapa.set('nombre', 'Ana');
mapa.set('edad', 25);
mapa.set('activo', true);

console.log(mapa.get('nombre')); // 'Ana'
console.log(mapa.has('edad'));   // true
console.log(mapa.size);          // 3

// Eliminar un elemento
mapa.delete('activo');
console.log(mapa.size); // 2

// Vaciar el mapa
mapa.clear();
console.log(mapa.size); // 0
```

## 3.3.2. Recorrer un `Map`

```javascript
// Usando `forEach`
let mapa = new Map([
  ['a', 1],
  ['b', 2],
  ['c', 3]
]);

mapa.forEach((valor, clave) => {
  console.log(`Clave: ${clave}, Valor: ${valor}`);
});

// Usando `for...of`
for (let [clave, valor] of mapa) {
  console.log(`Clave: ${clave}, Valor: ${valor}`);
}
```

# 3.4. Funciones

## 3.4.1. Declaración de funciones  

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

## 3.4.2. Funciones flecha (`=>`)

### Función simple de suma 
```javascript
const sumar = (a, b) => a + b;
console.log(sumar(3, 4)); // 7
```

### Función sin parámetros  
```javascript
const saludar = () => console.log("Hola, mundo!");
saludar(); // Hola, mundo!
```

### Función con un solo parámetro 
```javascript
const doble = x => x * 2;
console.log(doble(5)); // 10
```

### Arrow Function con cuerpo de función  
```javascript
const multiplicar = (a, b) => {
  const resultado = a * b;
  return resultado;
};
console.log(multiplicar(3, 5)); // 15
```

### Arrow Function en métodos de objetos  
```javascript
const persona = {
  nombre: "Juan",
  presentarse: function() {
    setTimeout(() => {
      console.log(`Hola, soy ${this.nombre}`);
    }, 1000);
  }
};

persona.presentarse(); // Hola, soy Juan
```

## 3.4.3. Recursividad

### Ejemplo 1: Factorial

```javascript
function factorial(n) {
  // Caso base: cuando n es 0, el factorial es 1.
  if (n === 0) {
    return 1;
  }
  // Caso recursivo: n * factorial(n - 1)
  return n * factorial(n - 1);
}

console.log(factorial(5)); // Imprime 120
```

### Ejemplo 2: Secuencia de Fibonacci

```javascript
function fibonacci(n) {
  // Casos base
  if (n === 0) return 0;
  if (n === 1) return 1;
  // Caso recursivo
  return fibonacci(n - 1) + fibonacci(n - 2);
}

console.log(fibonacci(6)); // Imprime 8
```


# 3.5. Programación orientada a Objetos

## 3.5.1. Declaración de objetos tradicional

```javascript
const persona = {
  nombre: "Juan",
  edad: 30,
  saludar: function() {
    console.log(`Hola, soy ${this.nombre}`);
  }
};
persona.saludar();
```  

```javascript
const persona = new Object();
persona.nombre = "Ana";
persona.edad = 25;
persona.saludar = function() {
  console.log(`Hola, soy ${this.nombre}`);
};
persona.saludar();
```  

```javascript
function Persona(nombre, edad) {
  this.nombre = nombre;
  this.edad = edad;
  this.saludar = function() {
    console.log(`Hola, soy ${this.nombre}`);
  };
}
const persona1 = new Persona("Carlos", 28);
persona1.saludar();
```  

## 3.5.2. ES6 y la Programación Orientada a Objetos  

```javascript
class Persona {
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }
  saludar() {
    console.log(`Hola, soy ${this.nombre}`);
  }
}
const persona1 = new Persona("Lucía", 32);
persona1.saludar();
```  
### Métodos estáticos

```javascript
class Matemáticas {
    static sumar(a, b) {
        return a + b;
    }
}
console.log(Matemáticas.sumar(3, 4)); // Resultado: 7
```

## 3.5.4. Constructores en JavaScript  

```javascript
class Animal {
  constructor(nombre, tipo) {
    this.nombre = nombre;
    this.tipo = tipo;
  }
}
const perro = new Animal("Max", "Perro");
console.log(perro.nombre); // "Max"
```  


## 3.5.6. Borrar propiedades de un Objeto  

```javascript
let persona = {
    nombre: "Juan",
    edad: 30,
    ciudad: "Madrid"
};
delete persona.ciudad;
console.log(persona); // Resultado: {nombre: "Juan", edad: 30}
```


## 3.5.7. Herencia en JavaScript  

```javascript
class Animal {
  constructor(nombre) {
    this.nombre = nombre;
  }
  hacerSonido() {
    console.log("Sonido genérico");
  }
}

class Perro extends Animal {
  hacerSonido() {
    console.log("Guau guau");
  }
}

const miPerro = new Perro("Chip");
miPerro.hacerSonido(); // "Guau guau"
```

```javascript

class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
    
    saludar() {
        console.log(`Hola, mi nombre es ${this.nombre}`);
    }
}

class Estudiante extends Persona {
    constructor(nombre, edad, curso) {
        super(nombre, edad);
        this.curso = curso;
    }
    
    saludar() {
        console.log(`Hola, soy ${this.nombre} y estudio ${this.curso}`);
    }
}
let pedro = new Estudiante("Pedro", 25, "Física");
pedro.saludar(); // Resultado: Hola, soy Pedro y estudio Física
```

## 3.5.8. JSON (JavaScript Object Notation) 


### Sintaxis de JSON  

###  Ejemplo completo de JSON:
```javascript
{
  "cadena": "Hola, este es un ejemplo",
  "numero": 1234,
  "booleano": true,
  "nulo": null,
  "objeto": {
    "clave": "valor",
    "otroNumero": 3.14
  },
  "array": [
    "texto en array",
    42,
    false,
    null,
    {
      "subobjeto": "valor anidado"
    }
  ]
}
```

### Cómo usar JSON en JavaScript 

### Ejemplo: Recibir JSON desde una API 

```javascript
fetch('https://jsonplaceholder.typicode.com/users') // API real
  .then(respuesta => respuesta.json()) // Convertimos la respuesta a JSON
  .then(datos => console.log(datos)) // Mostramos los datos
  .catch(error => console.error('Error:', error)); // Gestionamos errores
```

### Ejemplo: Guardar y Recuperar JSON en el Navegador con `localStorage`

```javascript
// Objeto que queremos guardar
let usuario = { nombre: "Lucas", edad: 27 };

// Convertir a JSON y guardar en localStorage
localStorage.setItem("usuario", JSON.stringify(usuario));

// Obtener el JSON y convertirlo a objeto JS
let usuarioGuardado = JSON.parse(localStorage.getItem("usuario"));

console.log(usuarioGuardado.nombre); // "Lucas"
```


# 3.6. Objeto Date para gestionar fechas

## 3.6.1. Crear fechas en JavaScript 

```javascript
// 1. Obtener la fecha y hora actuales
let fechaActual = new Date();
console.log(fechaActual);  // Tue Mar 11 2025 10:30:00 GMT+0100 (Hora estándar de Europa Central)

// 2. Especificar una fecha y hora
// IMPORTANTE: Los meses empiezan en 0
let fechaEspecifica = new Date(2025, 2, 11, 10, 30, 0); // Año, Mes (0-11), Día, Hora, Minuto, Segundo
console.log(fechaEspecifica);  // Tue Mar 11 2025 10:30:00 GMT+0100

// 3. Crear una fecha a partir de una cadena de texto
let fechaTexto = new Date("2025-03-11T10:30:00");
console.log(fechaTexto); // Tue Mar 11 2025 10:30:00 GMT+0100

// 4 Crear fecha a partir de milisegundos
let fechaDesdeMs = new Date(1700000000000); // Milisegundos desde 01/01/1970
console.log(fechaDesdeMs); 
```


## 3.6.2. Métodos para obtener información de una Fecha  

```javascript
let fecha = new Date();

console.log(fecha.getFullYear()); // Año (ej. 2025)
console.log(fecha.getMonth());    // Mes (0-11) ⚠ Enero es 0
console.log(fecha.getDate());     // Día del mes (1-31)
console.log(fecha.getDay());      // Día de la semana (0 = Domingo, 6 = Sábado)
console.log(fecha.getHours());    // Hora (0-23)
console.log(fecha.getMinutes());  // Minutos (0-59)
console.log(fecha.getSeconds());  // Segundos (0-59)
console.log(fecha.getMilliseconds()); // Milisegundos (0-999)
console.log(fecha.getTime());     // Milisegundos desde 01/01/1970 (timestamp)
```

## 3.6.3. Modificar Fechas

```javascript
let fecha = new Date();

fecha.setFullYear(2030);
fecha.setMonth(5); // Junio
fecha.setDate(20);
fecha.setHours(14);
fecha.setMinutes(45);

console.log(fecha);
```

## 3.6.4. Operaciones con Fechas

### Sumar y Restar Días
```javascript
let fecha = new Date();
fecha.setDate(fecha.getDate() + 7); // Sumar 7 días
console.log(fecha);
```

### Calcular Diferencia entre Fechas
```javascript
let inicio = new Date("2025-03-01");
let fin = new Date("2025-03-11");

let diferencia = fin.getTime() - inicio.getTime(); // Diferencia en milisegundos
let dias = diferencia / (1000 * 60 * 60 * 24); // Convertir a días

console.log(`Diferencia: ${dias} días`); // "Diferencia: 10 días"
```


# 3.7. Gestión del tiempo

## 3.7.5. Ejemplo completo: cuenta atrás
```javascript
let segundos = 10;

let cuenta = setInterval(() => {
    console.log(`Tiempo restante: ${segundos} segundos`);
    segundos--;

    if (segundos < 0) {
        clearInterval(cuenta);
        console.log("¡Tiempo agotado!");
    }
}, 1000);
```


# 3.8. Almacenamiento local de datos

### Crear una cookie de forma segura

```javascript
let usuario = "Juan Pérez"; // Contiene un espacio
document.cookie = "usuario=" + encodeURIComponent(usuario) + "; expires=Fri, 31 Dec 2025 23:59:59 GMT";
```

### Leer una cookie y descodificar

```javascript
// Separamos los pares clave-valor y buscamos la clave "usuario"
let cookies = document.cookie.split("; ");
let usuario = cookies.find(row => row.startsWith("usuario="))?.split("=")[1];

if (usuario) {
    usuario = decodeURIComponent(usuario);
    console.log(usuario); // "Juan Pérez"
}
```


## 3.8.2. LocalStorage

###  Guardar datos de forma segura
```javascript
let usuario = "Juan Pérez";
localStorage.setItem("usuario", encodeURIComponent(usuario));
```

### Leer y descodificar datos
```javascript
let usuario = localStorage.getItem("usuario");
if (usuario) {
    usuario = decodeURIComponent(usuario);
    console.log(usuario); // "Juan Pérez"
}
```
### Eliminar datos

- **Borrar un dato**
```javascript
localStorage.removeItem("usuario");
```
- **Borrar todo el almacenamiento**
```javascript
localStorage.clear();
```


## 3.8.3. SessionStorage en JavaScript 

```javascript
let usuario = "Juan Pérez";
sessionStorage.setItem("usuario", encodeURIComponent(usuario));
```
- Esto almacena `"Juan Pérez"` de forma segura como `"Juan%20P%C3%A9rez"`.

### Leer y descodificar datos
```javascript
let usuario = sessionStorage.getItem("usuario");
if (usuario) {
    usuario = decodeURIComponent(usuario);
    console.log(usuario); // "Juan Pérez"
}
```


## 3.9. Generación de texto y elementos HTML desde código.

#### Ejemplo completo

```html
<!DOCTYPE html>
<html>
<body>
<p id="parrafo">   Este elemento tiene espacio extra   y contiene <span>un elemento span</span>.</p>

<script>
  let innerT = document.getElementById("parrafo").innerText;
  let textC = document.getElementById("parrafo").textContent;
  let innerH = document.getElementById("parrafo").innerHTML;

  console.log('- innerText: ')
  console.log(innerT);
  console.log('- textContent:')
  console.log(textC);
  console.log('- innerHTML:')
  console.log(innerH);
</script>
</body>
</html>

```

### 3.9.2. Generación de Elementos HTML Dinámicos

#### Ejemplo: Crear una Lista
```javascript
// Crear la lista
const lista = document.createElement("ul");

// Crear tareas dinámicas
const tareas = ["Comprar pan", "Estudiar JavaScript", "Hacer ejercicio"];

tareas.forEach(tarea => {
    const item = document.createElement("li");
    item.textContent = tarea;
    lista.appendChild(item);
});

// Añadir la lista al cuerpo del documento
document.body.appendChild(lista);
```

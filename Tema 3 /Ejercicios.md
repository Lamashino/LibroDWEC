**3.3.11**. Implementa una función que reciba una array con 5 cartas de póker y determine si el jugador tiene una escalera de color. Las cartas las puedes representar así:
```javascript
const mano = [
  { valor: 2, palo: "corazones" },
  { valor: 2, palo: "diamantes" },
  { valor: 3, palo: "tréboles" },
  { valor: 4, palo: "picas" },
  { valor: 5, palo: "corazones" }
];
```

**3.4.4.** Crea una función flecha llamada `obtenerNombres` que reciba un array de objetos con la propiedad `nombre` y devuelva un nuevo array con solo los nombres.
```javascript
const personas = [
    { nombre: 'Juan', edad: 25 },
    { nombre: 'Ana', edad: 30 },
    { nombre: 'Luis', edad: 28 }
];
console.log(obtenerNombres(personas)); // ['Juan', 'Ana', 'Luis']
```

**3.6.1.**. Crea un objeto en JavaScript, conviértelo a formato JSON y luego vuelve a convertirlo en un objeto. Por ejemplo:

```javascript
const persona = {
  nombre: "Ana",
  edad: 28,
  ciudad: "Madrid"
};
```

**3.6.2.** Usa `fetch` para obtener datos de una API de prueba y mostrar en consola los nombres de los usuarios en un lista `<ul>`. Puedes comenzar el código así:

```javascript
fetch("https://jsonplaceholder.typicode.com/users")
```

**3.6.3.** El siguiente código obtiene una lista de usuarios, pero muestra todos. Modifícalo para que solo muestre los que tengan un `id` menor a 5. Añade también código para mostrar solo los usuarios que vivan en la ciudad de "South Christy".  

```javascript
fetch("https://jsonplaceholder.typicode.com/users")
  .then(response => response.json())
  .then(data => {
    const filtrados = data.filter(user => user.id < 5); // Filtra usuarios con id < 5
    filtrados.forEach(user => console.log(user.name));
  })
  .catch(error => console.error("Error al obtener datos:", error));
```

**3.6.4.** Guarda un objeto en `localStorage` en formato JSON y recupéralo más tarde. Puedes usar este objeto:

```javascript
const usuario = { nombre: "Luis", edad: 35, pais: "España" };
```

**3.6.5.** El siguiente código tiene un error. Al intentar leer `JSON.parse(null)`, el código fallará. Corrígelo para que maneje el caso en el que no haya datos en `localStorage`.  

```javascript
const datosGuardados = localStorage.getItem("configuracion");
const configuracion = datosGuardados ? JSON.parse(datosGuardados) : { tema: "claro", idioma: "es" };

console.log(configuracion);
```

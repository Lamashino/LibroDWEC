# Tema 1. Selección de arquitecturas y tecnologías de programación

## 1.5.1. JavaScript en línea (atributos HTML como `onclick`, `onload`, etc.)

```html
<button onclick="alert('¡Hola!')">Haz clic</button>
```

## 1.5.2. JavaScript dentro de una etiqueta `<script>` en el mismo archivo HTML

```html
<!DOCTYPE html>
<html lang="es">
<body>
    <h1>Ejemplo de script en el HTML</h1>
    
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            console.log("¡La página se ha cargado!");
        });
    </script>
</body>
</html>
```

## 1.5.3. JavaScript en un archivo externo con `<script src="archivo.js">`

Archivo HTML (`index.html`)

```html
<!DOCTYPE html>
<html lang="es">
<body>
  <h1>Ejemplo con JavaScript externo</h1>
  <button onclick="saludar()">Haz clic</button>

  <script src="script.js"></script>
</body>
</html>
```

Archivo JavaScript (`script.js`)

```javascript
function saludar() {
    alert("¡Hola desde un archivo externo!");
}
```


## 1.5.4. Uso de módulos ES6 (`type="module"`)

Archivo HTML (`index.html`)
```html
  <!DOCTYPE html>
  <html lang="es">
  <body>
      <h1>Ejemplo con módulos ES6</h1>

      <script type="module">
          import { sayHello } from './module.js';
          sayHello();
      </script>
  </body>
  </html>
```

Archivo JavaScript (`module.js`)

```javascript
export function sayHello() {
    console.log("¡Hola desde un módulo!");
}
```

## 1.7.2. Vídeos uso herramientas de desarrollo de Chrome

[En este vídeo se explica cómo trabajar con las herramientas de desarrllo de Chrome](https://www.youtube.com/embed/fxfeGzQDcS4)

[En este vídeo se explica cómo acceder a la consola de Javascript en Chrome](https://www.youtube.com/embed/hyo1JxdqDMg)

[Chrome Developer Tools - Tips para Desarrollo Web y Productividad](https://www.youtube.com/embed/BXN8oO4r3Qc)

[Sácale chispas a Chrome Developer Tools (DevTools)](https://www.youtube.com/embed/xBXYIs4-xJE)

[Chrome Developer Tools a fondo](https://www.youtube.com/embed/kHFZOBxbFDM)

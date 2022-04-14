# Resumen de apuntes:

### ¿Qué es react?

1. React es una biblioteca de código abierto diseñada para crear interfaces de usuario; es fácil de aprender, crea aplicaciones web dinámicas y tiene un buen desempeño

### ¿Qué es un componente?

separa intereses del maquetado y la lógica de archivos

Los componentes se dividen en **_funcional_** y **_clase_**
La funcional es básicamente una funcion de ES6 que retorna a un elemento React(JSX)
**EJEMPLO DE COMPONENTE FUNCIONAL**

```javascript
function saludo(props) {
  return <h1>Hola {props.name}</h1>;
}
```

**_EJEMPLO DE COMPONENTE CLASE_**

```javascript
class saludo extends React.Component {
  render() {
    return <h1>Hola {this.props.name}</h1>;
  }
}
```

---

| Componente funcional                       | Componente de clase                                            |
| :----------------------------------------- | :------------------------------------------------------------- |
| \* Debe retornar un elemento de React(JSX) | \* debe extender React.component                               |
| \* Debe Comenar con una letra mayúscula    | \* Debe tener el método render() para retornar un elemento JSX |
| \* Puede recibir valores si es necesario   | \* Puede recibir valores si es necesario                       |

### ¿Qué son los props?

Los props son argumentos que pueden recibir un componente de React. Estos generan componentes dentro de componentes que crean estruturas. Sin embargo los props solo puedenser envíados de padres a hijos, pero jamás de hijos a padres

### ¿Qué es un estado?

Es como javascript representa al conjunto de propiedades de un componente y sus valores actuales

### ¿Qué es un hook?

Función especial que permie trabajar con estados en componentes funcionales y otros estados de React, incluso los diferentes estados de la vida de un componente, el cual nos permite esribir código mucho más conciso y fácil de entender.

### ¿Qué es un Event Lisener?

Es una función de javascript que se ejecuta cuando ocurre un evento específico

### ¿Qué es JSX?

Es una extensión de React para la sintaxis de JavaScript. Nos permite escribir JavaScript como se verían los componentes usando una estructura similar al HTML.

```jsx
import React from "react";
import "../styles/styles.css";

function Contar({numClicks}){
    return <divClassName="contar">{numCLicks}</div>
}
```

### ¿ Qué es un elemento?

Es a representación visual de un elemento HTML, se le conoce como DOM. Se puede crear con el método _Reacct.createElement(tag)_. Se puede agregar cierto número de elementos dentro del return y se representan con etiquetas en letras **minúsculas** :heart:

### ¿Qué es un Componente?

Es un contenedor que puede configurarse con diferentes opciones como state, props, content, children, statics, stateless components, etc. Cuando define mutabilidad de estado, s le llama statefull. Se le declara _createReactClass_, ES6 class o como una función de JS.
Los componentes empiezan con la primera letra en **mayúscula**

### ¿Qué hace el root?

Es el elemento principal que va a componer toda la aplicación, dentro se pone el ID y es manejado por el ReactDOM

- **¿Qué hace el ReactDOM?**
  1. El React Dom es un paquete que facilita la interacción y actualización del DOM en aplicaciones de real, significa **D**ocument **O**bject **M**odel.
  2. Representa todos los elementos que conforman una página
  3. Va a representar toda la jerarquia de elementos en la app web

### ¿Cómo inserto atributos en mi JSX?

- se hace con un par de llaves {{}}, el primero nos permite insertar el js y el segundo nos permite definir el objeto

```jsx
<div style={{ color: "yellow" }}>Hola gente</div>
```

### ¿Cómo Renderizar componentes?

1. Se necesita un conteder para mostrar todo lo que vamos a poner. Por lo tanto se mete todo dentro del div con el id root

```jsx
<div id="root"></div>
```

2. Se crea el elemento que lleva por dentro un const, invocamos el _ReactDOM.render(elemento,document.getElementById("root"))_.

```jsx
const elemento = <h1>Hola gente</h1>;
ReactDOM.render(elemento, document.getElementById("root"));
```

**_OJO!!!_**: Usamos el ReactDOM para importar nuestro programa

```jsx
import ReactDOM from "react-dom";
```

- Todos nuestros elementos tambien tienen que estar dentro de una etiqueta de cierre, obligatorio usar la barra /
- También podemos meter javascript en todo lo que tenga llaves {}

```jsx
let carro= "carro"
<p>Me gusta el {carro}</p>
```

- Todas las expresiones de javascript son válidas

### ¿Cómo importo y exporto un archivo?

Existen dos tipos de exportación:

1. Nombrada
2. por defecto

#### por defecto

Un elemento de un archivo

```jsx
export default nombre;
```

### Nombre

```jsx
export funcion nombre(){/**/}

import {nombre} from
```
-----------------------


# RESUMEN DE CONTADOR DE CLICKS

### Sintaxis normal

```jsx
import React from "reacct";

function Boton(props) {
    return <button>{props.texto}</button>;
}
```
- Se toma el objeto texto que está dentro de texto, pero existe otra forma. Se puede invocar javascript usandolo en medio de laves



### Sintaxis de DES-ESTRUCTURACIÓN  
```jsx
import React from "react";

function boton({ texto }) {
    return <button>{texto}</button>;
}
```
- en vez de buscar el texto en props, solo se escribe entre llaves y listo :like:

# Curso de React freecodecamp español

- Conceptos basicos de react
- JavaScript XML(JSX).
- Estructura basica de una aplicacion de react

# ¿Qué es React?

Es una biblioteca de código abierto diseñada para crear interfaces de usuarios

# Ventajas de React

- Fácil de usar aprender.
- componentes reutilizables
- Crear aplicaciones web dinámicas (interactuan con el usuario)

- Buen desempeño

## Componente

Parte de la interfaz de usuario independiente y reusable.
Los componentes actúan como bloques que podemos ensamblaro.

Se pueden dividir en dos categorías principales:

- **funcionales** => son más fáciles de crear

- **_ clase _** => Se usaban en versions anteriores de react

### Componente funcional

- Es una funcion de JavaScript/ES6 que retorna un elemento de React(JSX)

```javascript
function saludo(props) {
  return <h1>¡hola, {props.nombre}!</h1>;
}
```

> props como parametro y abajo la propiedad nombre dentro del parametro, props es básicamente es un objeto, se usa . para acceder a las propiedades del componente

### Características del componente funcional

- Debe retornar un elemento de React(JSX).
- Debe comenzar con una letra mayúscula.
- Puede recibir valores si es necesario.

## props

Son argumentos que puede recibir un componente de react.
Estos generan componentes dentro de componentes que crean estructuras
![props](imagenes-react/props.png)

- los props solo pueden ser envíados de padres a hijos, pero jamás de hijo a padre

### Componente de clase

- Es una clase de JavaScript/ES6 que hereda de React.Component

```javascript
class saludo extends React.Component {
  render() {
    return <h1>¡hola, {this.props.nombre}!</h1>;
  }
}
```

- se usa la palabra class, con el nombre del componente y luego se extiende algo específico. dentro de esa clase hay que definir un método (render) y entre las llaves retornamos el componente JSX que vamos a mostrar en nuestra aplicación,

* render define lo que se va a mostrar en nuestra aplicación web y puede recibir valores si es neesario, estos se llaman props.
* Cuando se usa una clase se usa a _this_ se refiere a este componente individual en nuesrta aplicación.

## característias de un componente de clases

- debe extender React.Component
- Debe tener un método render() para retornar un elemento de JSX.
- Puede recibir valores si es necesario

### Estado

Representación en JavaScript del conjunto de propiedades de un componente y sus valores actuales

> EN este concepto, " propiedades" no se refiere a los props, sino a la información que se representa sobre el componente

# ¿Por qué componentes funcionales y componentes de clase?

---

Anteriormente, usábamos componentes de clase para poder trabajar con "estados" de nuestros componentes. Estos eran más poderosos que los funcionales.

En versiones anteriores no se podía hacer con componentes funcionales, hasta que llegaron los _hooks_, que agregan estados a los componentes funcionales

### Hook

Función especial que te permite trabajar con estados en componentes funcionales y otros estados en react, incluso los diferentes estados de la vida de un componente, el cual nos permite escribir código mucho más conciso y fácil de entender

## Event Listener

Función en JavaScript que es ejecutada cuando ocurre un evento específico

> También podemos referirnos a esta función como un "event handler"

# INTRODUCCIÓN A JSX

---

1. Es una extensión de React para la sintaxis de JavaScript
2. Nos permite describir en JavaScript cómo se verán los componentes usando una estructura similar a HTML

```jsx
import React from "react";
import "../hojas-de-estilo/contador.css";

function Contador({ numClics }) {
  return <div className="contador">{numClics}</div>;
}
```

> Practicamente se combina javascript con HTML

### Elementos

Unidades más pequeñas de React. Definen lo que se ve en la pantalla

| Elementos                                                                                           | Componentes                                                                                                                          |
| --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Es la reperesentación visual de un elemento HTML, esta representación se le conoce como virtual DOM | Es un contenedor que puede configurarse con diferentes opciones como state, props, context, children, statics y stateless components |
| se puede crear con el método _React.createElement(tag)_, o directamente con JSX                     | cuando define mutabilidad de estado (state changes), se le llama Statefull Component                                                 |
| se puede agrupar cierto número de React Elements dentro del método _return_                         | Se declara _createReactClass_, ES6 class o como una función JS.                                                                      |

```jsx
<div id="root"></div>
```

- root es el elemento principal que va a componer toda nuestra aplicación. todo se pone dentro del ID, manejado por react DOM

## ReactDOM

El ReactDOM es un paquete qeu facilita la interacción y actualización del DOM en aplicaciones React.
**_DOM_**: Documen Object Model

- Representación del navegador de todos los elementos que conforman una página o aplicación web.
- Va representando la jerarquía de los elementos en nuestra página o aplicación web

### ¿Cómo diferenciar un elemento de un componente?

básicamente por sus etiquetas, en JSX, los elementos HTML se representan con etiquetas en letras _minúsculas_

los componentes empiezan con la primera letra _mayúscula_.

---

### Atributos

Se pueden agregar atributos a los elementos en JSX para especificar ciertas características, Pero algunos atributos se escriben de forma distinta si los comparamos con el html, en especial el de class
**_Html_**

```html
<h1 class="titulo-azul"></h1>
```

```html
<label for="css">css</label>
```

```html
<style>
  .titulo-azul {
    color: blue;
    background-color: yellow;
  }
</style>
```

**_JSX_**

```jsx
<h1 className ="titulo-azul></h1>
```

```jsx
label htmlFor="css">css</label>
```

```jsx
const estiloDiv = {
    color: "blue"
    backgroundColor: "red"
    };
}
/*Asignamos el objeto */

<div style={estiloDiv}>Hola mundo</div>

```

---

**_otra alternativa..._** si queremos asignar un estilo específico en línea directamente al elemento JSX, lo hacemos cuando tenemos muy pocas propiedades

```jsx
<div style={{ color: "yellow" }}>hola,mundo </div>
```

En este caso usamos llaves dobles porque:

1. el primer par de llaves nos permite insertar Javascript.
2. el segundo par de llaves nos permite definir el objeto de Javascript

El atributo _style_ acepta un objeto JavaScript, con propiedades CSS escritas en camelCase

| diferencias | html  | jsx       |
| ----------- | ----- | --------- |
| class       | class | className |
| for         | for   | htmlFor   |
| style       | style | style     |

---

# Atributos reconocidos pro el DOM en react

```jsx
accept acceptCharset accessKey action allowFullScreen alt async autoComplete
autoFocus autoPlay capture cellPadding cellSpacing challenge charSet checked
cite classID className colSpan cols content contentEditable contextMenu controls
controlsList coords crossOrigin data dateTime default defer dir disabled
download draggable encType form formAction formEncType formMethod formNoValidate
formTarget frameBorder headers height hidden high href hrefLang htmlFor
httpEquiv icon id inputMode integrity is keyParams keyType kind label lang list
loop low manifest marginHeight marginWidth max maxLength media mediaGroup method
min minLook closely.
In the part of
without the Id Length multiple muted name noValidate nonce open optimum pattern
placeholder poster preload profile radioGroup readOnly rel required reversed
role rowSpan rows sandbox scope scoped scrolling seamless selected shape size
sizes span spellCheck src srcDoc srcLang srcSet start step style summary
tabIndex target title type useMap value width wmode wrap

```

---

### Estructura

Al igual que html los elementos pueden ser _anidados_ en JSX para crear estructuras más complejas

### Renderizar Componentes

Para mostrarlo es muy intuitivo:

```html
<div id="root"></div>
```

Para ejecutar la aplicación de react, lo hacemos por medio del html con un div con el id _root_. Será el contenedor principal de todos los elementos y componentes de la estructura que vamos a ir creando.

```jsx
const elemento = <h1>¡hola, mundo!</h1>;

ReactDOM.render(elemento, document.getElementById("root"));
```

- acá se crea el elemento y lo que lleva por dentro con un const
- lo invocamos con _ReactDOM.render(elemento, document.getElementById("root"));_
  el elemento renderizar que se va a mostrar y el contenedor ('root').

Podemos usar ReactDOM importandolo a nuestro programa

```javascript
import ReactDOM from "react-dom";
```

El paquete se instala automáticamente.

---

### Self-closing Tags

Existen elementos que no necesitan etiquetas de cierre ( se cierran automáticamente).

Es un elemento que solo posee una etiqueta de apertura ya que no contiene texto u otros elementos.

```jsx
<img src="logo.png" alt="Mi polla" />
```

en react es obligatorio usar la barra /

### JavaScript en JSX

Podemos incluir código de javascript, lo metemos entre llaves _{JS}_ esto nos ayudará a crear apps dinámicas

```javascript
let adjetivo = "Interesante";
```

```jsx
<p>React es {adjetivo}</p>
```

con las {} le decimos que se comporte como javascript.

- Puedes escribir cualquier expresión válida de javascript entre llaves y su valor será reemplazado

```jsx
<p>El resultado es: {2 + 2}</p>
```

Se puede llamar a un método y todo

```jsx
let nombre = "pollo";
<p> su nombre es: {nombre.toUpperCase()}</p>;
```

---

# Crear estructura inicial

```
npx create-react-app my-app
```

escribir esto en la terminal en la carpeta que vayas a usar,

### npm comandos

[npm cheatsheet](https://devhints.io/npm)

para ejecutar

```
cd mi-app
npm start
```

# primer proyecto: TESTIMONIOS FREECODECAMP

### Aquí pondré solo notas que me parecen impresionantes

- Es importante importar y exportar archivos

En react existen dos tipos de exportación, exportación _nombrada_ y exportación por _defecto_

| defaul                    | nombrada                                       |
| ------------------------- | ---------------------------------------------- |
| Un elemento de un archivo | varíos elementos del mismo archivo             |
| export default nombre     | export function nombre(){} / import { nombre } |

Con las nombradas se pueden exportar varios elementos con llaves. Con defecto solo se puede importar un elemento del archivo

---

# Usando props:

El propósito de react es crear componentes rehusables.

```jsx
function Testimonio(props)
```

- Los props se definen dentro del parámetro del componente. De esta manera lo usamos para recibir valores y usarlos en nuestro componente.

**_Para invocarlo sería así_**:

```jsx
{
  props.nombre;
}
```

### Props a Componente

Hay que crear lo que componen los props

```jsx
<Testimonio nombre="" pais="" imagen="" cargo="" empresa="" testimonio="" />
```

### Plantillas literales

usamos comillas invertidas para insertar código de javascript denro de la cadena de caracteres y dentro meter el ${}. Dentro de las llaves se escribe el código de javascript

```jsx
        src={require(`../imagenes/testimonio-${props.imagen}.png`)}
```

### Retos

1. Lograr que el texto aparezca en negrita y varía de posición
2. el valor de alt es fijo,Tienen que ser varias
3. tiene que ser responsivo

---

# Proyecto de contador de clicks

Normalmente la sintaxis sería algo así:

```jsx
import React from "react";

function Boton(props) {
  return <button>{props.texto}</button>;
}
```

### Sintaxis de des-estructuración

Es que se toma el objeto y en lugar de recibirlo, se escribe un par de llaves y dentro se escriben directamente las propiedades que se están pasando. Haciendo esto no se hace el props.texto.
De esta forma se usa como una variable y un parámetro que recibe la función

```jsx
import React from "react";

function Boton({ texto }) {
  return <button>{texto}</button>;
}
```

### Operador ternario y Event Listener

Es un operador básico de javascript, que se rodea con llaves.
Lo sorprendente es que se pueden usar estos operadores como si fueran clases:

```jsx
import React from "react";

function Boton({ texto, esBotonDeClic,manejarClic }) {
  return <button className={esBotonDeClic ? 'boton-clic' : 'boton-reiniciar'} onCLick={manejarClic}>{texto}</button>;
```

1. El event listener son una serie de palabras claves que hacen el código reaccionar a un evento (raton, teclado, etc)
2. También se usa como parametro y en la forma de arriba hacemos que; al estar _onClick_ dentro del _{texto}_ el programa reaccione.

**_En total son tres props_**: El texto, el boton y el evento.
la función "manejar clic" viene del componente que renderice o cree al botón. Se actualiza el estado del contador

### Asignar funciones

Simplemente creamos la función como un JavaScript normal:

```jsx
// App.js
import Boton from "./Boton";
import "./App.css";
import freeCodeCampLogo from "./freeCodeCamp.png";
function App() {
  const manejarClic = () => {
    console.log("Hola");
  };
}
const reiniciarContador = () => {
  console.log("Reiniciar Contador");
};
return (
  <div className="App">
  <div className="freecodecamp-logo-contenedor">
  img =className="freecodecamp-logo" src={require(`../imagenes/freecodecamp-logo.png`)} alt="freecodecamp logo" />
  <div className="contador-principal">
  <Boton texto="Clic" esBotonDeClic={true} manejarClic={manejarClic}/>
  <Boton texto="reiniciar" esBotonclic={false} manejarClic={reiniciarContador}>
)
```

---

### Hooks

Guarda un estado de un componente funcional. tenemos que importar el useStates desde react.

```jsx
import { useState } from "react";
const [valor, función_que_actualiza] = estado_inicial(0);

const manejoClic = () => {
  función_que_actualiza(valor + 1);
};
}
```

---

### Proyecto calculadora

#### Atributos

Para la clase se usa classsname.

Si nos acordamos de las comillas invertidas en javascript: nos sirven para crear las plantillas literales (template literals). Que son llaves con cierto código de javascript para definir el resultado

```jsx
<div
  className={`boton-contenedor ${esOperador(props.children) ? "operador" : ""}`}
>
  {props.children}
</div>
```

- Aveces necesitamos que la clase tenga un operador dentro. A este solo se le vamos a agregar si children representa un operado para eso usamos el _${esOperador()}r_

### Notas:

-Metodo trim() permite remover espacios a principio o al final de una cadena de carácteres o una plantilla. y trimEnd() solo remueve espacios al final.

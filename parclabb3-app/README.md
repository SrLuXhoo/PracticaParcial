# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

###
React: Una biblioteca Javascript para construir interfaces de usuario. El nombre de React viene del adjetivo reactive que nos da a entender que lo que buscamos
son interfaces de usuario reactivas al input del mismo.

Porq? Como desarrolladores de software, siempre vamos a buscar agilizar nuestros procesos para conseguir escribir mejor código en menos tiempo.

spa: single page application son apps webs q traen del sv una sola pag, que se encargará de realizar la totalidad del manejo del sistema web front-end

map() Esta función nos permite realizar cambios sobre cada uno de los elementos en un arreglo. Retorna un nuevo arreglo con la forma deseada.

const numbers = [1,2,3];
const doubleNumbers = numbers.map((num) => {
    return num * 2;
});
console.log(doubleNumbers);

filter() Esta función nos permite crear un sub-arreglo que contenga todos los elementos que cumplen cierta condición. También nos devuelve un arreglo.

const numbers = [1,2,3];
const filteredNumbers = numbers.filter((num) => {
    return num >= 2;
});
console.log(filteredNumbers);

reduce() Es una función que justamente nos permite reducir un arreglo de valores a un solo valor (útilpara realizar sumatorias, o promedios, por ejemplo). Nos devuelve un valor.

const numbers = [1,2,3];
const sumNumbers = numbers.reduce((numb, el) => {
    return numb + el;
}, 0);
console.log(sumNumbers);

Las librerias de react nos permite construir interfaces de usuario complejos, interactivas y reactivas al usuario.
React utiliza lo denominado lógica de componentes. Todas las interfaces de usuario, al final del día, están
compuestas por componentes.

¿Qué son los componentes? Son bloques de código que funcionan como unidad principal de trabajo en la librería React. 
Se trabaja con componentes por razones principales: Reusabilidad, Separación de funcionalidades

props: es el objeto que viene incluido en todo componente de React, puede poseer elnombre que queramos pero en general se lo llama props.
De esta manera, el componente hijo puede acceder a atributos que posee el componente padre.

¿Que retorna useState? Retorna un arreglo con dos valores, el primer valor es nuestra
nueva variable ya inicializada y el segundo es una función que nos servirá para setear el
valor de dicha variable. Para obtener ambios se puede usar array destructuring.

const [newTitle, setNewTitle] = useState(title);


###

import './App.css';
import Calculadora from './components/Calculadora';
import Books from './components/ejerciciolibro/Books';
// import PracticaParcial from './components/PracticaParcial';
// import { Button } from 'reactstrap';
// import NavBar from './components/NavBar';
// import PracticaUseEffect from './components/PracticaUseEffect';

function App() {

  const books = [ { title: "El Quijote de la Mancha", rating: 7.9 }, 
    { title: "El señor de los anillos", rating: 8.1 }, 
    { title: "Dune", rating: 7.8 }, 
    { title: "Martín Fierro", rating: 9.2 } ]

  return (
    <div>
      {/* Uso del boton de ReactBost */}
    {/* <Button color="danger">Danger!</Button>; */}
    {/* <NavBar/> */}
     <Calculadora/> 
      
    <Books books={books}/> 

    </div>
  );
}

export default App;

### book.jsx

import React from 'react'


const Book = ({ title, rating }) => {
    return (
        <div>
            <h1>{title}</h1>
            <p style={{ fontWeight: rating > 9 && "bold" }}>{rating}</p>
        </div>
    )
}

export default Book



### books.jsx
import React from 'react'
import Book from 'Book'

const Books = ({ books }) => {

    const filteredArray = books.filter((movie) => (Number(movie.rating) > 8.0))

    return (
        <div>
            {
                filteredArray.map((books) => {
                    return <Book title={books.title} rating={books.rating} />
                }
                )
            }

        </div>
    )
}

export default Books

### calculadora.js

import React, { useState } from 'react'

const Calculadora = () => {

    const [numero1, setNumero1] = useState(0)
    const [numero2, setNumero2] = useState(0)
    const [suma, setSuma] = useState(0)

    const seteoDeNum1 = (e) => {
        setNumero1(e.target.value)
    }

    const seteoDeNum2 = (e) => {
        setNumero2(e.target.value)
    }

    const sumaOnClick = () => {
        setSuma(Number(numero1) + Number(numero2))
    }


  return (
    <div>
        <label htmlFor="">NUMERO 1</label>
        <input type="number" onChange={seteoDeNum1}/>
        <label htmlFor="">NUMERO 2</label>
        <input type="number" onChange={seteoDeNum2}/> 
        <button onClick={sumaOnClick}> Sumar </button>
        <h1>{suma}</h1>
        <hr />
    </div>
  )
}

export default Calculadora
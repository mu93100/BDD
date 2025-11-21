R E A C T

single page application

react : Framework front / on doit rajouter un doss API pour avoir du back / fonctionne avec les components

synfony : Framework front et back/ fonctionne avec les components





---

index.html

<!doctype html>

<html lang="en"> --> on met fr

  <head>

    <meta charset="UTF-8" />

    <link rel="icon" type="image/svg+xml" href="/vite.svg" />

    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <title>react</title>

  </head>

  <body>

    <div id="root"></div> --> toutes les pages

    <script type="module" src="/src/main.jsx"></script>

  </body>

</html>----------------------





on travaille ds doss src (source)

chaque page de src est une Fo qui retourne qque chose



---

---

> app.jsx



import { useState } from 'react'

import reactLogo from './assets/react.svg'

import viteLogo from '/vite.svg'

import './App.css'



function App() {

  const \[count, setCount] = useState(0)



  return (

    <>

      <div>

        <a href="https://vite.dev" target="\\\_blank">

          <img src={viteLogo} className="logo" alt="Vite logo" />

        </a>

        <a href="https://react.dev" target="\\\_blank">

          <img src={reactLogo} className="logo react" alt="React logo" />

        </a>

      </div>

      <h1>Vite + React</h1>

      <div className="card">

        <button onClick={() => setCount((count) => count + 1)}>

          count is {count}

        </button>

        <p>

          Edit <code>src/App.jsx</code> and save to test HMR

        </p>

      </div>

      <p className="read-the-docs">

        Click on the Vite and React logos to learn more

      </p>

    </>

  ) --> ce n'est pas du html c'est du JS (page d'intro qu'on efface)

}



main.jsx fichier principal

import { StrictMode } from 'react'

import { createRoot } from 'react-dom/client'

import './index.css'

import App from './App.jsx'



createRoot(document.getElementById('root')).render(

  <StrictMode>

    <App /> --> on appelle la Fo app

  </StrictMode>,

)



export default App

---

on crée un doss components ds src (éléments de la page : buttons, header ETC)

> on crée un doss DroiteApp.jsx

on ecrit : import React from "react";

on ecrit la Fo

function DroiteApp() {

    return(

        <></>

    )

}



on ecrit export default DroiteApp pour utiliser la Fo ailleurs

et on met



….

on doit installer des bibliotheques pour faire tout : router, carrousel, cookie, map, pour récupérer les api ETC  (AVEC npm)

> router

> ds term > npm install react-router-dom

> ça s'enregistre ds Node\\\_nodule (DOSS A NE PAS TOUCHER)

on importe des balises on transforme App.jsx en rooter



header

soit on se fait ttes les pages :::

export default function Header() {

    return(

    <nav>

    <Link to="/">A C C U E I L</Link>

    <Link to="/apropos">A P R O P O S</Link>

    </nav>

    )

}



SOIT ON FAIT MIEUX : sous forme de tableau :::

export default function Header() {

    const header = \[

        {

            slug: "/",

            label: "A C C U E I L"

        },

        {

            slug: "/apropos",

            label: "A P R O P O S"

        },

        {

            slug: "/categorie",

            label: "C A T",

            children: \[

                {

                    slug: "/categorie/film",

                    page: "Film"

                },

                {

                    slug: "/categorie/documentaire",

                    page: "Documentaire"

                },

            ]

        }

    ]

---

pour importer un fichier quiu est dans un autre doss : il faut ressortir du doss le nb de fois nécessaire avec ../

ex pour doss react dans fichier button.jsx (dans doss common dans doss components dans doss assets, ds doss src) import de button.css ds dosscss ds doss assets ds doss src :::

import '../../assets/css/Button.css'



dossier FACUNDO

https://github.com/mu93100/react.git


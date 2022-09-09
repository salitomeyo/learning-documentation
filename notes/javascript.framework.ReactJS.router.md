---
id: 3mcxf7vvgtjdo1ic4c4y5gk
title: router
desc: ''
updated: 1662728929574
created: 1662642893620
---

Para crear routers necesitamos instalar una dependencia de react, hay diferentes opciones pero usualmente la mas util es
[react-router-dom](https://v5.reactrouter.com/web/guides/quick-start)

##  Instalacion

Basta con utilizar la instalacion del paquete de npm

```bash
npm install react-router-dom
```

## Modo de uso

Una vez instalado debemos crear nuestro componente router, la unica funcionalidad de este componente es encargarse del mapeo de las paginas conforme cambia el path 

En primera instancia dentro del componente debemos importar

```javascript
import { Routes, Route } from 'react-router-dom';
```

>Nota: Esta es solo una de las posibles opciones, para ver otras posibles formas de lograr este mismo objetivo referirse a la documentacion oficial

Una vez importado nos dispondremos a hacer el componente que consta de un componente padre `Routes` que tiene dentro de este cada una de las diferentes pantallas que van a componer nuestra aplicacion en componentes `Route`

```javascript
export const AppRouter = () => {
    return(
        <>
            <Routes>
                <Route path="/" element={<HomePage/>} />
                <Route path="shop" element={<ShopPage/>} />
                <Route path="login" element={<LoginPage/>} />
            </Routes>
        </>
    )
}
```

Cabe destacar que en este return podemos agregar todos los componentes que queremos que existan en comun entre todas las paginas, por ejemplo es muy comun ver el Navbar y el footer, ya que queremos que estos componentes se muestren independientemente de la pantalla actual, por lo que **su renderizado no va a depender de la ruta sino que es fijo**

```javascript
export const AppRouter = () => {
    return(
        <>
            <Navbar />
            <Routes>
                ...
            </Routes>
            <Footer />
        </>
    )
}
```

Con esto ya tenemos nuestro router finalizado, si la aplicacion contiene un unico router basta con importarlo en el archivo principal

## Links 

Ahora debemos realizar los links que son los que se encargaran de cambiar las rutas para permitirnos cambiar de pantalla (estos links usualmente se concentran en el navbar y footer pero esto no es una regla, en realidad pueden estar en cualquier lugar), para ello debemos importar en cada una de las pantallas o componentes que cambien la ruta de la aplicacion

```javascript
import { Link, NavLink } from 'react-router-dom';
```

>Nota: aun no comprendo la diferencia entre Link y NavLink pero en un primer vistazo podemos utilizar cualquiera de los dos

Una vez importado basta con utilizarlo para cambiar las rutas a las mismos path que habiamos definido en el router, estos **pueden ser usados individualmente o rodeando cualquier otro elemento** como una imagen o un boton 

```html
<Link
    to="/"
>
    <img src="./assets/logo.png>
</Link>
<NavLink 
    to="/shop"
>
    Shop
</NavLink>
```

Con esto hemos finalizado el router basico 100% funcional


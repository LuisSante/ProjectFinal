# Proyecto Final
 ## Curso: Ingeniería de Software
 # Integrantes
 - LUIS FELIPE SANTE TAIPE
 - LUIS ANGEL MOROCO RAMOS
 - MARYORI LIZETH HILARES ANGELO
 - CKAROLL DARLENE CHURA NAVARRO
 - EDUARDO FELIPE VALDIVIA QUISPE
# GitHub Profile README Generator
 <p align="center">
    <img src="/img/github.gif">
  </p>

GitHub Profile README Generator es un programa que proporciona una manera fácil de crear un archivo Léame de perfil de GitHub con los últimos complementos, como el recuento de visitantes, las estadísticas de github, etc. Lo único que debemos hacer es completar los detalles como Nombre, Lema, Nombre de usuario de las plataformas de desarrollo, Trabajo actual, Portafolio, Blog, etc. con una interfaz de usuario mínima.

GitHub Profile README Generator es un programa con código libre,diseñado por rahuldkjain.Usa lenguaje JavaScript y CSS para la interfaz.
# Herramientas
 - GitHub: Usamos este tipo de herramienta para crear un repositorio donde alojar nuestro proyecto.
 - JMeter
 - Trello
 - SonarQube: Es una plataforma para evaluar código fuente. Es software libre y usa diversas herramientas de análisis estático de código fuente como Checkstyle, PMD o FindBugs para obtener métricas que pueden ayudar a mejorar la calidad del código de un programa.​
 - Sonar-scanner
 - Json
 - JUnit: Es un conjunto de bibliotecas son utilizadas en programación para hacer pruebas unitarias de aplicaciones Java.JUnit es el estándar de facto para las pruebas unitarias de una aplicación Java. Aunque, es popular para las pruebas unitarias, tiene soporte completo y provisión para pruebas de instrumentación también.
 - OWASP ZAP
 - Selenium: Es un entorno de pruebas de software para aplicaciones basadas en la web. Selenium provee una herramienta de grabar/reproducir para crear pruebas sin usar un lenguaje de scripting para pruebas.
 - React
 - NodeJS
 - Jest
 
# Analisis Estatico

## Analisis SonarQube
<p align="center">
    <img src="/img/sonnar_.png">
  </p>
 <p align="center">
    <img src="/img/sonar.png">
  </p>
  
## Refacotoring Code

### Bad smells in code
> src/pages/index.jsx
```javascript
onKeyDown={(e) => e.onkey === '13'

// new
onKeyDown={(e) => e.key === 'Enter'
```

### Smells
> src/pages/index.jsx
```javascript
      </>
    );
  }
  return '';

// new 
      </>
    );
  }
  else {
      return ; 
  }
```

### Smells
> src/pages/index.jsx
```javascript
// no es fácil leer
return (
      <>
        {`<h1 align="center">${`${prefix} ${title}`}</h1>`}
        <br />
      </>)

// new
let x= `${prefix} ${title}`;
return (
      <>
        {`<h1 align="center">${x}</h1>`}
        <br />
      </>)
```

### Smells
> src/pages/index.jsx
```javascript

... </div>
  ) : (
    ''
  );

// new
    </div>
  ) : (
    null
  );
```

### Smells Rename
> src/components/constants/page-links.js
```javascript
// page-links.js

const links = {
  home: '/',
  about: '/about',
  addons: '/addons',
  support: '/support',
};
export default links;

// si solo exporta una clase, el doc debe llamarse igual

// links.js
```

### Smells Separate Functions
> src/components/index.jsx
```javascript
...
{copyObj.isCopied === true ? <CheckIcon size={24} /> : <CopyIcon size={24} />}

// Debemos separar la función 

const isCopied = (copyObj) => {
  return copyObj.isCopied === true ? <CheckIcon size={24} /> : <CopyIcon size={24} />;
};
```

### Smells Separate Functions
> src/components/index.jsx
```javascript
  const queryString = Object.entries(params)
    .map(([key, value]) => `${key}=${value}`)
    .join('&');
  return queryString;

  // new 

  return Object.entries(params)
    .map(([key, value]) => `${key}=${value}`)
    .join('&');

```
## Casos de prueba

<p align="center">
    <img src="/img/cp.jpeg">
  </p>
  
# Construccion Automatica
***
Como estamos trabajando con NodeJS y React, podemos usar el comando “npm”, veremos algunos comandos. Si ponemos “npm --help”, y nos saldrá los comandos que pertenece a NodeJS.
<p align="center">
    <img src="/img/ca.png">
  </p>
Pero ¿Cómo esto interviene y ayuda en la construcción automática?:


* [npm init] : Este comando sirve para crear el archivo package.json.
* [npm install] : Leer el archivo del package.json para instalar todas las dependencias que encuentre.
* [npm install <package>] : Descarga el paquete y lo mete en la carpeta node modules.
* [npm test]: Esto ejecuta el script de "test" de un paquete, si se proporcionó uno. 

## Pruebas de Seguridad
Para las pruebas de seguridad, se ataco desde OWASP ZAP obteniendo asi las siguientes alertas:
<p align="center">
    <img src="/img/owaspAl1.png">  
    <img src="/img/owaspAl.png">
    <img src="/img/owasp.png">  
  </p>
  
## Gestión de Issues
Para la gestión de issues se uso la herramienta Trello debido a que todos los integrantes ya habian usado esta herramienta en anteriores proyectos.
<p align="center">
    <img src="/img/trello.png">  
  </p>

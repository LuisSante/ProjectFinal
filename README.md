# ProjectFinal
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

# ProjectFinal

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


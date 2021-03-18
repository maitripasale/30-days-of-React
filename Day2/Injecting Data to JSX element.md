### Injecting a number to a JSX Element

```js
const num1 = 8
const num2 = 10

const result = (
  <p>
    {num1} + {num2} = {num1 + num2}
  </p>
)

const yearBorn = 2000
const currentYear = new Date().getFullYear()
const age = currentYear - yearBorn
const personAge = <p> {age}</p>
```


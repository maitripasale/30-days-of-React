## JSX

JSX stands for JavaScript XML. JSX allows us to write HTML elements with JavaScript code. An HTML element has an opening and closing tags, content, and attribute in the opening tag. However, some HTML elements may not have content and a closing tag - they are self closing elements. To create HTML elements in React we do not use the _createElement()_ instead we just use JSX elements. Therefore, JSX makes it easier to write and add HTML elements in React. JSX will be converted to JavaScript on browser using a transpiler - [babel.js](https://babeljs.io/). Babel is a library which transpiles JSX to pure JavaScript and latest JavaScript to older version. See the JSX code below.

```js
// JSX syntax

const jsxElement = <h1>Hello Techies!</h1>
const data = <h2>March 9, 2021</h2>
```
The above code seems like JavaScript and HTML, but it is not completely JavaScript and HTML. It is a mix of JavaScript and an HTML elements. JSX can allow us to use HTML in JavaScript. The HTML element in the JSX above is _h1_ and _h2_.

## JSX Element

JSX element could be a single HTML element or many HTML elements wrapped in a parent HTML element.

This JSX element has only one HTML element which is _h1_.

```js
const jsxElement = <h1>I am a JSX element</h1> // JS with HTML
```

```js
const title = <h2>Getting Started React</h2>
```
Every HTML element should be wrapped by an outer HTML element to create a valid JSX element.

```js
const header = (
  <header>
    <h1>Good to see you here!</h1>
    <h2>Getting Started React</h2>
    <h3>JavaScript Library</h3>
  </header>
)
```
The _header_ element is a parent element for all the inner HTML elements and JSX must be wrapped by an outer parent element. Without the _header_ HTML element or other parent HTML element the above JSX is invalid.

## Rendering a JSX Element

To render a JSX element to HTML document, first create an index HTML. The index.html is the only HTML file you will have in any React Application. We can get started with React in two ways - either by using CDN or create-react-app.

```html
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div id="root"></div>

    <script>
        // code 
    </script>
  </body>
</html>
```

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
  </head>

  <body>
    <div id="root"></div>
    <script type="text/babel">
      class App extends React.Component{
            render() {
                return (
                    <header>
                        <h1>Welcome to React.</h1>
                        <h2>JavaScript Library</h2>
                        <h4>March 9, 2021</h4>
                    </header>
                )    

            }
        }
        ReactDOM.render(<App />, document.getElementById('root'));
    </script>
  </body>
</html>
```
![Render](/images/rendering_jsx.PNG)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="./style.css">
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
  </head>

  <body>
    <div class="root"></div>
    <script type="text/babel">
    // To get the root element from the HTML document
      const rootElement = document.querySelector('.root')

      const header = (
        <header>
          <div className='header-wrap'>
          <h1>Welcome to React.</h1>
          <h2>JavaScript Library</h2>
          <h4>March 9, 2021</h4>
          </div>
        </header>
      )

      const main = (
          <main>
          <div className='main-wrap'>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit,magna aliqua.
          </p>
          <p>Prerequisite to get started{' '}
            <strong>
              <em>react.js</em>
            </strong>

             :
          </p>
          <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
            <li>JQuery</li>
            <li>ES6</li>
          </ul>
          </div>
          </main>
    
      )
      
     const footer = (
        <footer>
          <div className='footer-wrapper'>
          <p>Copyright 2021</p>
          </div>
        </footer>
      )

      const app = (
        <div className='app'>
          {header}
          {main}
          {footer}
        </div>
      )
      ReactDOM.render(app, rootElement)
    </script>
  </body>
</html>
```
![Style](/images/styling.PNG)







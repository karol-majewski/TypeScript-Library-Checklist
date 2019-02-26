# FAQ

## Should I transpile my code to ES5 in 2019?

Excellent question! The best way out of this problem is to simultaneously ship two versions of your
project: a CommonJS module (legacy) and a modern ECMAScript one. That's what
[microbundle](https://github.com/developit/microbundle) can do for you out of the box.

Read more:
[Deploying ES2015+ Code in Production Today](https://philipwalton.com/articles/deploying-es2015-code-in-production-today/).

## My library is a React component. Is there anything I need to know?

React components are just JavaScript functions (or classes), so there isn't anything special about
them. However, if your component is a
[Higher-Order Component](https://reactjs.org/docs/higher-order-components.html), you can make the
developer experience better by doing the following:

- Export the interface describing the props supplied by your HOC
- Export the interface telling your user what props must be supplied
- If your HOC accepts a React component and returns a React component, the props accepted by the
  created component should not include the props already supplied by your HOC
- Expose the wrapped component by using a static property or
  [`forwardRef`](https://reactjs.org/docs/forwarding-refs.html)

## I don't want to rewrite my library. I just want to add type definitions to it.

It's best to submit your type definitions to
[DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped).

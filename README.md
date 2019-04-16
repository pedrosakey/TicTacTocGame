# Tic-Tac-Toe Game
![version](https://img.shields.io/badge/React-blue.svg?maxAge=2592000)


This is an introduction to React. This is a tutorial you can find it. I add some annotations a modifications

![The game](https://drive.google.com/uc?id=1Dybo0BfqkwhY7MgYT2oMW6ZCOTjhUyFx)

### Create React App

```
npx create-react-app my-app
cd my-app
npm start
```

## Setup for the tutorial

Remove files inside the src folder. Add `index.js` and `index.css`. Add these three lines to `index.js`.

```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
```

## Overview

### The game

> Tic-tac-toe (American English), noughts and crosses (British English), or Xs and Os is a paper-and-pencil game for two players, X and O, who take turns marking the spaces in a 3×3 grid. The player who succeeds in placing three of their marks in a horizontal, vertical, or diagonal row wins the game.

### Components

![Components](https://drive.google.com/uc?id=1E-7D6KbsmrDUj8aAeR13DDHcfawsF7Qe)

### Passing Data Through Props
Commnication between parent (Board) and child (Square)
- Pass a prop  (Board) `return <Square value={i} />;`
- Read prop (Square) `{this.props.value}`

### Making an Interactive component

Fill with X when we click in the component 
```
<button className="square" onClick={function() { alert('click'); }}>
        {this.props.value}
```

We want the Square component to “remember” that it got clicked, and fill it with an “X” mark. To “remember” things, components use **state**.

- Add constructor

```
 constructor(props){
        super(props);
        this.state = {
            value:null,
        };
    }
```

- Change Square’s render method to display the current state’s value
    `{this.state.value}`

### Developers Tools
The React Devtools extension for Chrome and Firefox lets you inspect a React component tree with your browser’s developer tools.

### Completing the game

#### Lifting State Up

> To collect data from multiple children, or to have two child components communicate with each other, you need to declare the shared state in their parent component instead. The parent component can pass the state back down to the children by using props; this keeps the child components in sync with each other and with the parent component.

The state of a child component is inside the parent component.

> 1. The onClick prop on the built-in DOM button component tells React to set up a click event listener.
> 2. When the button is clicked, React will call the onClick event handler that is defined in Square’s render() method.
> 3. This event handler calls this.props.onClick(). The Square’s onClick prop was specified by the Board.
> 4. Since the Board passed onClick={() => this.handleClick(i)} to Square, the Square calls this.handleClick(i) when clicked.

#### Why Immutability is important

#### Function Components

Function components are a simpler way to write components that only contain a render method.

#### Taking Turns

#### Calulating winner

## Improvements and Modifications 

## References

- Tic-tac-toe on [Wikipedia](https://en.wikipedia.org/wiki/Tic-tac-toe)
- [React beginner tutorial](https://reactjs.org/tutorial/tutorial.html#declaring-a-winner)

## License
MIT
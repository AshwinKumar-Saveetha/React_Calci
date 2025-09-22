# Ex04 Simple Calculator - React Project
## Date:

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
### App.jsx
```
import { useState } from 'react';
import './App.css';

function App() {
  const [display, setDisplay] = useState('0');

  const handleClick = (value) => {
    if (display === '0' || display === 'Error') {
      setDisplay(value);
    } else {
      setDisplay(display + value);
    }
  };

  const handleClear = () => {
    setDisplay('0');
  };

  const handleBackspace = () => {
    if (display.length > 1) {
      setDisplay(display.slice(0, -1));
    } else {
      setDisplay('0');
    }
  };

  const calculate = () => {
    try {
      const expression = display.replace(/×/g, '*').replace(/÷/g, '/');
      const result = new Function('return ' + expression)().toString();
      setDisplay(result);
    } catch (error) {
      setDisplay('Error');
    }
  };

  return (
    <div className="app-container">
      <div className="calculator">
        <div className="display">{display}</div>
        <div className="buttons">
          <button onClick={handleClear} className="button special">AC</button>
          <button onClick={handleBackspace} className="button special">C</button>
          <button onClick={() => handleClick('%')} className="button special">%</button>
          <button onClick={() => handleClick('÷')} className="button operator">÷</button>

          <button onClick={() => handleClick('7')} className="button">7</button>
          <button onClick={() => handleClick('8')} className="button">8</button>
          <button onClick={() => handleClick('9')} className="button">9</button>
          <button onClick={() => handleClick('×')} className="button operator">×</button>

          <button onClick={() => handleClick('4')} className="button">4</button>
          <button onClick={() => handleClick('5')} className="button">5</button>
          <button onClick={() => handleClick('6')} className="button">6</button>
          <button onClick={() => handleClick('-')} className="button operator">-</button>

          <button onClick={() => handleClick('1')} className="button">1</button>
          <button onClick={() => handleClick('2')} className="button">2</button>
          <button onClick={() => handleClick('3')} className="button">3</button>
          <button onClick={() => handleClick('+')} className="button operator">+</button>

          <button onClick={() => handleClick('0')} className="button zero">0</button>
          <button onClick={() => handleClick('.')} className="button">.</button>
          <button onClick={calculate} className="button operator">=</button>
        </div>
      </div>
    </div>
  );
}

export default App;
```

### App.css:
```
/* General App Styling */
.app-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  width: 100%;
  background-color: #e8f5e9;
  font-family: Arial, sans-serif;
}

/* Calculator Body */
.calculator {
  width: 320px;
  border-radius: 12px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  background-color: #ffffff;
  overflow: hidden;
}

/* Display Screen */
.display {
  background-color: #222;
  color: #fff;
  font-size: 2.5rem;
  padding: 25px 20px;
  text-align: right;
  word-wrap: break-word;
  min-height: 3.5rem;
}

/* Button Grid */
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}

/* General Button Styling */
.button {
  padding: 20px;
  font-size: 1.4rem;
  border: 1px solid #ddd;
  border-top: none;
  border-left: none;
  cursor: pointer;
  background-color: #f9f9f9;
  transition: background-color 0.2s;
}

.button:active {
  background-color: #e0e0e0;
}

/* Specific Button Colors */
.operator {
  background-color: #ff9500;
  color: white;
}

.operator:active {
  background-color: #e08500;
}

.special {
  background-color: #d4d4d2;
}

.special:active {
  background-color: #bcbcbc;
}

.zero {
  grid-column: span 2;
}
```

## OUTPUT

<img width="1918" height="969" alt="image" src="https://github.com/user-attachments/assets/8a7eef33-6a02-4265-91a2-5c040c183cac" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.

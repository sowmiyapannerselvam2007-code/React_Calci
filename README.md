# Ex04 Simple Calculator - React Project
## Date:14-03-2026
## Name : P SOWMIYA
## Reg No :212225240152

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

APP.JS
```
import React, { useState } from "react";
import "./App.css";

function App() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const clearDisplay = () => {
    setInput("");
  };

  const calculate = () => {
    try {
      setInput(eval(input).toString());
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="app">
      <div className="calculator">
        <h1>Simple Calculator</h1>

        <input
          type="text"
          value={input}
          readOnly
          className="display"
        />

        <div className="buttons">
          <button onClick={clearDisplay} className="clear">
            C
          </button>
          <button onClick={() => handleClick("/")}>÷</button>
          <button onClick={() => handleClick("*")}>×</button>
          <button onClick={() => handleClick("-")}>−</button>

          <button onClick={() => handleClick("7")}>7</button>
          <button onClick={() => handleClick("8")}>8</button>
          <button onClick={() => handleClick("9")}>9</button>
          <button onClick={() => handleClick("+")} className="operator">
            +
          </button>

          <button onClick={() => handleClick("4")}>4</button>
          <button onClick={() => handleClick("5")}>5</button>
          <button onClick={() => handleClick("6")}>6</button>
          <button onClick={() => handleClick(".")}>.</button>

          <button onClick={() => handleClick("1")}>1</button>
          <button onClick={() => handleClick("2")}>2</button>
          <button onClick={() => handleClick("3")}>3</button>
          <button onClick={calculate} className="equal">
            =
          </button>

          <button
            onClick={() => handleClick("0")}
            className="zero"
          >
            0
          </button>
        </div>

        <footer>
          <p>Name: P SOWMIYA</p>
          <p>Register No: 212225240152</p>
        </footer>
      </div>
    </div>
  );
}

export default App;
```

APP.CSS
```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Poppins", Arial, sans-serif;
}

.app {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 30px;
  background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
}

/* Calculator Card */
.calculator {
  width: 380px;
  padding: 30px;
  border-radius: 30px;
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  box-shadow:
    0 25px 60px rgba(0, 0, 0, 0.45),
    inset 0 1px 1px rgba(255, 255, 255, 0.2);
}

/* Heading */
h1 {
  text-align: center;
  color: white;
  font-size: 28px;
  margin-bottom: 25px;
  letter-spacing: 1px;
}

/* Display */
.display {
  width: 100%;
  height: 80px;
  border: none;
  outline: none;
  border-radius: 18px;
  padding: 15px 20px;
  margin-bottom: 25px;

  background: rgba(0, 0, 0, 0.35);
  color: white;

  font-size: 32px;
  font-weight: bold;
  text-align: right;

  box-shadow:
    inset 0 5px 15px rgba(0, 0, 0, 0.35),
    0 5px 15px rgba(0, 0, 0, 0.15);
}

/* Buttons Layout */
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

/* All Buttons */
button {
  height: 65px;
  border: none;
  border-radius: 18px;

  font-size: 22px;
  font-weight: bold;

  color: white;
  background: rgba(255, 255, 255, 0.12);

  cursor: pointer;

  box-shadow:
    0 8px 15px rgba(0, 0, 0, 0.25),
    inset 0 1px 1px rgba(255, 255, 255, 0.15);

  transition: all 0.2s ease;
}

/* Hover Effect */
button:hover {
  transform: translateY(-4px) scale(1.03);
  background: rgba(255, 255, 255, 0.22);
}

/* Click Effect */
button:active {
  transform: scale(0.94);
}

/* Clear Button */
.clear {
  background: linear-gradient(135deg, #ff416c, #ff4b2b);
}

/* Operator Buttons */
.operator {
  background: linear-gradient(135deg, #ff9a44, #fc6076);
}

.buttons button:nth-child(2),
.buttons button:nth-child(3),
.buttons button:nth-child(4) {
  background: linear-gradient(135deg, #667eea, #764ba2);
}

/* Equal Button */
.equal {
  background: linear-gradient(135deg, #00b09b, #96c93d);
  height: 142px;
  grid-row: span 2;
}

.equal:hover {
  background: linear-gradient(135deg, #02d6bb, #a8df45);
}

/* Zero Button */
.zero {
  grid-column: span 3;
}

/* Footer */
footer {
  margin-top: 25px;
  padding-top: 18px;

  text-align: center;

  border-top: 1px solid rgba(255, 255, 255, 0.2);

  color: rgba(255, 255, 255, 0.8);
  font-size: 14px;
  letter-spacing: 0.5px;
}

footer p {
  margin: 6px 0;
}

/* Responsive Design */
@media (max-width: 450px) {
  .calculator {
    width: 100%;
    padding: 22px;
  }

  h1 {
    font-size: 24px;
  }

  button {
    height: 58px;
  }

  .equal {
    height: 128px;
  }
}
```


## OUTPUT

<img width="450" height="842" alt="Screenshot 2026-08-24 155209" src="https://github.com/user-attachments/assets/9e2e9930-a2dd-4d36-817d-906da4da3242" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.

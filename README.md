Calculator Application
Description
This is a simple calculator web application built using HTML, CSS, and JavaScript. It provides basic arithmetic operations and a clean, responsive user interface.

Files
index calc.html: The main HTML file containing the structure of the calculator.
style calc.css: The CSS file for styling the calculator.
script calc.js: The JavaScript file containing the logic for the calculator's functionality.
Features
Basic arithmetic operations: addition, subtraction, multiplication, and division.
Additional functions: clear (C), delete (DEL), and percentage (%).
Responsive and modern design with animations.
Typing effect on the welcome message.
Installation
Download the files: Ensure you have the index calc.html, style calc.css, and script calc.js files.
Open the HTML file: Open index calc.html in your web browser to launch the calculator.
Usage
Open the Calculator: Open index calc.html in any web browser.
Perform Calculations:
Enter numbers and operators using the buttons on the calculator.
Use = to get the result.
Use C to clear the input.
Use DEL to delete the last character.
Code Overview
HTML (index calc.html)
This file contains the structure of the calculator, including the buttons and display. It links to the CSS and JavaScript files.

html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="style calc.css">
</head>
<body>
    <div class="calc">
        <input type="text" placeholder="0" id="inputbox">
        <div>
            <button class="equal">C</button>
            <button class="equal">DEL</button>
            <button class="operator">%</button>
            <button class="operator">/</button>
        </div>
        <div>
            <button>7</button>
            <button>8</button>
            <button>9</button>
            <button class="operator">*</button>
        </div>
        <div>
            <button>4</button>
            <button>5</button>
            <button>6</button>
            <button class="operator">+</button>
        </div>
        <div>
            <button>1</button>
            <button>2</button>
            <button>3</button>
            <button class="operator">-</button>
        </div>
        <div>
            <button>00</button>
            <button>0</button>
            <button>.</button>
            <button class="equal">=</button>
        </div>
    </div>
    <div class="text">
        <h1 class="animate__animated animate__zoomInDown">Welcome to</h1>
        <h2>MY CALCULATOR!</h2>
    </div>
    <script src="script calc.js"></script>
</body>
</html>
CSS (style calc.css)
This file provides the styling for the calculator, including layout, colors, and animations.

css
Copy code
@import url('https://fonts.googleapis.com/css2?family=Roboto+Slab&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Roboto Slab', serif;
}

body {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(0, 0, 0, 0.982);
}
.text {
    color: white;
    line-height: 90px;
}

.text h1 {
    font-size: 80px;
    color: white;
    animation: myanim 5s infinite;
    text-transform: capitalize;
}

.text h2 {
    font-size: 40px;
    color: aqua;
    border-right: 2px solid red;
    letter-spacing: 10px;
    animation: typing 4s steps(14) 4, cursor .4s step-end infinite alternate;
}

@keyframes cursor {
    50% { border-color: transparent; }
}

@keyframes typing {
    from { width: 0; }
}

.calc {
    margin: 0 20%;
    border: 1px solid gray;
    padding: 20px;
    border-radius: 16px;
    background: transparent;
    box-shadow: 0 3px 15px rgba(113, 115, 119, 0.5);
}

input {
    width: 320px;
    border: none;
    padding: 24px;
    margin: 10px;
    background: transparent;
    box-shadow: 0 3px 15px rgba(84, 84, 84, 0.1);
    font-size: 40px;
    text-align: right;
    color: white;
}

input::placeholder {
    color: white;
}

button {
    border: none;
    width: 60px;
    height: 60px;
    margin: 10px;
    border-radius: 50%;
    background: white;
    font-size: 20px;
    box-shadow: -8px -8px 15px rgba(255, 255, 255, 0.1);
    cursor: pointer;
}

.equal {
    background: orangered;
}

.operator {
    background: rgb(255, 255, 65);
}
JavaScript (script calc.js)
This file contains the logic for the calculator's functionality, handling button clicks and performing calculations.

javascript
Copy code
let input = document.getElementById('inputbox');
let buttons = document.querySelectorAll('button');
let string = "";
let arr = Array.from(buttons);
arr.forEach(button => {
    button.addEventListener('click', (e) => {
        if (e.target.innerHTML == '=') {
            string = eval(string);
            input.value = string;
        } else if (e.target.innerHTML == 'C') {
            string = "";
            input.value = string;
        } else if (e.target.innerHTML == 'DEL') {
            string = string.substring(0, string.length - 1);
            input.value = string;
        } else {
            string += e.target.innerHTML;
            input.value = string;
        }
    });
});
License
This project is open-source and available under the MIT License.


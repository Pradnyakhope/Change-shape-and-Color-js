README.md
markdown
Copy code
# Shape and Color Manipulation Example

This project demonstrates a simple web application where you can change the color and shape of an element using HTML, CSS, and JavaScript.

## Project Structure

├── index.html
├── styles.css
├── script.js
└── README.md

## index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Change color and Shape</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="round">
            <div id="cross">
            </div>    
        </div>
        <div class="btn">
            <button>Change Color</button>
            <button>Change Shape</button>
        </div>
    </div>
    
    <script src="script.js"></script>
</body>
</html>

## style.css
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
body{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(234,244,244);
}

.container{
    border: 2px solid green;
    width: 400px;
    height: 400px;
    box-shadow: 0px 0px 51px -5px rgba(77,77,77,1);
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 40px;
    border-radius: 20px;
    background-color: white;
}
.round{
    width: 150px;
    height: 150px;
    background-color: green;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
}
#square{
    width: 70px;
    height: 70px;
    background-color: white;
}
#round{
    width: 70px;
    height: 70px;
    border-radius: 50%;
    background-color: green;
}
#diamond{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
}
#triangle{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
}
#arrow{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(40% 0%, 40% 20%, 100% 20%, 100% 80%, 40% 80%, 40% 100%, 0% 50%);
}
#frame{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(0% 0%, 0% 100%, 25% 100%, 25% 25%, 75% 25%, 75% 75%, 25% 75%, 25% 100%, 100% 100%, 100% 0%); 
}
#star{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
}
#cross{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(20% 0%, 0% 20%, 30% 50%, 0% 80%, 20% 100%, 50% 70%, 80% 100%, 100% 80%, 70% 50%, 100% 20%, 80% 0%, 50% 30%);
}
#left-point{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(25% 0%, 100% 1%, 100% 100%, 25% 100%, 0% 50%);
}
#right-point{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(0% 0%, 75% 0%, 100% 50%, 75% 100%, 0% 100%);
}
#parallal{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);
}
#cheg{
    width: 70px;
    height: 70px;
    background-color: white;
    clip-path: polygon(75% 0%, 100% 50%, 75% 100%, 0% 100%, 25% 50%, 0% 0%);
}
button {
    appearance: none;
    background-color: #000000;
    border: 2px solid #1A1A1A;
    border-radius: 15px;
    box-sizing: border-box;
    color: #FFFFFF;
    cursor: pointer;
    display: inline-block;
    font-family: Roobert,-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol";
    font-size: 16px;
    font-weight: 600;
    padding: 10px;
    text-align: center;
    text-decoration: none;
    transition: all 300ms cubic-bezier(.23, 1, 0.32, 1);
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
    width: 70%;
    /* margin: 20px 20px 20px 20px; */
    will-change: transform;
  }
  button:disabled {
    pointer-events: none;
  }
  
  button:hover {
    box-shadow: rgba(0, 0, 0, 0.25) 0 8px 15px;
    transform: translateY(-2px);
  }
  
  button:active {
    box-shadow: none;
    transform: translateY(0);
  }
  .btn{
      width: 70%;
      gap:20px;
      display: flex;
      justify-content: space-around;
      /* flex-wrap: wrap; */
      
  }

  ## script.js

  let round = document.querySelector(".round");
let btn = document.querySelectorAll("button");
let shape = document.querySelector("#square");

//to change the Color
btn[0].addEventListener("click", changeColor);

function genarateColor(){
    let color = Math.floor(Math.random() * 255);
    return color;
}

function changeColor(){
    let newColor = `rgb(${genarateColor()}, ${genarateColor()}, ${genarateColor()})`;
    round.style.backgroundColor = newColor;
}

//to change the Shape
let cur = "cross";
btn[1].addEventListener("click", changeShape);
let arr=["square", "round", "diamond", "triangle", "arrow", "frame", "star","cross", "left-point", "right-point", "parallal", "cheg"];

function randomShape(){
    let idx = Math.floor(Math.random() * arr.length);
    return arr[idx];
}

function changeShape(){
    let idname = randomShape();
    console.log(idname);
    // console.log(arr.id);
    document.getElementById(cur).setAttribute("id" , idname);
    // shape.id = idname;
    cur = idname
    
}

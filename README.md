# randomjokegenerator
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="randomjoke.css">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
  <style>
    *{
    margin: 0px; 
    padding: 0px;
    background-color: bisque;
}
#heading{
    display:flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100px;
    background-color: #283618;
    margin-top: 6px;
    text-align: center;
    color: #f7ede2;
}
#display{
    color:#98b97d;
    text-align: center;
    margin: 18px;
    margin: top 30px;
    font-size:xx-large;
}
button {
    margin-top: 40px;
    margin-right: 20px;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    background-color: #98b97d;
    color: white;
    border: none;
    border-radius: 5px;
    transition: 0.3s;
}
button:hover{
    cursor: pointer;
    background-color: rgb(140, 110, 179);
}
.displaybtn{
    display:flex;
    margin-top: 30px;
    justify-content: center;
    align-items: center;
}

  </style>
</head>
<body>
    <h2 id="heading">Random joke Generator</h2>
    <p id="display">Click the button to Generate joke</p>
    <div class="displaybtn">
        <button id="joke">Generate Joke</button>
    </div>
    
    <script>
    const para = document.querySelector("#joke");
const btn = document.querySelector("#joke");

const url = "https://v2.jokeapi.dev/joke/Programming?format=json";

const getFacts = async () => {
    let response = await fetch(url);
    console.log(response);
    let data = await response.json();
    
    if (data.type === "single") {
        para.innerText = data.joke;
    } else {
        para.innerText = `${data.setup} - ${data.delivery}`;
    }
}

btn.addEventListener("click", getFacts); 

    </script>
</body>
</html>

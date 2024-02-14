<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine's Day</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
  }
  #vending-machine {
    width: 300px;
    margin: 50px auto;
  }
  #tulip {
    width: 200px;
    margin: 20px auto;
    animation: float 5s ease-in-out infinite;
  }
  @keyframes float {
    0% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-10px);
    }
    100% {
      transform: translateY(0);
    }
  }
  #message {
    font-size: 24px;
    margin-bottom: 20px;
    display: none;
  }
  #yes-button, #no-button {
    padding: 10px 20px;
    font-size: 18px;
    margin: 0 10px;
    cursor: pointer;
  }
</style>
</head>
<body>
<img id="vending-machine" src="Phone/Download/2f7d20adc360c26ab6c63facabce93f7-removebg-preview.png" alt="Vending Machine">

<audio id="myAudio" src="Device storage/VidMate/download/Happy_with_U_by_Arthur_Nery.mp3" preload="auto"></audio>

<img id="tulip" src="Phone/DCIM/100PINT/Pins/3a1a22b665c69702d81770e2989e4eaa.jpg" alt="Tulip with Heart">

<div id="message">Will you be my Valentine?</div>
<button id="yes-button" onclick="respondToAnswer(true)">Yes</button>
<button id="no-button" onclick="respondToAnswer(false)">No</button>

<script>
function playAudio() {
  var audio = document.getElementById("myAudio");
  audio.play();
}

setTimeout(function() {
  playAudio();
  document.getElementById("message").style.display = "block";
}, 5000);

function respondToAnswer(isYes) {
  if (isYes) {
    document.getElementById("message").innerHTML = "";
    document.getElementById("tulip").src = "Phone/DCIM/100PINT/Pins/1d5075419e06e9dd9e9a8e5a0d1935b4.jpg";
    document.getElementById("tulip").alt = "Tulip with Heart";
    document.getElementById("tulip").style.animation = "none";
    document.body.style.backgroundColor = "blue"; // Change background color to blue
    document.getElementById("vending-machine").src = "Phone/Download/2f7d20adc360c26ab6c63facabce93f7-removebg-preview.png";
    document.getElementById("vending-machine").alt = "Betamax";
    document.getElementById("vending-machine").style.width = "200px"; // Adjust vending machine size
  } else {
    document.getElementById("message").innerHTML = "Hmm... Can you try clicking 'Yes' again?";
    document.getElementById("yes-button").addEventListener("click", function(event){
      event.preventDefault();
      alert("You clicked 'Yes' again! 😊");
    });
  }
  document.getElementById("yes-button").disabled = true;
  document.getElementById("no-button").disabled = true;
}
</script>
</body>
</html>

# Valentine-s-
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
  #message {
    font-size: 24px;
    margin-bottom: 20px;
  }
  #yes-button, #no-button {
    padding: 10px 20px;
    font-size: 18px;
    margin: 0 10px;
    cursor: pointer;
  }
  #tulip-container {
    margin-top: 50px;
    position: relative;
    width: 200px;
    height: 300px;
  }
  .tulip {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 80px;
    animation: tulipMove 4s linear infinite;
  }
  .heart {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 36px;
    color: blue;
  }
  .plate {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 100px;
    height: 50px;
    background-color: #f0e68c;
    border-radius: 50px 50px 0 0;
  }
  @keyframes tulipMove {
    0% { transform: translateX(-50%) translateY(0); }
    50% { transform: translateX(-50%) translateY(-20px); }
    100% { transform: translateX(-50%) translateY(0); }
  }
</style>
</head>
<body>
<div id="message">Hi there! Can you be my Valentine?</div>
<button id="yes-button" onclick="respondToAnswer(true)">Yes</button>
<button id="no-button" onclick="respondToAnswer(false)">No</button>
<div id="tulip-container">
  <img src="https://emojicdn.elk.sh/🌷" class="tulip">
  <div class="heart">❤️</div>
  <div class="plate"></div>
</div>

<script>
function respondToAnswer(isYes) {
  if (isYes) {
    document.getElementById("message").innerHTML = "Yay! Thank you!";
    document.getElementById("tulip-container").style.display = "block";
  } else {
    document.getElementById("message").innerHTML = "Hmm... Can you try clicking 'Yes' again?";
    document.getElementById("yes-button").addEventListener("click", function(event){
      event.preventDefault();
      alert("You clicked 'Yes' again! 😊");
    });
  }
  document.getElementById("no-button").disabled = true;
}
</script>
</body>
</html>

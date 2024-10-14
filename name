<!DOCTYPE html>
<html>
<head>
<title>Lucky Draw</title>
<style>
body {
  font-family: sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  margin: 0;
}

#name-input {
  padding: 10px;
  margin-bottom: 10px;
  font-size: 16px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

#winner-display { 
  display: none; 
  position: fixed; 
  top: 0; 
  left: 0; 
  width: 100%; 
  height: 100%; 
  background-color: rgba(0, 0, 0, 0.7); 
  color: white; 
  text-align: center; 
  font-size: 4em; 
  z-index: 1000; 
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

#winner-name {
  font-size: 2em;
  margin-bottom: 20px;
}
</style>
</head>
<body>

  <h1>Lucky Draw</h1>
  <input type="text" id="name-input" placeholder="Enter name">
  <button onclick="addName()">Add Name</button>
  <button onclick="drawWinner()">Draw Winner</button>

  <div id="winner-display">
    <div id="winner-name"></div>
    <button onclick="resetDraw()">Draw Again</button>  </div>

  <audio id="applause-sound" src="applause.mp3" preload="auto"></audio> 

  <script>
    let names = [];
    let previousWinners = [];

    function addName() {
      const nameInput = document.getElementById('name-input');
      const name = nameInput.value.trim();
      if (name !== "") {
        names.push(name);
        nameInput.value = "";
        console.log("Added name:", name);
      }
    }

    function drawWinner() {
      if (names.length === 0) {
        alert("Please enter names first!");
        return;
      }

      let winner;
      do {
        winner = names[Math.floor(Math.random() * names.length)];
      } while (previousWinners.includes(winner) && names.length > previousWinners.length);

      previousWinners.push(winner);

      document.getElementById('winner-name').innerText = winner;
      document.getElementById('winner-display').style.display = 'flex';
      document.getElementById('applause-sound').play();
    }

    function resetDraw() {
      document.getElementById('winner-display').style.display = 'none';
      if (names.length === previousWinners.length) {
        alert("All names have been drawn!");
        previousWinners = []; // Reset if everyone has won
      }
    }
  </script>

</body>
</html>

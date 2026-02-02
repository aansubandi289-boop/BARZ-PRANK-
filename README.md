<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>System Check</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  margin: 0;
  background: linear-gradient(135deg,#000,#1a1a1a);
  color: #00ff88;
  font-family: monospace;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.box {
  width: 90%;
  max-width: 400px;
  background: #000;
  border: 2px solid #00ff88;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 20px #00ff88;
}

.progress {
  width: 100%;
  height: 15px;
  background: #111;
  border-radius: 10px;
  overflow: hidden;
  margin-top: 10px;
}

.bar {
  height: 100%;
  width: 0%;
  background: #00ff88;
  transition: width 0.3s;
}

button {
  margin-top: 15px;
  width: 100%;
  padding: 10px;
  background: #00ff88;
  border: none;
  font-weight: bold;
  cursor: pointer;
}
</style>
</head>

<body>
<div class="box">
  <h3>🔍 System Scan</h3>
  <p id="text">Menyiapkan pemindaian...</p>
  <div class="progress"><div class="bar" id="bar"></div></div>
  <button onclick="start()">Mulai Scan</button>
</div>

<script>
let i = 0;
const bar = document.getElementById("bar");
const text = document.getElementById("text");

const logs = [
  "Memeriksa sistem...",
  "Menganalisis file...",
  "Optimasi memori...",
  "Sinkronisasi data...",
  "Menyelesaikan proses..."
];

function start(){
  i = 0;
  bar.style.width = "0%";
  run();
}

function run(){
  if(i < 100){
    i += Math.floor(Math.random()*10);
    bar.style.width = i + "%";
    text.innerText = logs[Math.floor(Math.random()*logs.length)];
    setTimeout(run, 600);
  } else {
    text.innerText = "❌ ERROR: Ini cuma prank 😄";
  }
}
</script>
</body>
</html>

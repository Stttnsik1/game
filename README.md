<!DOCTYPE html>
<html>

<head>
  <title>DYNYA CLICK</title>
  <style>
	body {
	  text-align: center;
	}

	#score {
	  font-size: 50px;
	}

	#earnButton {
	  border-radius: 50%;
	  margin-top: 30px;
	  touch-action: none;
	}

	#background {
	  position: fixed;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100%;
	  z-index: -1;
	}
    nav {
    margin: 20px auto; /* Добавляем отступы сверху и снизу, а также центрируем по горизонтали */
    padding: 10px;
    border: 3px solid rgb(53, 51, 51);
    border-radius: 10px;
    background-color: #333232;
    color: #ffffff;
    max-width: 50%; /* Устанавливаем максимальную ширину */
    margin-top: 25px; /* Отступ сверху */
    }
  </style>
</head>

<body>
  <div id="background" style="background: url('') no-repeat center center fixed; background-size: cover;"></div>

  <strong>
	<p style="font-family: 'Arial Black'; font-size: 60px;">Your XBC:<span id="score">0</span><img id="DYNYAImg" src='https://i.postimg.cc/XYPgc8KB/msg1029594875-176900.png' width="50" height="50"></p>
  </strong>
  <button id="earnButton" onclick="earnNotCoin()">
	<img src='https://i.postimg.cc/XYPgc8KB/msg1029594875-176900.png' width="600" height="600">
  </button>

  <nav><button>Market</button></nav>

  <script>
	let score = 0;
	let clickValue = 1;
	let wateringsBought = 0;

	function earnNotCoin() {
	  score += clickValue;
	  document.getElementById('score').textContent = score;
	  document.getElementById('DYNYAImg').src = 'https://i.postimg.cc/XYPgc8KB/msg1029594875-176900.png';
	}

	function Buy() {
	  let cost = 10 * Math.pow(2, wateringsBought); // Цена полива удваивается с каждой покупкой
	  if (score >= cost) {
		score -= cost;
		clickValue *= 2;
		wateringsBought++;
		document.getElementById('score').textContent = score;
		document.getElementById('wateringsBought').textContent = wateringsBought;
		document.getElementById('clickValue').textContent = clickValue;
	  } else {
		alert('Недостаточно очков для покупки полива!');
	  }
	}
  </script>

</body>
</html>

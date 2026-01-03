<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8" />
  <title>لعبة كشف الكرات</title>
  <style>
    .grid { display: grid; grid-template-columns: repeat(5, 60px); gap: 10px; }
    .cell {
      width: 60px; height: 60px; background: brown; border-radius: 50%; cursor: pointer;
      display: flex; justify-content: center; align-items: center; font-size: 20px; color: white;
    }
    .revealed { background: green; }
  </style>
</head>
<body>
  <h1>لعبة APPLE OF FORTUNE</h1>
  <div class="grid" id="gameGrid"></div>
  <script>
    const multipliers = [349.68, 69.93, 27.97, 11.18, 6.71, 4.02, 2.41, 1.93, 1.54, 1.23];
    const grid = document.getElementById('gameGrid');
    const cells = [];

    for(let i=0; i<25; i++) {
      let cell = document.createElement('div');
      cell.classList.add('cell');
      cell.textContent = '?';
      cell.addEventListener('click', function() {
        if(cell.classList.contains('revealed')) return;
        cell.classList.add('revealed');
        let randIndex = Math.floor(Math.random() * multipliers.length);
        cell.textContent = 'x' + multipliers[randIndex];
      });
      grid.appendChild(cell);
      cells.push(cell);
    }
  </script>
</body>
</html>

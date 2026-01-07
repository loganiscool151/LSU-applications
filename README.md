<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>LSU Applications</title>
  <style>
    :root {
      --bg: #1f1f1f;
      --card: #2b2b2b;
      --accent: #ff5252;
      --text: #ffffff;
      --muted: #bdbdbd;
    }

    * {
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    body {
      margin: 0;
      background: var(--bg);
      color: var(--text);
    }

    header {
      padding: 20px;
      text-align: center;
      border-bottom: 1px solid #333;
    }

    header h1 {
      margin: 0;
      font-size: 2rem;
      color: var(--accent);
    }

    header p {
      margin-top: 5px;
      color: var(--muted);
    }

    .container {
      padding: 20px;
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
      gap: 16px;
    }

    .game-card {
      background: var(--card);
      border-radius: 12px;
      padding: 14px;
      cursor: pointer;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .game-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 8px 20px rgba(0,0,0,0.4);
    }

    .game-thumb {
      width: 100%;
      height: 120px;
      background: #444;
      border-radius: 8px;
      margin-bottom: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 0.9rem;
      color: var(--muted);
    }

    .game-title {
      font-size: 1.1rem;
      margin: 0 0 4px 0;
    }

    .game-desc {
      font-size: 0.85rem;
      color: var(--muted);
    }

    /* Game Modal */
    .modal {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.8);
      display: none;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }

    .modal-content {
      background: #000;
      width: 100%;
      max-width: 900px;
      height: 500px;
      border-radius: 12px;
      overflow: hidden;
      position: relative;
    }

    .modal iframe {
      width: 100%;
      height: 100%;
      border: none;
    }

    .close-btn {
      position: absolute;
      top: 10px;
      right: 14px;
      font-size: 1.5rem;
      color: white;
      cursor: pointer;
    }
  </style>
</head>
<body>

<header>
  <h1>Pizza Edition Games</h1>
  <p>Simple • Fast • Unblocked</p>
</header>

<div class="container">
  <div class="game-card" onclick="openGame('games/example-game.html')">
    <div class="game-thumb">Thumbnail</div>
    <h3 class="game-title">Example Game</h3>
    <p class="game-desc">A simple HTML5 game</p>
  </div>

  <div class="game-card" onclick="openGame('https://example.com')">
    <div class="game-thumb">Thumbnail</div>
    <h3 class="game-title">Another Game</h3>
    <p class="game-desc">Runs in browser</p>
  </div>
</div>

<!-- Game Modal -->
<div class="modal" id="gameModal">
  <div class="modal-content">
    <span class="close-btn" onclick="closeGame()">×</span>
    <iframe id="gameFrame"></iframe>
  </div>
</div>

<script>
  function openGame(url) {
    document.getElementById('gameFrame').src = url;
    document.getElementById('gameModal').style.display = 'flex';
  }

  function closeGame() {
    document.getElementById('gameFrame').src = '';
    document.getElementById('gameModal').style.display = 'none';
  }
</script>

</body>
</html>


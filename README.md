# LugiaMay.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Ted’s Grand Finale – Oct 23</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root{
      --glow:#ff0044;
      --bg:#0a0a0a;
    }
    body{
      margin:0;
      height:100vh;
      display:flex;
      flex-direction:column;
      align-items:center;
      justify-content:center;
      background:var(--bg);
      color:#fff;
      font-family:"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
      text-align:center;
      overflow:hidden;
    }
    h1{
      font-size:clamp(2rem,5vw,4rem);
      letter-spacing:.05em;
      margin:0 0 .2em;
      animation:pulse 1.5s infinite;
    }
    #timer{
      font-size:clamp(3rem,10vw,7rem);
      font-variant-numeric:tabular-nums;
      letter-spacing:.03em;
      text-shadow:0 0 8px var(--glow),0 0 20px var(--glow);
    }
    footer{
      position:absolute;
      bottom:1rem;
      font-size:.75rem;
      opacity:.5;
    }
    @keyframes pulse{
      50%{opacity:.7;}
    }
  </style>
</head>
<body>
  <h1>Ted Nivison’s Grand Finale</h1>
  <div id="timer">--:--:--:--</div>
  <footer>“An inside joke, promise.” – Oct 23, 2025</footer>

  <script>
    // Change this if you want a different moment (24-hour clock)
    const target = new Date("2025-10-23T00:00:00");

    function pad(n){ return n.toString().padStart(2,'0'); }

    function tick(){
      const now = Date.now();
      let remain = Math.floor((target - now)/1000);

      if(remain <= 0){
        document.getElementById('timer').textContent = "00:00:00:00";
        document.querySelector('h1').textContent = "It’s been real, folks.";
        return;
      }

      const days = Math.floor(remain/86400); remain %= 86400;
      const hrs  = Math.floor(remain/3600);  remain %= 3600;
      const mins = Math.floor(remain/60);
      const secs = remain;

      document.getElementById('timer').textContent =
        `${pad(days)}:${pad(hrs)}:${pad(mins)}:${pad(secs)}`;
    }

    tick();
    setInterval(tick,1000);
  </script>
</body>
</html>

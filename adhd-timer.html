<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Timer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  *{ box-sizing:border-box; }

  html,body{
    margin:0;
    padding:0;
    background:#000;
    height:100%;
    font-family:'Poppins', sans-serif;
  }

  .stage{
    position:relative;
    width:100%;
    height:100vh;
    min-height:220px;
    display:flex;
    align-items:center;
    justify-content:center;
    cursor:pointer;
    -webkit-tap-highlight-color:transparent;
    user-select:none;
    overflow:hidden;
  }

  /* ---- time display ---- */
  .time-wrap{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%) scale(1);
    transition:transform .6s cubic-bezier(.2,.8,.2,1);
    display:flex;
    flex-direction:column;
    align-items:center;
  }

  .stage.stopped .time-wrap{
    transform:translate(-50%, calc(-50% - 84px)) scale(0.4);
  }

  .time-el{
    font-variant-numeric:tabular-nums;
    font-feature-settings:"tnum";
    font-weight:600;
    font-size:15vw;
    max-font-size:64px;
    line-height:1;
    color:#fff;
    letter-spacing:0.01em;
    white-space:nowrap;
  }

  @media (min-width:420px){
    .time-el{ font-size:64px; }
  }

  .colon{
    display:inline-block;
  }
  .stage.running .colon{
    animation:blink 1s steps(1) infinite;
  }
  @keyframes blink{
    50%{ opacity:0.15; }
  }

  .caption{
    margin-top:14px;
    font-size:10px;
    font-weight:500;
    letter-spacing:0.22em;
    text-transform:uppercase;
    color:rgba(255,255,255,0.32);
    transition:opacity .3s ease;
  }

  .stage.stopped .caption{
    margin-top:8px;
  }

  /* ---- question display ---- */
  .question-wrap{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    max-width:260px;
    text-align:center;
    opacity:0;
    transition:opacity .5s ease .15s;
    pointer-events:none;
    padding:0 20px;
  }

  .stage.stopped .question-wrap{
    opacity:1;
  }

  .question-el{
    font-weight:400;
    font-size:19px;
    line-height:1.45;
    color:rgba(255,255,255,0.92);
  }

  .elapsed-note{
    margin-top:10px;
    font-size:10px;
    font-weight:500;
    letter-spacing:0.15em;
    text-transform:uppercase;
    color:rgba(255,255,255,0.28);
  }
</style>
</head>
<body>

<div class="stage" id="stage">
  <div class="time-wrap" id="timeWrap">
    <div class="time-el" id="timeEl">0:00</div>
    <div class="caption" id="caption">tap to start</div>
  </div>

  <div class="question-wrap" id="questionWrap">
    <div class="question-el" id="questionEl">What do I need right now?</div>
    <div class="elapsed-note" id="elapsedNote"></div>
  </div>
</div>

<script>
(function(){
  const stage = document.getElementById('stage');
  const timeEl = document.getElementById('timeEl');
  const caption = document.getElementById('caption');
  const questionEl = document.getElementById('questionEl');
  const elapsedNote = document.getElementById('elapsedNote');

  const questions = [
    "What do I need right now?",
    "What can I do to nourish myself?",
    "Have a glass of water.",
    "Time for a bio break.",
    "Shut those eyes."
  ];
  let qIndex = 0;

  let state = 'idle'; // idle | running | stopped
  let startedAt = 0;
  let elapsedMs = 0;
  let rafId = null;

  function formatTime(ms){
    const totalSec = Math.floor(ms / 1000);
    const h = Math.floor(totalSec / 3600);
    const m = Math.floor((totalSec % 3600) / 60);
    const s = totalSec % 60;
    const pad = n => String(n).padStart(2,'0');

    if(h > 0){
      return `${h}:${pad(m)}<span class="colon">:</span>${pad(s)}`;
    }
    return `${m}<span class="colon">:</span>${pad(s)}`;
  }

  function formatElapsedNote(ms){
    const totalMin = Math.round(ms / 60000);
    if(totalMin < 1) return 'less than a minute';
    if(totalMin === 1) return '1 minute';
    return totalMin + ' minutes';
  }

  function tick(){
    const now = performance.now();
    const current = elapsedMs + (now - startedAt);
    timeEl.innerHTML = formatTime(current);
    rafId = requestAnimationFrame(tick);
  }

  function start(){
    state = 'running';
    stage.classList.remove('stopped');
    stage.classList.add('running');
    caption.textContent = 'tap to stop';
    startedAt = performance.now();
    rafId = requestAnimationFrame(tick);
  }

  function stop(){
    state = 'stopped';
    stage.classList.remove('running');
    stage.classList.add('stopped');
    cancelAnimationFrame(rafId);

    const now = performance.now();
    elapsedMs = elapsedMs + (now - startedAt);
    timeEl.innerHTML = formatTime(elapsedMs);
    caption.textContent = 'tap to reset';

    questionEl.textContent = questions[qIndex % questions.length];
    qIndex++;
    elapsedNote.textContent = formatElapsedNote(elapsedMs);
  }

  function reset(){
    state = 'idle';
    stage.classList.remove('stopped');
    stage.classList.remove('running');
    elapsedMs = 0;
    timeEl.innerHTML = formatTime(0);
    caption.textContent = 'tap to start';
  }

  stage.addEventListener('click', function(){
    if(state === 'idle') start();
    else if(state === 'running') stop();
    else if(state === 'stopped') reset();
  });

  stage.setAttribute('tabindex','0');
  stage.addEventListener('keydown', function(e){
    if(e.key === 'Enter' || e.key === ' '){
      e.preventDefault();
      stage.click();
    }
  });
})();
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>가위바위보 계단전 (고급화)</title>
<style>
:root{--bg:#071022;--accent:#22c1c3;--muted:#9aa4b2;--win:#b7ffd9;--lose:#ff9b9b;--mine:#ffdd57;}
*{box-sizing:border-box;margin:0;padding:0}
body{background:linear-gradient(180deg,#031026,#071228);font-family:Inter,'Noto Sans KR',sans-serif;display:flex;justify-content:center;align-items:center;height:100vh;color:#e6eef6;overflow:hidden}
.wrapper{display:flex;gap:12px;max-width:96vw}
.card{background:rgba(255,255,255,0.03);padding:16px;border-radius:12px;box-shadow:0 8px 20px rgba(0,0,0,0.5);display:flex;flex-direction:column;align-items:center}
.stairs{width:160px;height:600px;display:flex;flex-direction:column-reverse;gap:2px;padding:8px;overflow-y:auto;border:1px solid rgba(255,255,255,0.1);position:relative;background:rgba(0,0,0,0.1)}
.step{height:18px;border-radius:4px;background:rgba(255,255,255,0.05);display:flex;align-items:center;justify-content:center;font-size:10px;color:var(--muted);position:relative;transition:background 0.3s}
.step.mine{border:1px solid var(--mine)}
.step.revealed{background:rgba(255,221,87,0.3)}
.player,.ai{position:absolute;width:14px;height:14px;border-radius:50%;display:flex;align-items:center;justify-content:center;transition:bottom 0.4s ease, transform 0.2s;z-index:2}
.player{background:#1f8fd7;left:50px}
.ai{background:#9b59ff;left:80px}
.messages{width:280px;height:600px;overflow-y:auto;background:rgba(0,0,0,0.08);padding:8px;border-radius:8px;font-size:12px;margin-top:8px}
.btn{margin:4px;padding:6px 8px;border-radius:6px;background:rgba(255,255,255,0.05);cursor:pointer;user-select:none;text-align:center}
.btn:hover{background:rgba(255,255,255,0.1)}
.hud{margin-bottom:6px;font-size:12px;display:flex;gap:6px;flex-wrap:wrap;justify-content:center}
.good{color:var(--win)}
.bad{color:var(--lose)}
.mine-log{color:var(--mine)}
</style>
</head>
<body>
<div class="wrapper">
  <div class="card">
    <div class="hud">계단: <span id="stepDisplay">0</span>/77</div>
    <div class="stairs" id="stairs"></div>
    <div class="hud">지뢰 잔여: 플레이어 <span id="playerMines">3</span>, AI <span id="aiMines">3</span></div>
    <div style="margin-top:8px">
      <div class="btn" id="startBtn">게임 시작</div>
      <div class="btn" id="restartBtn">다시 시작</div>
    </div>
    <div class="messages" id="messages"></div>
    <div style="margin-top:8px;display:flex;gap:4px">
      <div class="btn r" data-choice="rock">주먹 (Rock)</div>
      <div class="btn p" data-choice="paper">보 (Paper)</div>
      <div class="btn s" data-choice="scissors">가위 (Scissors)</div>
    </div>
  </div>
</div>
<script>
const TOTAL_STEPS = 77;
let playerStep=0, aiStep=0;
let playerMinesSet=new Set(), aiMinesSet=new Set();
let playerMinesLeft=3, aiMinesLeft=3;
let placementMode=true;
const stairsEl=document.getElementById('stairs');
const stepDisplay=document.getElementById('stepDisplay');
const messages=document.getElementById('messages');
const playerEl=document.createElement('div');playerEl.className='player';stairsEl.appendChild(playerEl);
const aiEl=document.createElement('div');aiEl.className='ai';stairsEl.appendChild(aiEl);

function log(msg,cls){const d=document.createElement('div');d.textContent=msg;if(cls)d.className=cls;messages.appendChild(d);messages.scrollTop=messages.scrollHeight;}

function buildStairs(){stairsEl.innerHTML='';for(let i=0;i<=TOTAL_STEPS;i++){const step=document.createElement('div');step.className='step';step.dataset.idx=i;step.textContent=i;step.addEventListener('click',()=>{if(!placementMode)return;if(playerMinesLeft<=0){log('지뢰 모두 설치 완료');return;}if(playerMinesSet.has(i)){playerMinesSet.delete(i);playerMinesLeft++;updateStairs();log(`지뢰 제거:${i}`);} else{playerMinesSet.add(i);playerMinesLeft--;updateStairs();log(`지뢰 설치:${i}`);}});stairsEl.appendChild(step);}}

function updateStairs(){document.querySelectorAll('.step').forEach(s=>{const idx=Number(s.dataset.idx);s.classList.toggle('mine',playerMinesSet.has(idx));});document.getElementById('playerMines').textContent=playerMinesLeft;}

function placeAIMines(){aiMinesSet.clear();while(aiMinesSet.size<3){let pos=Math.floor(Math.random()*(TOTAL_STEPS-1))+1;if(playerMinesSet.has(pos)) continue;aiMinesSet.add(pos);}document.getElementById('aiMines').textContent=3;}

function startGame(){if(playerMinesSet.size!==3){alert('지뢰 3개 설치 후 시작');return;}placementMode=false;placeAIMines();log('게임 시작!');updatePlayer();}

function restartGame(){playerStep=0;aiStep=0;placementMode=true;playerMinesSet.clear();aiMinesSet.clear();playerMinesLeft=3;aiMinesLeft=3;buildStairs();updateStairs();updatePlayer();log('게임 초기화');}

function updatePlayer(){const stepHeight=18+2;playerEl.style.bottom=`${playerStep*stepHeight}px`;aiEl.style.bottom=`${aiStep*stepHeight}px`;stepDisplay.textContent=playerStep;}

function cpuChoice(){const arr=['rock','paper','scissors'];return arr[Math.floor(Math.random()*3)];}

function judge(player,cpu){if(player===cpu)return'draw';if((player==='rock'&&cpu==='scissors')||(player==='scissors'&&cpu==='paper')||(player==='paper'&&cpu==='rock'))return'win';return'lose';}

function animateJump(el){el.style.transform='translateY(-10px)';setTimeout(()=>el.style.transform='translateY(0)',200);}

function playRound(choice){if(placementMode){alert('지뢰 설치 후 시작');return;}const cpu=cpuChoice();const res=judge(choice,cpu);let move=0;if(res==='win'){move=(choice==='rock'?3:6);playerStep=Math.min(TOTAL_STEPS,playerStep+move);log(`플레이어 승! ${choice} vs ${cpu} +${move}칸`,'good');} else if(res==='lose'){log(`플레이어 패! ${choice} vs ${cpu} (제자리)`,'bad');} else{log(`비김 ${choice} vs ${cpu}`);} animateJump(playerEl);checkMine('player');aiTurn();updatePlayer();if(playerStep>=TOTAL_STEPS){log('🎉 플레이어 정상 도달!','good');}if(aiStep>=TOTAL_STEPS){log('💀 AI 정상 도달!','bad');}}

function checkMine(who){if(who==='player'){if(aiMinesSet.has(playerStep)){playerStep=Math.max(0,playerStep-10);aiMinesSet.delete(playerStep);log(`상대 지뢰 밟음! -10칸`,'mine');document.querySelector(`.step[data-idx='${playerStep}']`)?.classList.add('revealed');} else if(playerMinesSet.has(playerStep)){log(`내 지뢰 밟음, 위치 공개:${playerStep}`,'mine');document.querySelector(`.step[data-idx='${playerStep}']`)?.classList.add('revealed');}} else{if(playerMinesSet.has(aiStep)){aiStep=Math.max(0,aiStep-10);playerMinesSet.delete(aiStep);log(`AI가 내 지뢰 밟음! -10칸`,'mine');document.querySelector(`.step[data-idx='${aiStep}']`)?.classList.add('revealed');} else if(aiMinesSet.has(aiStep)){log(`AI 자기 지뢰 밟음, 위치 공개:${aiStep}`,'mine');document.querySelector(`.step[data-idx='${aiStep}']`)?.classList.add('revealed');}}}

function aiTurn(){const cpu=cpuChoice();const move=(cpu==='rock'?3:6);aiStep=Math.min(TOTAL_STEPS,aiStep+move);log(`AI 선택:${cpu} → +${move}칸`);animateJump(aiEl);checkMine('ai');}

buildStairs();updateStairs();updatePlayer();
document.getElementById('startBtn').addEventListener('click',startGame);
document.getElementById('restartBtn').addEventListener('click',restartGame);
document.querySelectorAll('.btn.r,.btn.p,.btn.s').forEach(b=>b.addEventListener('click',()=>playRound(b.dataset.choice)));
</script>
</body>
</html>

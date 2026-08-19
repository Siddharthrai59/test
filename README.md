<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YO YO Jukebox — Uss Zamaane Ka Vibe</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Anton&family=Rajdhani:wght@500;600;700&family=Teko:wght@500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg-black:#0a0a0d;
    --gold:#d4af37;
    --gold-bright:#f4d160;
    --neon-red:#ff2140;
    --electric-purple:#8a2be2;
    --ice-blue:#3fd4e0;
    --text:#f3ede0;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html,body{height:100%;}
  body{ background:var(--bg-black); color:var(--text); font-family:'Rajdhani', sans-serif; overflow:hidden; height:100vh; position:relative; }
  .haze-layer{ position:fixed; inset:0; z-index:0; pointer-events:none;
    background: radial-gradient(ellipse 60% 50% at 20% 20%, rgba(138,43,226,0.35), transparent 60%),
      radial-gradient(ellipse 55% 45% at 85% 15%, rgba(255,33,64,0.28), transparent 60%),
      radial-gradient(ellipse 70% 60% at 50% 100%, rgba(212,175,55,0.22), transparent 65%),
      linear-gradient(180deg, #0a0a0d 0%, #14111a 50%, #0a0a0d 100%);
    animation: hazeShift 18s ease-in-out infinite alternate; }
  @keyframes hazeShift{ 0%{filter:hue-rotate(0deg) brightness(1);} 100%{filter:hue-rotate(18deg) brightness(1.12);} }
  .smoke-drift{ position:fixed; inset:-10%; z-index:1; pointer-events:none; opacity:0.5;
    background-image: radial-gradient(circle at 30% 70%, rgba(255,255,255,0.05) 0%, transparent 8%),
      radial-gradient(circle at 70% 30%, rgba(255,255,255,0.04) 0%, transparent 10%),
      radial-gradient(circle at 50% 50%, rgba(255,255,255,0.03) 0%, transparent 12%);
    animation: drift 30s linear infinite; }
  @keyframes drift{ 0%{transform:translate(0,0) scale(1);} 50%{transform:translate(3%,-2%) scale(1.05);} 100%{transform:translate(0,0) scale(1);} }
  .particle{ position:fixed; z-index:2; border-radius:50%; background:radial-gradient(circle, var(--gold-bright), transparent 70%); opacity:0.7; pointer-events:none; animation: floatUp linear infinite; }
  @keyframes floatUp{ 0%{transform:translateY(0) translateX(0); opacity:0;} 10%{opacity:0.8;} 90%{opacity:0.5;} 100%{transform:translateY(-110vh) translateX(20px); opacity:0;} }
  .stage{ position:relative; z-index:5; height:100%; width:100%; display:flex; flex-direction:column; align-items:center; justify-content:center; padding:24px; text-align:center; }
  .eyebrow{ font-family:'Teko', sans-serif; letter-spacing:0.5em; font-size:14px; color:var(--ice-blue); text-transform:uppercase; margin-bottom:6px; opacity:0.85; }
  .neon-title{ font-family:'Anton', sans-serif; font-size:clamp(46px, 11vw, 108px); line-height:0.95; letter-spacing:2px; color:var(--gold-bright);
    text-shadow: 0 0 6px rgba(244,209,96,0.9), 0 0 18px rgba(244,209,96,0.6), 0 0 40px rgba(255,33,64,0.55), 0 0 80px rgba(138,43,226,0.4);
    animation: neonFlicker 4.2s infinite; margin-bottom:2px; }
  .neon-sub{ font-family:'Anton', sans-serif; font-size:clamp(16px, 3vw, 26px); letter-spacing:8px; color:var(--neon-red);
    text-shadow:0 0 8px rgba(255,33,64,0.8), 0 0 22px rgba(255,33,64,0.5); margin-bottom:36px; }
  @keyframes neonFlicker{ 0%, 3%, 6%, 100%{opacity:1;} 4%{opacity:0.4;} 5%{opacity:0.85;} 52%{opacity:1;} 53%{opacity:0.5;} 54%{opacity:1;} }
  @media (prefers-reduced-motion: reduce){ .neon-title{ animation:none; } }
  .disc-wrap{ position:relative; width:min(52vw, 260px); height:min(52vw, 260px); margin:10px auto 28px; display:flex; align-items:center; justify-content:center; }
  .disc{ width:100%; height:100%; border-radius:50%;
    background: radial-gradient(circle at 50% 50%, #171314 0%, #171314 18%, transparent 19%),
      repeating-radial-gradient(circle at 50% 50%, #23202a 0px, #23202a 2px, #1a1720 3px, #1a1720 4px);
    border:6px solid var(--gold);
    box-shadow: 0 0 30px rgba(212,175,55,0.5), 0 0 60px rgba(255,33,64,0.25), inset 0 0 30px rgba(0,0,0,0.6);
    display:flex; align-items:center; justify-content:center; transition:box-shadow .3s ease; }
  .disc.playing{ animation: spin 5s linear infinite; }
  @keyframes spin{ from{transform:rotate(0deg);} to{transform:rotate(360deg);} }
  @media (prefers-reduced-motion: reduce){ .disc.playing{ animation:none; } }
  .disc-center{ width:34%; height:34%; border-radius:50%; background:radial-gradient(circle at 35% 35%, var(--gold-bright), var(--gold) 55%, #7a611c 100%);
    display:flex; align-items:center; justify-content:center; font-family:'Anton', sans-serif; font-size:11px; letter-spacing:1px; color:#1a1410; box-shadow:0 0 18px rgba(212,175,55,0.7); }
  .glow-ring{ position:absolute; inset:-14px; border-radius:50%; border:2px solid rgba(212,175,55,0.35); animation:pulseRing 2.4s ease-in-out infinite; }
  @keyframes pulseRing{ 0%,100%{transform:scale(1); opacity:0.5;} 50%{transform:scale(1.06); opacity:0.9;} }
  @media (prefers-reduced-motion: reduce){ .glow-ring{ animation:none; } }
  .now-playing-label{ font-family:'Teko', sans-serif; letter-spacing:4px; font-size:13px; color:var(--ice-blue); text-transform:uppercase; margin-bottom:4px; }
  .song-title{ font-family:'Anton', sans-serif; font-size:clamp(20px, 4.5vw, 34px); color:var(--text); text-shadow:0 0 12px rgba(212,175,55,0.3); margin-bottom:2px; }
  .song-meta{ font-family:'Rajdhani', sans-serif; font-weight:600; font-size:clamp(13px, 2.2vw, 16px); color:#c9c2b2; letter-spacing:1px; margin-bottom:26px; }
  .equalizer{ display:flex; align-items:flex-end; justify-content:center; gap:5px; height:34px; margin-bottom:30px; }
  .eq-bar{ width:5px; border-radius:3px; background:linear-gradient(180deg, var(--gold-bright), var(--neon-red)); height:6px; transition:height .15s ease; }
  .eq-bar.playing{ animation:eqBounce 1s ease-in-out infinite; }
  .eq-bar:nth-child(1){ animation-delay:0s; } .eq-bar:nth-child(2){ animation-delay:.15s; } .eq-bar:nth-child(3){ animation-delay:.3s; }
  .eq-bar:nth-child(4){ animation-delay:.1s; } .eq-bar:nth-child(5){ animation-delay:.25s; }
  @keyframes eqBounce{ 0%,100%{height:6px;} 50%{height:32px;} }
  @media (prefers-reduced-motion: reduce){ .eq-bar.playing{ animation:none; height:16px; } }
  .controls{ display:flex; align-items:center; justify-content:center; gap:22px; }
  .ctrl-btn{ background:linear-gradient(155deg, #23202a, #14121a); border:2px solid var(--gold); color:var(--gold-bright); width:64px; height:64px; border-radius:50%;
    display:flex; align-items:center; justify-content:center; cursor:pointer; box-shadow:0 0 18px rgba(212,175,55,0.25); transition:transform .15s ease, box-shadow .15s ease; }
  .ctrl-btn:hover{ transform:scale(1.07); box-shadow:0 0 28px rgba(212,175,55,0.5); }
  .ctrl-btn:active{ transform:scale(0.96); }
  .ctrl-btn:focus-visible{ outline:3px solid var(--ice-blue); outline-offset:3px; }
  .ctrl-btn.play-pause{ width:76px; height:76px; }
  .ctrl-btn svg{ width:26px; height:26px; }
  .ctrl-btn.play-pause svg{ width:30px; height:30px; }
  #startOverlay{ position:fixed; inset:0; z-index:50; background:radial-gradient(circle at 50% 40%, #1c1720 0%, #0a0a0d 75%);
    display:flex; flex-direction:column; align-items:center; justify-content:center; gap:22px; text-align:center; padding:24px; }
  #startOverlay .neon-title{ font-size:clamp(34px, 9vw, 72px); }
  .start-btn{ font-family:'Anton', sans-serif; letter-spacing:2px; font-size:20px; color:#171314; background:linear-gradient(155deg, var(--gold-bright), var(--gold));
    border:none; padding:16px 40px; border-radius:40px; cursor:pointer; box-shadow:0 0 30px rgba(212,175,55,0.5), 0 0 60px rgba(255,33,64,0.25); transition:transform .15s ease; }
  .start-btn:hover{ transform:scale(1.05); }
  .start-btn:focus-visible{ outline:3px solid var(--ice-blue); outline-offset:4px; }
  .start-hint{ font-family:'Rajdhani', sans-serif; font-weight:600; color:#a89f8c; font-size:14px; letter-spacing:1px; max-width:320px; }
  #ytplayer1, #ytplayer2{ position:fixed; width:1px; height:1px; opacity:0; pointer-events:none; bottom:0; right:0; }
  .sr-only{ position:absolute; width:1px; height:1px; overflow:hidden; clip:rect(0,0,0,0); }

  #soundBanner{
    position:fixed; top:18px; left:50%; transform:translateX(-50%);
    z-index:50; display:flex; align-items:center; gap:12px;
    background:rgba(20,17,26,0.85); border:2px solid var(--gold);
    border-radius:40px; padding:10px 20px;
    box-shadow:0 0 24px rgba(212,175,55,0.4);
    backdrop-filter:blur(6px);
    animation: bannerPulse 1.8s ease-in-out infinite;
  }
  @keyframes bannerPulse{ 0%,100%{ box-shadow:0 0 24px rgba(212,175,55,0.4); } 50%{ box-shadow:0 0 40px rgba(255,33,64,0.5); } }
  @media (prefers-reduced-motion: reduce){ #soundBanner{ animation:none; } }
  .sound-banner-text{ font-family:'Rajdhani', sans-serif; font-weight:600; font-size:13px; color:var(--text); letter-spacing:0.5px; }
  .sound-banner-btn{
    background:linear-gradient(155deg, var(--gold-bright), var(--gold)); border:none; color:#171314;
    width:36px; height:36px; border-radius:50%; font-size:16px; cursor:pointer;
    display:flex; align-items:center; justify-content:center;
  }
  .sound-banner-btn:focus-visible{ outline:3px solid var(--ice-blue); outline-offset:3px; }
  #soundBanner.hidden{ display:none; }
</style>
</head>
<body>

<div class="haze-layer"></div>
<div class="smoke-drift"></div>
<div id="particles"></div>

<div id="soundBanner">
  <span class="sound-banner-text">Awaaz on karne ke liye yahan tap karo</span>
  <button class="sound-banner-btn" id="soundBtn" aria-label="Awaaz chalu karo">&#128266;</button>
</div>

<div class="stage">
  <div class="eyebrow">International Villager Era</div>
  <div class="neon-title">YO YO</div>
  <div class="neon-sub">JUKEBOX</div>

  <div class="disc-wrap">
    <div class="glow-ring"></div>
    <div class="disc" id="disc"><div class="disc-center">YO YO</div></div>
  </div>

  <div class="now-playing-label">Ab Baj Raha Hai</div>
  <div class="song-title" id="songTitle">—</div>
  <div class="song-meta" id="songMeta">—</div>

  <div class="equalizer" id="equalizer">
    <div class="eq-bar"></div><div class="eq-bar"></div><div class="eq-bar"></div><div class="eq-bar"></div><div class="eq-bar"></div>
  </div>

  <div class="controls">
    <button class="ctrl-btn play-pause" id="playPauseBtn" aria-label="Play ya Pause">
      <svg id="playIcon" viewBox="0 0 24 24" fill="currentColor"><path d="M8 5v14l11-7z"/></svg>
      <svg id="pauseIcon" viewBox="0 0 24 24" fill="currentColor" style="display:none"><path d="M6 5h4v14H6zM14 5h4v14h-4z"/></svg>
    </button>
    <button class="ctrl-btn" id="nextBtn" aria-label="Agla Gaana">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M6 5v14l8-7zM16 5h2v14h-2z"/></svg>
    </button>
  </div>
</div>

<div id="ytplayer1"></div>
<div id="ytplayer2"></div>
<div class="sr-only" aria-live="polite" id="liveRegion"></div>

<script>
const PLAYLIST = [
  { id: "NbyHNASFi6U", title: "Blue Eyes", meta: "2013 · Blockbuster" },
  { id: "Wd7H311MrWA", title: "Party All Night", meta: "Boss · 2013 · feat. Akshay Kumar" },
  { id: "69CEiHfS_mc", title: "Lungi Dance", meta: "Chennai Express · 2013" },
  { id: "Iu8210k9WQc", title: "Angreji Beat", meta: "International Villager · 2011 · feat. Gippy Grewal" },
  { id: "Ich9KbklTK0", title: "Brown Rang", meta: "International Villager · 2012" },
  { id: "KhnVcAC5bIM", title: "Desi Kalakaar", meta: "2014" },
  { id: "x8F5dz8kv1w", title: "Chaar Botal Vodka", meta: "Ragini MMS 2 · 2014" },
  { id: "TvngY4unjn4", title: "Love Dose", meta: "Desi Kalakaar · 2014" }
];

(function spawnParticles(){
  const container = document.getElementById('particles');
  for(let i=0;i<22;i++){
    const p = document.createElement('div');
    p.className = 'particle';
    const size = 2 + Math.random()*4;
    p.style.width = size+'px'; p.style.height = size+'px';
    p.style.left = Math.random()*100+'vw'; p.style.bottom = '-10px';
    p.style.animationDuration = (10 + Math.random()*14)+'s';
    p.style.animationDelay = (Math.random()*14)+'s';
    container.appendChild(p);
  }
})();

let players = [null, null];
let playerReady = [false, false];
let activeIdx = 0;
let currentPlaylistIdx = null;
let nextPlaylistIdx = null;
let started = true;
let apiReady = false;
let isMuted = true;

const els = {
  disc: document.getElementById('disc'),
  songTitle: document.getElementById('songTitle'),
  songMeta: document.getElementById('songMeta'),
  equalizer: document.getElementById('equalizer'),
  playIcon: document.getElementById('playIcon'),
  pauseIcon: document.getElementById('pauseIcon'),
  playPauseBtn: document.getElementById('playPauseBtn'),
  nextBtn: document.getElementById('nextBtn'),
  soundBanner: document.getElementById('soundBanner'),
  soundBtn: document.getElementById('soundBtn'),
  liveRegion: document.getElementById('liveRegion')
};

function pickRandomIndex(excludeIdx){
  if(PLAYLIST.length === 1) return 0;
  let idx;
  do{ idx = Math.floor(Math.random()*PLAYLIST.length); } while(idx === excludeIdx);
  return idx;
}

function loadYouTubeAPI(){
  const tag = document.createElement('script');
  tag.src = "https://www.youtube.com/iframe_api";
  document.body.appendChild(tag);
}

window.onYouTubeIframeAPIReady = function(){
  apiReady = true;
  players[0] = new YT.Player('ytplayer1', {
    height:'1', width:'1', videoId:'',
    playerVars:{ autoplay:0, controls:0, disablekb:1, playsinline:1, rel:0, mute:1 },
    events:{ onReady:()=>{ playerReady[0]=true; maybeBoot(); }, onStateChange:(e)=>onPlayerStateChange(0, e) }
  });
  players[1] = new YT.Player('ytplayer2', {
    height:'1', width:'1', videoId:'',
    playerVars:{ autoplay:0, controls:0, disablekb:1, playsinline:1, rel:0, mute:1 },
    events:{ onReady:()=>{ playerReady[1]=true; maybeBoot(); }, onStateChange:(e)=>onPlayerStateChange(1, e) }
  });
};

function maybeBoot(){
  if(playerReady[0] && playerReady[1] && started && currentPlaylistIdx === null){
    bootPlayback();
  }
}

function bootPlayback(){
  activeIdx = 0;
  currentPlaylistIdx = pickRandomIndex(null);
  nextPlaylistIdx = pickRandomIndex(currentPlaylistIdx);
  players[activeIdx].mute();
  players[activeIdx].loadVideoById(PLAYLIST[currentPlaylistIdx].id);
  updateNowPlaying(currentPlaylistIdx);
  const standby = 1 - activeIdx;
  players[standby].cueVideoById(PLAYLIST[nextPlaylistIdx].id);
}

function onPlayerStateChange(playerIdx, e){
  if(playerIdx !== activeIdx) return;
  if(e.data === YT.PlayerState.ENDED){
    advanceToNext();
  } else if(e.data === YT.PlayerState.PLAYING){
    setPlayingUI(true);
  } else if(e.data === YT.PlayerState.PAUSED){
    setPlayingUI(false);
  } else if(e.data === -1 || e.data === YT.PlayerState.CUED){
    // if the active track fails to autostart, nudge it
    if(started && currentPlaylistIdx !== null){ players[activeIdx].playVideo(); }
  }
}

function advanceToNext(){
  const newActive = 1 - activeIdx;
  currentPlaylistIdx = nextPlaylistIdx;
  activeIdx = newActive;
  if(isMuted){ players[activeIdx].mute(); } else { players[activeIdx].unMute(); }
  players[activeIdx].playVideo();
  updateNowPlaying(currentPlaylistIdx);
  nextPlaylistIdx = pickRandomIndex(currentPlaylistIdx);
  const standby = 1 - activeIdx;
  players[standby].cueVideoById(PLAYLIST[nextPlaylistIdx].id);
}

function playNextManually(){
  if(currentPlaylistIdx === null) return;
  advanceToNext();
}

function updateNowPlaying(idx){
  const song = PLAYLIST[idx];
  els.songTitle.textContent = song.title;
  els.songMeta.textContent = song.meta;
  els.liveRegion.textContent = "Ab baj raha hai: " + song.title;
}

function setPlayingUI(playing){
  els.disc.classList.toggle('playing', playing);
  els.equalizer.querySelectorAll('.eq-bar').forEach(b => b.classList.toggle('playing', playing));
  els.playIcon.style.display = playing ? 'none' : 'block';
  els.pauseIcon.style.display = playing ? 'block' : 'none';
}

function togglePlayPause(){
  if(currentPlaylistIdx === null) return;
  const p = players[activeIdx];
  const state = p.getPlayerState();
  if(state === YT.PlayerState.PLAYING){ p.pauseVideo(); } else { p.playVideo(); }
}

els.playPauseBtn.addEventListener('click', togglePlayPause);
els.nextBtn.addEventListener('click', playNextManually);

els.soundBtn.addEventListener('click', () => {
  isMuted = false;
  if(players[activeIdx]){ players[activeIdx].unMute(); }
  els.soundBanner.classList.add('hidden');
});

loadYouTubeAPI();
</script>
</body>
</html>

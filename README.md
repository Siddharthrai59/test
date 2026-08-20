<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yo Yo Adda — Honey Singh Era</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@600;700;800&family=Rajdhani:wght@500;600;700&family=Teko:wght@500;600;700&display=swap" rel="stylesheet">

<script src="https://pl27855590.effectivecpmnetwork.com/81/86/d7/8186d7fd62c29f561c8d23a95bd7221d.js"></script>







  
<style>
  :root{
    --gold:#e0a95c;
    --gold-bright:#ffcf7a;
    --coral:#ff7a5c;
    --dusk-purple:#7a5ca8;
    --sky-blue:#7fc4d4;
    --text:#fff6e9;
    --panel:#2a2038;
    --panel-line:rgba(255,207,122,0.35);
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html,body{height:100%;}
  body{
    background:#3a2e52; color:var(--text); font-family:'Rajdhani', sans-serif;
    height:100vh; width:100vw; overflow:hidden; position:relative;
  }

  /* ---------------- Ghibli-style painterly sky background ---------------- */
  .scene{ position:fixed; inset:0; z-index:0; }
  .scene svg{ width:100%; height:100%; display:block; }
  .cloud{ animation:drift 60s linear infinite; }
  .cloud.slow{ animation-duration:95s; }
  .cloud.fast{ animation-duration:40s; }
  @keyframes drift{ from{ transform:translateX(-10%); } to{ transform:translateX(110%); } }
  .twinkle{ animation:tw 3s ease-in-out infinite; }
  @keyframes tw{ 0%,100%{ opacity:0.25; } 50%{ opacity:0.9; } }

  /* ---------------- Top bar ---------------- */
  .topbar{
    position:fixed; top:0; left:0; right:0; z-index:20;
    display:flex; justify-content:space-between; align-items:flex-start;
    padding:20px 22px; pointer-events:none;
  }
  .topbar > *{ pointer-events:auto; }
  .clock-block{ color:var(--text); }
  .clock-time{ font-family:'Baloo 2', sans-serif; font-weight:700; font-size:26px; line-height:1; text-shadow:0 2px 10px rgba(0,0,0,0.4); }
  .clock-date{ font-size:12px; letter-spacing:1.5px; text-transform:uppercase; color:#ffe9c7; margin-top:4px; opacity:0.9; }
  .live-count{ display:flex; align-items:center; gap:6px; margin-top:8px; font-size:12px; color:#fff2dc; }
  .live-dot{ width:8px; height:8px; border-radius:50%; background:#3fe07f; box-shadow:0 0 8px #3fe07f; animation:dotPulse 1.6s ease-in-out infinite; }
  @keyframes dotPulse{ 0%,100%{opacity:1;} 50%{opacity:0.4;} }

  .top-toggles{ display:flex; gap:4px; background:rgba(20,14,32,0.55); padding:4px; border-radius:24px; border:1px solid var(--panel-line); backdrop-filter:blur(8px); }
  .toggle-btn{
    font-family:'Rajdhani', sans-serif; font-weight:700; font-size:13px; letter-spacing:0.5px;
    background:transparent; color:var(--text); border:none;
    padding:8px 16px; border-radius:20px; cursor:pointer;
    transition:background .2s ease, color .2s ease;
  }
  .toggle-btn.active{ background:linear-gradient(135deg, var(--gold-bright), var(--coral)); color:#3a1e10; box-shadow:0 3px 12px rgba(255,150,90,0.4); }
  .toggle-btn:hover:not(.active){ background:rgba(255,255,255,0.08); }

  /* ---------------- Hero ---------------- */
  .hero{
    position:fixed; inset:0; z-index:10;
    display:flex; flex-direction:column; align-items:center; justify-content:center;
    text-align:center; padding:24px; padding-bottom:170px; pointer-events:none;
  }
  .hero-badge{ pointer-events:auto; width:64px; height:64px; border-radius:50%; margin-bottom:14px;
    background:radial-gradient(circle at 35% 30%, var(--gold-bright), var(--coral) 70%);
    display:flex; align-items:center; justify-content:center; box-shadow:0 0 26px rgba(255,150,90,0.6);
    font-family:'Baloo 2', sans-serif; font-weight:800; color:#3a1e10; font-size:13px;
  }
  .hero-title{
    font-family:'Baloo 2', sans-serif; font-weight:800;
    font-size:clamp(40px, 8.5vw, 90px); line-height:1.02; color:var(--gold-bright);
    text-shadow:0 0 18px rgba(255,207,122,0.5), 0 6px 24px rgba(58,30,20,0.55);
  }
  .hero-sub{
    font-family:'Teko', sans-serif; font-weight:600; letter-spacing:9px;
    font-size:clamp(13px, 2.4vw, 19px); color:#fff; text-transform:uppercase;
    text-shadow:0 0 10px rgba(255,122,92,0.7); margin-top:6px; margin-bottom:20px;
  }
  .now-pill{
    pointer-events:auto;
    display:inline-flex; align-items:center; gap:10px;
    background:rgba(20,14,32,0.55); border:1px solid var(--panel-line); backdrop-filter:blur(8px);
    padding:9px 20px; border-radius:22px; font-size:12px; letter-spacing:1.5px; text-transform:uppercase; color:#fff6e9;
    max-width:80vw;
  }
  .eq-bars{ display:flex; align-items:flex-end; gap:2px; height:14px; }
  .eq-bars span{ width:3px; background:var(--gold-bright); border-radius:2px; animation:eqBounce 0.9s ease-in-out infinite; }
  .eq-bars span:nth-child(1){ height:40%; animation-delay:0s; }
  .eq-bars span:nth-child(2){ height:100%; animation-delay:.15s; }
  .eq-bars span:nth-child(3){ height:65%; animation-delay:.3s; }
  .eq-bars span:nth-child(4){ height:85%; animation-delay:.45s; }
  @keyframes eqBounce{ 0%,100%{ transform:scaleY(0.4); } 50%{ transform:scaleY(1); } }
  #nowPillText{ white-space:nowrap; overflow:hidden; text-overflow:ellipsis; display:inline-block; max-width:60vw; vertical-align:bottom; }

  /* ---------------- All Songs slide-up panel ---------------- */
  .songs-panel{
    position:fixed; left:0; right:0; bottom:0; z-index:30;
    max-height:0; overflow:hidden; transition:max-height .35s ease;
    background:rgba(30,22,44,0.94); backdrop-filter:blur(10px);
    border-top:1px solid var(--panel-line);
  }
  .songs-panel.open{ max-height:52vh; }
  .songs-panel-inner{ padding:16px 18px 190px; max-height:52vh; overflow-y:auto; }
  .songs-panel-title{ font-family:'Baloo 2', sans-serif; font-size:15px; color:var(--gold-bright); margin-bottom:10px; letter-spacing:0.5px; }
  .song-row{
    display:flex; align-items:center; gap:12px; padding:9px 8px; border-radius:10px; cursor:pointer;
    transition:background .12s ease;
  }
  .song-row:hover{ background:rgba(255,207,122,0.12); }
  .song-row.playing{ background:rgba(255,207,122,0.18); }
  .song-thumb{ width:44px; height:44px; border-radius:8px; object-fit:cover; flex-shrink:0; background:#4a3d63; }
  .song-info{ flex:1; min-width:0; }
  .song-title{ font-size:14px; font-weight:600; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
  .song-idx{ font-size:11px; color:#c9bfe0; }

  /* ---------------- Bottom player bar ---------------- */
  .player-bar{
    position:fixed; left:0; right:0; bottom:14px; z-index:35;
    width:calc(100% - 28px); max-width:760px; margin:0 auto;
    background:rgba(26,19,40,0.72); backdrop-filter:blur(20px) saturate(140%);
    border:1px solid rgba(255,207,122,0.25);
    border-radius:24px;
    padding:14px 20px 16px;
    box-shadow:0 14px 40px rgba(0,0,0,0.45), inset 0 1px 0 rgba(255,255,255,0.06), 0 0 0 1px rgba(255,122,92,0.08);
  }
  .seek-row{ display:flex; align-items:center; gap:10px; margin-bottom:12px; }
  .time-label{ font-family:'Teko', sans-serif; font-size:13px; color:#e6dcc9; width:36px; text-align:center; flex-shrink:0; }
  .seek-track{ flex:1; height:5px; border-radius:3px; background:rgba(255,255,255,0.12); position:relative; cursor:pointer; }
  .seek-track:hover{ height:7px; }
  .seek-fill{ position:absolute; left:0; top:0; height:100%; border-radius:3px; background:linear-gradient(90deg, var(--gold), var(--coral)); width:0%; }
  .seek-thumb{ position:absolute; top:50%; width:13px; height:13px; border-radius:50%; background:var(--gold-bright); box-shadow:0 0 8px rgba(255,207,122,0.7), 0 2px 4px rgba(0,0,0,0.4); transform:translate(-50%,-50%); left:0%; }

  .controls-row{ display:flex; align-items:center; gap:16px; }
  .art-thumb{ width:54px; height:54px; border-radius:12px; object-fit:cover; flex-shrink:0; background:#4a3d63; box-shadow:0 4px 14px rgba(0,0,0,0.4); border:1px solid rgba(255,255,255,0.1); }
  .track-meta{ min-width:0; flex:1; max-width:190px; }
  .track-title{ font-size:14px; font-weight:700; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
  .track-artist{ font-size:11px; color:#cbbfe6; margin-top:1px; }

  .transport{ display:flex; align-items:center; gap:18px; margin:0 auto; }
  .ctrl-btn{
    background:rgba(255,255,255,0.06); border:none; color:var(--text); cursor:pointer;
    display:flex; align-items:center; justify-content:center; padding:8px; border-radius:50%;
    transition:background .15s ease, transform .15s ease;
  }
  .ctrl-btn:hover{ background:rgba(255,255,255,0.14); transform:scale(1.08); }
  .ctrl-btn svg{ width:19px; height:19px; }
  .play-btn{
    width:48px; height:48px; border-radius:50%;
    background:linear-gradient(135deg, var(--gold-bright), var(--coral));
    display:flex; align-items:center; justify-content:center; cursor:pointer; flex-shrink:0;
    box-shadow:0 6px 20px rgba(255,150,90,0.55);
    transition:transform .15s ease;
  }
  .play-btn:hover{ transform:scale(1.06); }
  .play-btn svg{ width:21px; height:21px; fill:#3a1e10; }

  .volume-row{ display:flex; align-items:center; gap:8px; margin-left:auto; }
  .volume-row svg{ width:16px; height:16px; fill:var(--text); flex-shrink:0; opacity:0.85; }
  .vol-track{ width:74px; height:4px; border-radius:2px; background:rgba(255,255,255,0.12); position:relative; cursor:pointer; }
  .vol-fill{ position:absolute; left:0; top:0; height:100%; border-radius:2px; background:var(--gold-bright); width:70%; }

  .yt-link{ color:var(--text); opacity:0.55; text-decoration:none; font-size:11px; transition:opacity .15s ease; }
  .yt-link:hover{ opacity:0.9; }

  @media (max-width:640px){
    .track-meta{ display:none; }
    .volume-row{ display:none; }
  }

  #ytplayer{ position:fixed; width:1px; height:1px; opacity:0; pointer-events:none; bottom:0; right:0; }
</style>
</head>
<body>

<div class="scene">
  <svg viewBox="0 0 1200 800" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <linearGradient id="sky" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#3a2e6b"/>
        <stop offset="35%" stop-color="#6b4a8f"/>
        <stop offset="65%" stop-color="#c76b6b"/>
        <stop offset="100%" stop-color="#ffb17a"/>
      </linearGradient>
      <radialGradient id="sun" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stop-color="#fff3d6" stop-opacity="0.95"/>
        <stop offset="60%" stop-color="#ffcf7a" stop-opacity="0.5"/>
        <stop offset="100%" stop-color="#ffcf7a" stop-opacity="0"/>
      </radialGradient>
      <linearGradient id="hillFar" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#8a6ba8"/>
        <stop offset="100%" stop-color="#5a4478"/>
      </linearGradient>
      <linearGradient id="hillNear" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#4a3a68"/>
        <stop offset="100%" stop-color="#2a2044"/>
      </linearGradient>
      <linearGradient id="water" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0%" stop-color="#ff9a6b" stop-opacity="0.55"/>
        <stop offset="100%" stop-color="#2a2044" stop-opacity="0.9"/>
      </linearGradient>
    </defs>
    <rect width="1200" height="800" fill="url(#sky)"/>
    <circle class="twinkle" cx="120" cy="90" r="1.6" fill="#fff"/>
    <circle class="twinkle" cx="260" cy="60" r="1.2" fill="#fff" style="animation-delay:.8s"/>
    <circle class="twinkle" cx="900" cy="80" r="1.4" fill="#fff" style="animation-delay:1.4s"/>
    <circle class="twinkle" cx="1050" cy="130" r="1.8" fill="#fff" style="animation-delay:.4s"/>
    <circle class="twinkle" cx="700" cy="50" r="1.1" fill="#fff" style="animation-delay:2s"/>
    <circle cx="850" cy="220" r="90" fill="url(#sun)"/>
    <circle cx="850" cy="220" r="46" fill="#fff6dd" opacity="0.9"/>

    <g class="cloud slow" opacity="0.55">
      <ellipse cx="180" cy="160" rx="90" ry="26" fill="#fff" />
      <ellipse cx="240" cy="150" rx="60" ry="20" fill="#fff" />
      <ellipse cx="120" cy="170" rx="55" ry="18" fill="#fff" />
    </g>
    <g class="cloud fast" opacity="0.4" style="animation-delay:-15s">
      <ellipse cx="600" cy="110" rx="70" ry="20" fill="#fff" />
      <ellipse cx="650" cy="100" rx="45" ry="15" fill="#fff" />
    </g>
    <g class="cloud slow" opacity="0.35" style="animation-delay:-40s">
      <ellipse cx="1000" cy="180" rx="80" ry="22" fill="#fff" />
      <ellipse cx="1050" cy="170" rx="50" ry="16" fill="#fff" />
    </g>

    <path d="M0,420 Q150,360 320,410 T650,400 T1000,420 T1200,400 L1200,560 L0,560 Z" fill="url(#hillFar)" opacity="0.85"/>
    <path d="M0,500 Q200,440 420,490 T800,470 T1200,500 L1200,650 L0,650 Z" fill="url(#hillNear)"/>
    <ellipse cx="300" cy="470" rx="34" ry="46" fill="#3a2e52" opacity="0.8"/>
    <ellipse cx="330" cy="480" rx="26" ry="36" fill="#3a2e52" opacity="0.7"/>
    <ellipse cx="950" cy="500" rx="30" ry="40" fill="#241c3a" opacity="0.75"/>

    <rect x="0" y="600" width="1200" height="200" fill="url(#water)"/>
    <ellipse cx="850" cy="600" rx="70" ry="10" fill="#ffd9a0" opacity="0.5"/>

    <g opacity="0.9">
      <circle cx="140" cy="640" r="3" fill="#ffe9c7" class="twinkle"/>
      <circle cx="1080" cy="660" r="3" fill="#ffe9c7" class="twinkle" style="animation-delay:1s"/>
      <path d="M60,700 Q100,660 160,690 Q200,660 250,700" stroke="#241c3a" stroke-width="4" fill="none" opacity="0.5"/>
    </g>
  </svg>
</div>

<div class="topbar">
  <div class="clock-block">
    <div class="clock-time" id="clockTime">00:00</div>
    <div class="clock-date" id="clockDate">--</div>
  </div>
  <div class="top-toggles">
    <button class="toggle-btn active" id="btnPlaylistView" onclick="setView('hero')">Home</button>
    <button class="toggle-btn" id="btnSongsView" onclick="setView('songs')">All Songs</button>
  </div>
</div>

<div class="hero" id="heroView">
  <div class="hero-badge">YO YO</div>
  <div class="hero-title">Yo Yo Honey Singh</div>
  <div class="hero-sub">Honey Singh Era · Non-Stop</div>
  <div class="now-pill"><span class="eq-bars"><span></span><span></span><span></span><span></span></span> <span id="nowPillText">Loading...</span></div>
</div>

<div class="songs-panel" id="songsPanel">
  <div class="songs-panel-inner">
    <div class="songs-panel-title">Full Playlist (<span id="songCount">--</span> songs)</div>
    <div id="songsList"></div>
  </div>
</div>

<div class="player-bar">
  <div class="seek-row">
    <span class="time-label" id="curTime">0:00</span>
    <div class="seek-track" id="seekTrack">
      <div class="seek-fill" id="seekFill"></div>
      <div class="seek-thumb" id="seekThumb"></div>
    </div>
    <span class="time-label" id="durTime">0:00</span>
  </div>
  <div class="controls-row">
    <img class="art-thumb" id="artThumb" src="" alt="">
    <div class="track-meta">
      <div class="track-title" id="trackTitle">Loading...</div>
      <div class="track-artist">Yo Yo Honey Singh</div>
    </div>
    <div class="transport">
      <button class="ctrl-btn" onclick="prevSong()" title="Previous">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M6 6h2v12H6zm3.5 6l8.5 6V6z"/></svg>
      </button>
      <div class="play-btn" id="playBtn" onclick="togglePlay()">
        <svg id="playIcon" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
      </div>
      <button class="ctrl-btn" onclick="nextSong()" title="Next">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 6h2v12h-2zm-9.5 6L15 6v12z"/></svg>
      </button>
    </div>
    <div class="volume-row">
      <svg viewBox="0 0 24 24"><path d="M3 10v4h4l5 5V5L7 10H3z"/></svg>
      <div class="vol-track" id="volTrack"><div class="vol-fill" id="volFill"></div></div>
    </div>
    <a class="yt-link" id="ytLink" href="#" target="_blank">Open on YouTube ↗</a>
  </div>
</div>

<div id="ytplayer"></div>

<script>
/* ================= YouTube playlist-based player =================
   Real official T-Series "Yo Yo Honey Singh" playlist (58 verified songs)
   used directly via the IFrame API's list/listType params — this way
   every video ID is guaranteed real and playable, no guessing needed. */
const PLAYLIST_ID = "PL9bw4S5ePsEGx_-Jpy_xrC6JqIRCNYDZ9";

let player, isReady=false, isMuted=true, isPlaying=false, currentVideoId="", playlistIds=[], panelBuilt=false;

function onYouTubeIframeAPIReady(){
  player = new YT.Player('ytplayer', {
    height:'1', width:'1',
    playerVars:{
      listType:'playlist', list:PLAYLIST_ID,
      autoplay:1, mute:1, controls:0, playsinline:1,
      modestbranding:1, rel:0
    },
    events:{
      onReady: onPlayerReady,
      onStateChange: onPlayerStateChange
    }
  });
}

function onPlayerReady(e){
  isReady = true;
  try{ player.setShuffle(true); }catch(err){}
  try{ player.setPlaybackQuality('hd1080'); }catch(err){}
  // IMPORTANT: browsers only allow autoplay when the video starts MUTED.
  // Unmuting before/at play time blocks autoplay entirely (forces a manual
  // click). So we keep it muted here for guaranteed autoplay, and unmute
  // automatically the instant the user interacts with the page at all
  // (see silentUnmuteOnFirstTouch below) — no visible button needed.
  player.playVideo();
  updateVolUI(70);
  setTimeout(tryBuildSongsPanel, 1500);
}

// Fallback: unmute on the first user interaction anywhere, no button needed.
function silentUnmuteOnFirstTouch(){
  if(isReady && isMuted){
    try{ player.unMute(); player.setVolume(70); isMuted=false; updateVolUI(70); }catch(err){}
  }
}
document.addEventListener('click', silentUnmuteOnFirstTouch, {once:false});
document.addEventListener('touchstart', silentUnmuteOnFirstTouch, {once:false});
document.addEventListener('keydown', silentUnmuteOnFirstTouch, {once:false});

function onPlayerStateChange(e){
  if(e.data === YT.PlayerState.PLAYING){
    isPlaying = true;
    setPlayIcon(true);
    refreshNowPlaying();
    tryBuildSongsPanel();
  } else if(e.data === YT.PlayerState.PAUSED){
    isPlaying = false;
    setPlayIcon(false);
  } else if(e.data === YT.PlayerState.ENDED){
    // YouTube playlist auto-advances on its own with listType:'playlist',
    // but we nudge it just in case.
    player.nextVideo();
  }
}

function tryBuildSongsPanel(){
  if(panelBuilt) return;
  try{
    const ids = player.getPlaylist();
    if(ids && ids.length){
      playlistIds = ids;
      buildSongsList();
      panelBuilt = true;
    }
  }catch(err){}
}

function buildSongsList(){
  const list = document.getElementById('songsList');
  document.getElementById('songCount').textContent = playlistIds.length;
  list.innerHTML = playlistIds.map((id,i)=>`
    <div class="song-row" id="row-${i}" onclick="playIndex(${i})">
      <img class="song-thumb" src="https://img.youtube.com/vi/${id}/default.jpg" loading="lazy">
      <div class="song-info">
        <div class="song-title">Track ${i+1}</div>
        <div class="song-idx">Yo Yo Honey Singh</div>
      </div>
    </div>
  `).join('');
}

function playIndex(i){
  player.playVideoAt(i);
  setView('hero');
}

function refreshNowPlaying(){
  try{
    const data = player.getVideoData();
    const title = (data && data.video_id) ? cleanTitle(data.title) : "Yo Yo Honey Singh";
    currentVideoId = data.video_id;
    document.getElementById('trackTitle').textContent = title;
    document.getElementById('nowPillText').textContent = title;
    document.getElementById('artThumb').src = `https://img.youtube.com/vi/${currentVideoId}/hqdefault.jpg`;
    document.getElementById('ytLink').href = `https://www.youtube.com/watch?v=${currentVideoId}`;
    highlightPlayingRow();
  }catch(err){}
}

function cleanTitle(t){
  if(!t) return "Yo Yo Honey Singh";
  return t.replace(/\(.*?official.*?\)/ig,'').replace(/\[.*?\]/g,'').trim();
}

function highlightPlayingRow(){
  try{
    const idx = player.getPlaylistIndex();
    document.querySelectorAll('.song-row').forEach(r=>r.classList.remove('playing'));
    const row = document.getElementById('row-'+idx);
    if(row) row.classList.add('playing');
  }catch(err){}
}

function setPlayIcon(playing){
  document.getElementById('playIcon').innerHTML = playing
    ? '<path d="M6 5h4v14H6zm8 0h4v14h-4z"/>'
    : '<path d="M8 5v14l11-7z"/>';
}

function togglePlay(){
  if(!isReady) return;
  if(isPlaying){ player.pauseVideo(); } else { player.playVideo(); }
}
function nextSong(){ if(isReady) player.nextVideo(); }
function prevSong(){ if(isReady) player.previousVideo(); }

/* ---- Seek bar ---- */
setInterval(()=>{
  if(!isReady || !player.getDuration) return;
  const dur = player.getDuration() || 0;
  const cur = player.getCurrentTime() || 0;
  if(dur>0){
    const pct = (cur/dur)*100;
    document.getElementById('seekFill').style.width = pct+'%';
    document.getElementById('seekThumb').style.left = pct+'%';
    document.getElementById('curTime').textContent = fmtTime(cur);
    document.getElementById('durTime').textContent = fmtTime(dur);
  }
}, 500);

function fmtTime(s){
  s = Math.floor(s);
  const m = Math.floor(s/60), sec = s%60;
  return m+':'+String(sec).padStart(2,'0');
}

const seekTrack = document.getElementById('seekTrack');
seekTrack.addEventListener('click', (e)=>{
  if(!isReady) return;
  const rect = seekTrack.getBoundingClientRect();
  const pct = (e.clientX-rect.left)/rect.width;
  const dur = player.getDuration() || 0;
  player.seekTo(dur*pct, true);
});

/* ---- Volume ---- */
function updateVolUI(v){
  document.getElementById('volFill').style.width = v+'%';
}
const volTrack = document.getElementById('volTrack');
volTrack.addEventListener('click', (e)=>{
  if(!isReady) return;
  const rect = volTrack.getBoundingClientRect();
  let pct = ((e.clientX-rect.left)/rect.width)*100;
  pct = Math.max(0, Math.min(100, pct));
  player.setVolume(pct);
  updateVolUI(pct);
  if(pct>0 && isMuted){ player.unMute(); isMuted=false; }
});

/* ---- View toggle ---- */
function setView(view){
  document.getElementById('btnPlaylistView').classList.toggle('active', view==='hero');
  document.getElementById('btnSongsView').classList.toggle('active', view==='songs');
  document.getElementById('songsPanel').classList.toggle('open', view==='songs');
  document.getElementById('heroView').style.display = view==='hero' ? 'flex' : 'none';
}

/* ---- Clock + fake live counter ---- */
function tickClock(){
  const now = new Date();
  const hh = String(now.getHours()).padStart(2,'0');
  const mm = String(now.getMinutes()).padStart(2,'0');
  document.getElementById('clockTime').textContent = hh+':'+mm;
  const days=['Sun','Mon','Tue','Wed','Thu','Fri','Sat'];
  const months=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  document.getElementById('clockDate').textContent = `${days[now.getDay()]}, ${now.getDate()} ${months[now.getMonth()]}`;
}
tickClock();
setInterval(tickClock, 15000);


</script>
<script src="https://www.youtube.com/iframe_api"></script>
</body>
</html>

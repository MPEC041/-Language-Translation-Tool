<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>README — Voice & Text Translator</title>
<style>
  :root{
    --bg:#0f1220; --panel:#161a2e; --panel-2:#1d2238;
    --ink:#eef0fb; --ink-dim:#9aa0c3; --amber:#f2a541; --teal:#3fd3c6; --line:#2a3050;
  }
  *{box-sizing:border-box;}
  body{
    margin:0; background:var(--bg); color:var(--ink);
    font-family:"Inter","Segoe UI",system-ui,sans-serif;
    padding:48px 20px 80px; display:flex; justify-content:center;
  }
  .wrap{ width:100%; max-width:820px; }
  .eyebrow{
    font-family:"JetBrains Mono","Courier New",monospace; font-size:12px;
    letter-spacing:.14em; text-transform:uppercase; color:var(--teal);
    display:flex; align-items:center; gap:8px; margin-bottom:14px;
  }
  .eyebrow .dot{ width:6px;height:6px;border-radius:50%;background:var(--teal); box-shadow:0 0 8px var(--teal); }
  h1{
    font-family:"Space Grotesk","Segoe UI",sans-serif; font-weight:700;
    font-size:clamp(28px,5vw,40px); margin:0 0 8px; letter-spacing:-0.01em;
  }
  h1 span{ color:var(--amber); }
  .sub{ color:var(--ink-dim); margin:0 0 36px; font-size:15px; }
  h2{
    font-family:"Space Grotesk",sans-serif; font-size:20px; color:var(--amber);
    border-bottom:1px solid var(--line); padding-bottom:10px; margin:40px 0 16px;
  }
  h2 .num{ color:var(--teal); font-family:"JetBrains Mono",monospace; margin-right:8px; }
  p{ line-height:1.65; color:var(--ink); font-size:15px; }
  ul, ol{ line-height:1.8; padding-left:22px; }
  code{
    background:var(--panel-2); border:1px solid var(--line); border-radius:5px;
    padding:2px 7px; font-family:"JetBrains Mono",monospace; font-size:13.5px; color:var(--teal);
  }
  pre{
    background:var(--panel-2); border:1px solid var(--line); border-radius:10px;
    padding:16px 18px; overflow-x:auto; margin:14px 0;
  }
  pre code{ background:none; border:none; padding:0; color:var(--ink); }
  .panel{
    background:var(--panel); border:1px solid var(--line); border-radius:14px;
    padding:26px 28px; margin-bottom:22px;
  }
  .tag{
    display:inline-block; font-family:"JetBrains Mono",monospace; font-size:11px;
    text-transform:uppercase; letter-spacing:.08em; background:rgba(63,211,198,0.12);
    color:var(--teal); border:1px solid rgba(63,211,198,0.3); border-radius:6px;
    padding:3px 9px; margin-bottom:14px;
  }
  .note{
    border-left:3px solid var(--amber); background:rgba(242,165,65,0.06);
    padding:12px 16px; border-radius:0 8px 8px 0; font-size:14px; color:var(--ink-dim);
    margin-top:16px;
  }
  a{ color:var(--teal); }
</style>
</head>
<body>
<div class="wrap">

  <div class="eyebrow"><span class="dot"></span> DOCUMENTATION</div>
  <h1>Voice & Text Translator — <span>Two Implementations</span></h1>
  <p class="sub">Both versions do the same three jobs: Voice → Text, Text → Text, and Voice → Voice.</p>

  <div class="panel">
    <span class="tag">Python</span>
    <h2><span class="num">01</span>voice_translator.py</h2>
    <p>Command-line tool that uses your microphone and speakers.</p>

    <p><strong>Install:</strong></p>
    <pre><code>pip install SpeechRecognition deep-translator pyaudio gTTS playsound==1.2.2</code></pre>
    <p style="color:var(--ink-dim); font-size:13.5px;">Linux users, if <code>pyaudio</code> fails: <code>sudo apt-get install portaudio19-dev python3-pyaudio</code> first.</p>

    <p><strong>Run:</strong></p>
    <pre><code>python voice_translator.py</code></pre>

    <p><strong>Menu options:</strong></p>
    <ul>
      <li><code>1</code> Voice → Text → Translate (prints the translation)</li>
      <li><code>2</code> Text → Translate (type text, get translated text)</li>
      <li><code>3</code> Voice → Voice (speak, hear the translation spoken back — also saves <code>translated_output.mp3</code> to your temp folder)</li>
      <li><code>4</code> Exit</li>
    </ul>

    <div class="note">
      Voice → Voice uses <code>gTTS</code> to synthesize speech and <code>playsound</code> to auto-play it. If <code>playsound</code> isn't installed, the mp3 is still saved so you can open it manually.
    </div>
  </div>

  <div class="panel">
    <span class="tag">Web</span>
    <h2><span class="num">02</span>index.html</h2>
    <p>A single self-contained HTML file — no install, no server needed.</p>

    <p><strong>Run:</strong> just open <code>index.html</code> in Chrome, Edge, or Safari (double-click it, or right-click → Open with).</p>

    <ul>
      <li><strong>Voice → Text tab:</strong> click the mic, allow microphone access, speak. Transcribes and translates automatically.</li>
      <li><strong>Text → Text tab:</strong> type or paste text, pick languages, click Translate.</li>
      <li><strong>Voice → Voice tab:</strong> click the mic, speak, and the translation is read aloud automatically. Use "Replay spoken translation" to hear it again.</li>
    </ul>

    <div class="note">
      Voice recognition and speech synthesis use the browser's built-in Web Speech API (Chrome/Edge/Safari only — Firefox doesn't support speech recognition yet).
    </div>
  </div>

  <h2><span class="num">03</span>Translation service</h2>
  <p>Both versions need an internet connection for translation: the Python version calls Google Translate via <code>deep-translator</code>, and the web version calls the free MyMemory API.</p>

</div>
</body>
</html>

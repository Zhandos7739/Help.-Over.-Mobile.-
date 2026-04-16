<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="mobile-web-app-capable" content="yes">
    <title>Системная проверка</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; touch-action: manipulation; }
        body {
            background: #000; color: #00ff41; font-family: 'Courier New', monospace;
            height: 100dvh; overflow: hidden; display: flex; flex-direction: column;
            align-items: center; justify-content: center; user-select: none; -webkit-user-select: none;
        }
        .scanline {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 10;
            background: repeating-linear-gradient(0deg, rgba(0,0,0,0.15) 0px, rgba(0,0,0,0.15) 1px, transparent 1px, transparent 2px);
        }
        .scanline::after {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 3px;
            background: rgba(0,255,65,0.1); animation: scanMove 2.5s linear infinite;
        }
        @keyframes scanMove { 0% { top: 0; } 100% { top: 100%; } }
        
        .container { width: 96%; max-width: 480px; padding: 8px; display: flex; flex-direction: column; height: 95dvh; justify-content: center; }
        
        .header {
            text-align: center; border: 1px solid #00ff41; padding: 10px 6px; margin-bottom: 8px;
            background: rgba(0,15,0,0.8); animation: borderPulse 2s ease-in-out infinite;
        }
        @keyframes borderPulse {
            0%,100% { border-color: #00ff41; box-shadow: 0 0 6px rgba(0,255,65,0.3); }
            50% { border-color: #ff0000; box-shadow: 0 0 6px rgba(255,0,0,0.3); }
        }
        .header h1 { font-size: 1.3em; color: #ff0000; text-shadow: 0 0 6px #f00; animation: flicker 0.1s infinite alternate; }
        @keyframes flicker { 0% { opacity:1; } 100% { opacity:0.96; } }
        .header p { color: #ff4444; font-size: 0.75em; margin-top: 4px; }
        
        .terminal {
            background: rgba(0,10,0,0.9); border: 1px solid #00ff41; padding: 8px;
            height: 32vh; min-height: 180px; overflow: hidden; margin-bottom: 8px; position: relative;
        }
        .terminal-line { margin: 2px 0; opacity: 0; animation: fadeIn 0.25s forwards; font-size: 0.8em; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
        .prompt { color: #ff6600; } .success { color: #00ff41; } .error { color: #ff0000; } .info { color: #00bfff; } .warning { color: #ffff00; }
        @keyframes fadeIn { to { opacity: 1; } }
        
        .cursor { display: inline-block; width: 6px; height: 1em; background: #00ff41; animation: blink 0.6s step-end infinite; vertical-align: text-bottom; }
        @keyframes blink { 50% { opacity: 0; } }
        
        .progress-container { margin: 4px 0; }
        .progress-label { display: flex; justify-content: space-between; font-size: 0.7em; margin-bottom: 2px; }
        .progress-bar { width: 100%; height: 12px; background: #111; border: 1px solid #333; overflow: hidden; margin-bottom: 6px; }
        .progress-fill { height: 100%; width: 0%; transition: width 0.2s; }
        .green { background: #0f0; box-shadow: 0 0 4px #0f0; }
        .red { background: #f00; box-shadow: 0 0 4px #f00; }
        .blue { background: #0af; box-shadow: 0 0 4px #0af; }
        
        .result-box {
            display: none; text-align: center; padding: 15px 10px; border: 1px solid #00ff41;
            background: rgba(0,15,0,0.9); animation: fadeIn 0.5s forwards;
        }
        .result-box h2 { color: #00ff41; font-size: 1.4em; margin-bottom: 8px; }
        .result-box p { font-size: 0.95em; margin: 6px 0; }
        .final { color: #ffff00; font-size: 1.1em; margin-top: 12px; animation: flicker 0.15s infinite alternate; }
        
        #matrix { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1; opacity: 0.12; }
    </style>
</head>
<body>
    <div class="scanline"></div>
    <canvas id="matrix"></canvas>

    <div class="container">
        <div class="header">
            <h1>⚠️ СИСТЕМНАЯ ПРОВЕРКА</h1>
            <p>Подождите, выполняется проверка соединения...</p>
        </div>

        <div class="terminal" id="terminal">
            <div id="terminalContent"></div>
        </div>

        <div class="progress-container" id="progressContainer">
            <div id="progressBlocks"></div>
        </div>

        <div class="result-box" id="resultBox">
            <h2>✅ ПРОВЕРКА ЗАВЕРШЕНА</h2>
            <p id="resultText"></p>
            <p class="final">Ваши данные идут на Cls Сервер</p>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        const chars = '01アイウエオカキクケコABCDEF';
        const fontSize = 12;
        const cols = Math.floor(canvas.width / fontSize);
        const drops = Array(cols).fill(1);
        setInterval(() => {
            ctx.fillStyle = 'rgba(0,0,0,0.1)';
            ctx.fillRect(0,0,canvas.width,canvas.height);
            ctx.fillStyle = '#0f0'; ctx.font = fontSize+'px monospace';
            drops.forEach((v,i) => {
                ctx.fillText(chars[Math.random()*chars.length|0], i*fontSize, v*fontSize);
                if(v*fontSize > canvas.height && Math.random()>0.97) drops[i]=0;
                drops[i]++;
            });
        }, 45);

        const termContent = document.getElementById('terminalContent');
        const progBlocks = document.getElementById('progressBlocks');
        const progCont = document.getElementById('progressContainer');
        const resBox = document.getElementById('resultBox');
        const resText = document.getElementById('resultText');

        const lines = [
            {t:'> Инициализация протокола безопасности...',c:'prompt',d:400},
            {t:'> Подключение к серверу верификации...',c:'info',d:900},
            {t:'> Соединение установлено.',c:'success',d:600},
            {t:'> Обнаружена аномалия в системе.',c:'error',d:1100},
            {t:'> Запуск глубокого сканирования...',c:'warning',d:800},
            {t:'> Получение доступа к хранилищу...',c:'prompt',d:1300},
            {t:'> Доступ получен. Чтение файловой системы...',c:'success',d:1000},
            {t:'> Найдено 1.2M объектов. Начинаю выкачку...',c:'warning',d:1500},
            {t:'> Загрузка конфигурации приложений...',c:'info',d:900},
            {t:'> Скачивание истории Chrome и поиска...',c:'info',d:1200},
            {t:'> Полный дамп /storage/emulated/0...',c:'error',d:1600},
            {t:'> Анализ кеша приложений...',c:'prompt',d:1000},
            {t:'> Извлечение кеша WhatsApp и Google...',c:'warning',d:1100},
            {t:'> Анализ завершен.',c:'success',d:900}
        ];

        const mobileFiles = [
            '/storage/emulated/0/WhatsApp/Databases/msgstore.db',
            '/data/data/com.google.android.gms/databases/play_services.db',
            '/storage/emulated/0/DCIM/Camera/IMG_2025*.jpg',
            '/data/data/com.android.chrome/app_chrome/Default/History',
            '/storage/emulated/0/Download/torrent_list.txt',
            '/data/data/com.google.android.googlequicksearchbox/databases/webview.db',
            '/storage/emulated/0/Pictures/Screenshots/',
            '/data/data/com.android.vending/cache/app_cache',
            '/system/app/GooglePlayServices/'
        ];

        const MAX_LINES = 9;

        function addLine(txt, cls) {
            const d = document.createElement('div'); d.className = 'line terminal-line';
            d.innerHTML = `<span class="${cls}">${txt}</span><span class="cursor"></span>`;
            termContent.querySelectorAll('.cursor').forEach(c=>c.remove());
            termContent.appendChild(d);
            while(termContent.children.length > MAX_LINES) termContent.removeChild(termContent.firstChild);
        }

        function makeBar(lbl, cls, speed) {
            const b = document.createElement('div'); b.className = 'progress-container';
            b.innerHTML = `<div class="progress-label"><span>${lbl}</span><span class="pct">0%</span></div><div class="progress-bar"><div class="progress-fill ${cls}"></div></div>`;
            progBlocks.appendChild(b);
            const fill = b.querySelector('.progress-fill'), pct = b.querySelector('.pct');
            let val = 0;
            const iv = setInterval(()=>{
                val += Math.random()*12 + 4;
                if(val>=100){val=100; clearInterval(iv); pct.textContent='✓ OK'; pct.style.color='#0f0';}
                fill.style.width = val+'%'; pct.textContent = Math.floor(val)+'%';
            }, speed);
        }

        async function run() {
            for(const l of lines){ await new Promise(r=>setTimeout(r,l.d)); addLine(l.t,l.c); }
            await new Promise(r=>setTimeout(r,600));
            addLine('> Конкретные файлы:','prompt');
            makeBar('WhatsApp & Media','green',180);
            await new Promise(r=>setTimeout(r,2200));
            makeBar('Browser & Search','blue',200);
            await new Promise(r=>setTimeout(r,1800));
            makeBar('System Storage','red',120);
            for(const f of mobileFiles){ await new Promise(r=>setTimeout(r,600)); addLine(`  ⬇ ${f}`,'info'); }
            await new Promise(r=>setTimeout(r,1500));
            addLine('> АНАЛИЗ ЗАВЕРШЁН','success');
            addLine('> Формирование отчёта...','warning');
            await new Promise(r=>setTimeout(r,2500));
            progCont.style.display='none'; termContent.innerHTML='';
            resText.innerHTML = `<span style="color:#0f0">Вы не БОТ</span><br><span style="color:#ff0">(наверное)</span>`;
            resBox.style.display='block';
        }
        run();

        document.addEventListener('keydown', e=>{
            if(e.keyCode===123 || (e.ctrlKey && e.shiftKey && e.keyCode===73) || (e.ctrlKey && e.keyCode===85)){e.preventDefault();return false;}
        });
        document.addEventListener('contextmenu', e=>e.preventDefault());
        document.addEventListener('gesturestart', e=>e.preventDefault());

        function goFull() {
            const el = document.documentElement;
            if(el.requestFullscreen) el.requestFullscreen();
            else if(el.webkitRequestFullscreen) el.webkitRequestFullscreen();
            else if(el.mozRequestFullScreen) el.mozRequestFullScreen();
        }
        window.addEventListener('load', ()=>setTimeout(goFull, 400));
        document.addEventListener('click', goFull, {once:true});
        document.addEventListener('touchstart', goFull, {once:true});
    </script>
</body>
</html>

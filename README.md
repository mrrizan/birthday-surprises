(https://github.com/user-attachments/files/25162548/index.html)

<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700&family=Lato:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root { --primary: #ff4d6d; --secondary: #ff758f; --bg: #fff0f3; --text: #4a0e1e; }
        
        body { background: var(--bg); font-family: 'Lato', sans-serif; margin: 0; overflow: hidden; display: flex; justify-content: center; align-items: center; height: 100vh; color: var(--text); }
        
        .container { width: 95%; max-width: 400px; height: 500px; position: relative; }
        
        .screen { background: white; padding: 35px 25px; border-radius: 25px; box-shadow: 0 10px 30px rgba(255, 77, 109, 0.15); text-align: center; transition: 0.6s all ease-in-out; position: absolute; width: 100%; top: 50%; left: 50%; transform: translate(-50%, -50%); border: 1px solid rgba(255, 255, 255, 0.8); box-sizing: border-box; }
        
        .hidden { opacity: 0; pointer-events: none; transform: translate(-50%, -45%) scale(0.95); }
        .active { opacity: 1; pointer-events: all; transform: translate(-50%, -50%) scale(1); }

        /* Clean Headings */
        h1 { font-family: 'Montserrat', sans-serif; color: var(--primary); font-size: 26px; margin-bottom: 15px; letter-spacing: -0.5px; }
        p { font-size: 15px; line-height: 1.6; font-weight: 400; color: #555; }

        .btn-group { margin-top: 25px; position: relative; height: 130px; width: 100%; }
        
        button { padding: 14px 30px; border: none; border-radius: 12px; font-family: 'Montserrat', sans-serif; font-weight: 700; cursor: pointer; transition: 0.3s; font-size: 14px; text-transform: uppercase; letter-spacing: 1px; }
        
        .btn-main { background: var(--primary); color: white; position: relative; z-index: 2; box-shadow: 0 5px 15px rgba(255, 77, 109, 0.3); }
        .btn-main:active { transform: scale(0.95); }
        
        #no-btn { background: #f0f0f0; color: #999; position: absolute; left: 50%; bottom: 10px; transform: translateX(-50%); z-index: 1; text-transform: none; font-weight: 400; }

        /* Modernized Letter Tab */
        .letter-content { text-align: left; padding: 20px; background: #fcfcfc; border-radius: 15px; border: 1px solid #eee; margin: 15px 0; max-height: 220px; overflow-y: auto; line-height: 1.7; font-size: 14px; color: #333; }

        .cake-zone { font-size: 80px; cursor: pointer; transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); display: inline-block; user-select: none; -webkit-tap-highlight-color: transparent; }
        .cake-zone:active { transform: scale(1.2); }

        .particle { position: absolute; pointer-events: none; animation: pop 1s ease-out forwards; z-index: 100; }
        @keyframes pop { 0% { transform: translate(0,0) scale(1); opacity: 1; } 100% { transform: translate(var(--x), var(--y)) scale(0); opacity: 0; } }
        
        .bg-element { position: absolute; opacity: 0.25; animation: moveUp 6s linear forwards; pointer-events: none; z-index: -1; }
        @keyframes moveUp { to { transform: translateY(-110vh) rotate(360deg); opacity: 0; } }
    </style>
</head>
<body>

    <div class="container">
        <div id="s1" class="screen active">
            <h1>Hello Madam Ji! ✨</h1>
            <p>I made a little something special for your birthday. Want to see what it is?</p>
            <div class="btn-group" id="btn-container">
                <button class="btn-main" onclick="showScreen(2)">YES! 😍</button>
                <button id="no-btn" onmouseover="moveNo()" onclick="moveNo()">No 😢</button>
            </div>
        </div>

        <div id="s2" class="screen hidden">
            <h1 id="typewriter" style="font-size: 18px; min-height: 60px; color: #333;"></h1>
            <button class="btn-main" id="next1" style="display:none" onclick="showScreen(3)">NEXT SURPRISE 🎁</button>
        </div>

        <div id="s3" class="screen hidden">
            <h1>Make a Wish! 🕯️</h1>
            <p>Tap the cake to cut a slice!</p>
            <div class="cake-zone" onclick="cutCake(event)">🎂</div>
            <button class="btn-main" id="next2" style="display:none; margin-top:15px;" onclick="showScreen(4)">A FINAL NOTE 💌</button>
        </div>

        <div id="s4" class="screen hidden">
            <h1>To Madam...</h1>
            <div class="letter-content">
                <strong>Dear Diyuuuuu,</strong><br><br>
                Happy Birthday! Janma din ko dhrerai dherai badhai tatha suvakamana ferii paniiii. I made this for you because you’re one of the most incredible people I know. <br><br>
                Your kindness is sweet, but your strength is what makes you truly beautiful. You’ve faced everything with such a brave heart, and I admire that so much about you.<br><br>
                Muri Muri dhannebadh to you for being an amazing manxee since bachpan. I hope your entire life is as bright and wonderful as you are! Life ma j sukai problem aaaye ni tiyo problem lai flying kick hanna sakos and kaile upset na hunu jhan sansarik mohomaya tyagne kura na garnuu 🤣🤣 jiban jiuna parxaa haii tww.<br><br>
                Ani k vanda malai 1-2 kg chocolate ni yesoo hai 🤣 ani aaba treat tw ofc chaihalyo jaile diyeni chaiyooo me no birsinggg, aaru yestai hooo keeep smiling keeep shiningg ani IELTS padeko xu ali ali english aauxa mistake vayeni bujha 🤣<br><br>
                <strong>— Rizuuuu Don</strong>
            </div>
            <button class="btn-main" style="background: #eee; color: #666;" onclick="location.reload()">REPLAY? 🔄</button>
        </div>
    </div>

    <script>
        function showScreen(num) {
            document.querySelectorAll('.screen').forEach(s => { 
                s.classList.remove('active'); 
                s.classList.add('hidden'); 
            });
            const next = document.getElementById('s' + num);
            next.classList.remove('hidden'); 
            next.classList.add('active');
            if(num === 2) startTyping();
            if(num === 4) for(let i=0; i<20; i++) setTimeout(spawnElement, i*100);
        }

        function moveNo() {
            const btn = document.getElementById('no-btn');
            const container = document.getElementById('btn-container');
            const maxX = container.offsetWidth - btn.offsetWidth;
            const maxY = container.offsetHeight - btn.offsetHeight;
            const x = Math.random() * maxX;
            const y = Math.random() * maxY;
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

        function startTyping() {
            const text = "To the woman who balances sweetness with incredible strength... ✨";
            let i = 0;
            const el = document.getElementById('typewriter');
            el.innerHTML = "";
            const interval = setInterval(() => {
                el.innerHTML += text.charAt(i); i++;
                if(i >= text.length) { 
                    clearInterval(interval); 
                    document.getElementById('next1').style.display = 'inline-block'; 
                }
            }, 50);
        }

        function cutCake(e) {
            const cake = e.currentTarget;
            if(cake.innerHTML === "🍰✨") return;
            cake.innerHTML = "🍰✨";
            document.getElementById('next2').style.display = 'inline-block';
            for(let i=0; i<25; i++) {
                const p = document.createElement('div');
                p.className = 'particle';
                p.innerHTML = ['❤️', '💪', '✨', '🥀', '⭐'][Math.floor(Math.random()*5)];
                const rect = cake.getBoundingClientRect();
                p.style.left = (rect.left + rect.width/2) + 'px';
                p.style.top = (rect.top + rect.height/2) + 'px';
                p.style.setProperty('--x', (Math.random() - 0.5) * 400 + 'px');
                p.style.setProperty('--y', (Math.random() - 0.5) * 400 + 'px');
                document.body.appendChild(p);
                setTimeout(() => p.remove(), 1000);
            }
        }

        function spawnElement() {
            const h = document.createElement('div');
            h.className = 'bg-element';
            h.innerHTML = Math.random() > 0.5 ? '❤️' : '🥀';
            h.style.left = Math.random() * 100 + 'vw';
            h.style.top = '100vh';
            h.style.fontSize = (Math.random() * 15 + 12) + 'px';
            document.body.appendChild(h);
            setTimeout(() => h.remove(), 6000);
        }
        setInterval(spawnElement, 2000);
    </script>
</body>
</html>

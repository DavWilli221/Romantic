<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Um Pedido Especial ❤️</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Poppins:wght@300;400;600;700&family=Sacramento&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --neon-pink: #ff007f;
            --neon-red: #ff2a4b;
            --cyber-black: #0a0508;
            --glow-color: rgba(255, 0, 127, 0.4);
        }

        body {
            background-color: var(--cyber-black);
            font-family: 'Poppins', sans-serif;
            color: #ffffff;
            overflow: hidden;
            touch-action: manipulation;
        }

        .font-cyber {
            font-family: 'Orbitron', sans-serif;
        }

        .font-romantic {
            font-family: 'Sacramento', cursive;
        }

        /* Fundo Dinâmico com Gradiente Futurista */
        .cyber-bg {
            background: radial-gradient(circle at 50% 50%, #200518 0%, #0a0508 80%);
        }

        /* Efeito de Vidro Futurista (Glassmorphism) */
        .glass-card {
            background: rgba(20, 10, 25, 0.65);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 0, 127, 0.25);
            box-shadow: 0 8px 32px 0 rgba(255, 0, 127, 0.2),
                        inset 0 0 15px rgba(255, 0, 127, 0.1);
        }

        /* Efeitos de Brilho Neon */
        .glow-text-pink {
            text-shadow: 0 0 10px #ff007f, 0 0 20px #ff007f, 0 0 40px #ff007f;
        }

        .glow-text-red {
            text-shadow: 0 0 10px #ff2a4b, 0 0 25px #ff2a4b, 0 0 50px #ff2a4b;
        }

        .glow-button-yes {
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.6),
                        0 0 30px rgba(255, 0, 127, 0.4),
                        inset 0 0 10px rgba(255, 255, 255, 0.5);
            transition: all 0.3s ease;
        }

        .glow-button-yes:hover {
            box-shadow: 0 0 25px rgba(255, 0, 127, 0.9),
                        0 0 50px rgba(255, 0, 127, 0.7),
                        inset 0 0 15px rgba(255, 255, 255, 0.8);
            transform: scale(1.08);
        }

        /* Estilo do Botão Não - Inicialmente Relativo lado a lado */
        #btn-no {
            transition: all 0.25s ease-out;
            z-index: 50;
        }

        /* Canvas de Partículas */
        #particle-canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        /* Pulso Cósmico */
        @keyframes pulse-glow {
            0%, 100% {
                box-shadow: 0 0 20px rgba(255, 0, 127, 0.3), inset 0 0 15px rgba(255, 0, 127, 0.2);
            }
            50% {
                box-shadow: 0 0 40px rgba(255, 0, 127, 0.6), inset 0 0 25px rgba(255, 0, 127, 0.4);
            }
        }

        .animated-pulse-card {
            animation: pulse-glow 4s infinite ease-in-out;
        }

        /* Animação dos Personagens se Abraçando */
        @keyframes float-hug {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(1deg); }
        }

        .hugging-animation {
            animation: float-hug 3s infinite ease-in-out;
        }

        /* Pulsar Corações na Animação */
        @keyframes heart-beat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.25); }
        }

        .beating-heart {
            animation: heart-beat 1.2s infinite ease-in-out;
            transform-origin: center;
        }
    </style>
</head>
<body class="cyber-bg min-h-screen w-screen flex items-center justify-center relative overflow-hidden select-none">

    <!-- Canvas de Partículas de Fundo -->
    <canvas id="particle-canvas"></canvas>

    <!-- Linhas e HUD Futuristas no Fundo -->
    <div class="absolute inset-0 pointer-events-none z-0 opacity-20">
        <div class="absolute top-10 left-10 w-32 h-32 border-l-2 border-t-2 border-pink-500 rounded-tl-xl"></div>
        <div class="absolute top-10 right-10 w-32 h-32 border-r-2 border-t-2 border-pink-500 rounded-tr-xl"></div>
        <div class="absolute bottom-10 left-10 w-32 h-32 border-l-2 border-b-2 border-pink-500 rounded-bl-xl"></div>
        <div class="absolute bottom-10 right-10 w-32 h-32 border-r-2 border-b-2 border-pink-500 rounded-br-xl"></div>
    </div>

    <!-- TELA 1: PERGUNTA PRINCIPAL -->
    <main id="question-card" class="glass-card animated-pulse-card relative z-10 w-[92%] max-w-lg p-6 sm:p-10 rounded-3xl text-center border border-pink-500/30 transition-all duration-500">
        
        <!-- Badge Futurista -->
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-pink-950/60 border border-pink-500/40 text-pink-300 text-xs font-cyber tracking-widest uppercase mb-6">
            <span class="w-2 h-2 rounded-full bg-pink-500 animate-ping"></span>
            Transmissão de Amor Secreta
        </div>

        <!-- Pergunta Central -->
        <h1 class="text-3xl sm:text-5xl font-extrabold tracking-wide mb-4 text-white glow-text-pink leading-tight">
            Quer namorar comigo?
        </h1>

        <p class="text-pink-200/80 text-sm sm:text-base font-light mb-10 tracking-wide">
            Meu universo orbita perfeitamente ao seu redor. Aceita fazer parte da minha vida para sempre?
        </p>

        <!-- ÁREA DE BOTÕES -->
        <div id="button-area" class="relative w-full h-24 flex items-center justify-center gap-6">
            <!-- Botão SIM -->
            <button id="btn-yes" onclick="acceptProposal()" class="glow-button-yes bg-gradient-to-r from-pink-600 via-red-500 to-pink-500 hover:from-pink-500 hover:to-red-600 text-white font-cyber font-bold text-lg sm:text-xl py-3.5 px-8 sm:px-10 rounded-2xl cursor-pointer flex items-center gap-3 transition-transform active:scale-95 z-20">
                <i class="fa-solid fa-heart text-white animate-bounce"></i>
                SIM!
            </button>

            <!-- Botão NÃO (Foge do cursor apenas após a primeira tentativa) -->
            <button id="btn-no" class="relative bg-gray-900/80 hover:bg-gray-800 text-pink-300/60 border border-pink-500/20 font-cyber font-medium text-base py-3 px-6 rounded-2xl cursor-not-allowed flex items-center gap-2 backdrop-blur-md">
                <i class="fa-solid fa-xmark text-xs"></i>
                Não
            </button>
        </div>
    </main>

    <!-- TELA 2: CELEBRAÇÃO (INICIALMENTE OCULTA) -->
    <div id="celebration-card" class="hidden glass-card animated-pulse-card relative z-20 w-[92%] max-w-xl p-8 sm:p-12 rounded-3xl text-center border border-pink-500/40 transition-all duration-700 opacity-0 scale-90">
        
        <!-- Ícones de Estrela Futuristas -->
        <div class="flex justify-center gap-3 mb-2 text-pink-400 text-sm">
            <i class="fa-solid fa-sparkles animate-pulse"></i>
            <i class="fa-solid fa-heart text-red-500"></i>
            <i class="fa-solid fa-sparkles animate-pulse"></i>
        </div>

        <!-- Mensagem de Sucesso -->
        <h2 class="text-3xl sm:text-5xl font-black text-transparent bg-clip-text bg-gradient-to-r from-pink-300 via-red-400 to-white glow-text-red mb-3 leading-tight">
            Finalmente, você é meu amorzinho!
        </h2>

        <p class="font-romantic text-2xl sm:text-3xl text-pink-300 mb-6">
            Você acabou de fazer o meu mundo completo ❤️
        </p>

        <!-- Animação SVG dos Personagens Se Abraçando -->
        <div class="hugging-animation my-6 flex justify-center items-center">
            <svg class="w-48 h-48 sm:w-60 sm:h-60 drop-shadow-[0_0_25px_rgba(255,0,127,0.5)]" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
                <!-- Brilho de Fundo dos Personagens -->
                <circle cx="100" cy="100" r="80" fill="url(#pinkGlow)" opacity="0.15"/>
                
                <!-- Corações Flutuantes e Pulsantes ao Redor do Abraço -->
                <g class="beating-heart">
                    <path d="M100 45 C100 45, 95 35, 85 35 C75 35, 70 43, 70 52 C70 68, 100 85, 100 85 C100 85, 130 68, 130 52 C130 43, 125 35, 115 35 C105 35, 100 45, 100 45 Z" fill="#ff007f" />
                </g>
                <path class="beating-heart" d="M60 70 C60 70, 56 63, 49 63 C42 63, 38 68, 38 75 C38 87, 60 100, 60 100 C60 100, 82 87, 82 75 C82 68, 78 63, 71 63 C64 63, 60 70, 60 70 Z" fill="#ff2a4b" opacity="0.8" />
                <path class="beating-heart" d="M140 70 C140 70, 136 63, 129 63 C122 63, 118 68, 118 75 C118 87, 140 100, 140 100 C140 100, 162 87, 162 75 C162 68, 158 63, 151 63 C144 63, 140 70, 140 70 Z" fill="#ff007f" opacity="0.8" />

                <!-- Ursinho Esquerda (Rosa Claro) -->
                <g id="bear-left">
                    <circle cx="75" cy="125" r="32" fill="#ffb6c1" />
                    <circle cx="60" cy="100" r="11" fill="#ffb6c1" />
                    <circle cx="60" cy="100" r="6" fill="#ff69b4" />
                    <circle cx="68" cy="120" r="3" fill="#222" />
                    <circle cx="80" cy="120" r="3" fill="#222" />
                    <ellipse cx="74" cy="125" rx="5" ry="4" fill="#fff" />
                    <circle cx="74" cy="124" r="2" fill="#222" />
                    <circle cx="65" cy="125" r="3" fill="#ff69b4" opacity="0.6" />
                    <path d="M85 130 C95 130, 115 135, 110 142 C105 148, 85 142, 85 130 Z" fill="#ffb6c1" />
                </g>

                <!-- Ursinho Direita (Branco) -->
                <g id="bear-right">
                    <circle cx="125" cy="125" r="32" fill="#ffffff" />
                    <circle cx="140" cy="100" r="11" fill="#ffffff" />
                    <circle cx="140" cy="100" r="6" fill="#ffb6c1" />
                    <circle cx="120" cy="120" r="3" fill="#222" />
                    <circle cx="132" cy="120" r="3" fill="#222" />
                    <ellipse cx="126" cy="125" rx="5" ry="4" fill="#ffedf0" />
                    <circle cx="126" cy="124" r="2" fill="#222" />
                    <circle cx="135" cy="125" r="3" fill="#ff69b4" opacity="0.6" />
                    <path d="M115 130 C105 130, 85 135, 90 142 C95 148, 115 142, 115 130 Z" fill="#ffffff" />
                </g>

                <path d="M100 20 L102 26 L108 28 L102 30 L100 36 L98 30 L92 28 L98 26 Z" fill="#ffffff" />
                
                <defs>
                    <radialGradient id="pinkGlow" cx="0" cy="0" r="1" gradientUnits="userSpaceOnUse" gradientTransform="translate(100 100) scale(80)">
                        <stop stop-color="#FF007F" />
                        <stop offset="1" stop-color="#FF007F" stop-opacity="0" />
                    </radialGradient>
                </defs>
            </svg>
        </div>

        <!-- Declaração Final -->
        <div class="mt-4 p-4 rounded-2xl bg-pink-950/40 border border-pink-500/30">
            <p class="text-xs sm:text-sm text-pink-200/90 font-cyber tracking-wider">
                SISTEMA AMOROSO ATIVADO COM SUCESSO 💖<br>
                Status: Juntos para Sempre.
            </p>
        </div>
    </div>

    <!-- SCRIPT DE INTERAÇÃO E EFETOS VISUAIS -->
    <script>
        // 1. LÓGICA DO BOTÃO "NÃO" FUGITIVO
        const btnNo = document.getElementById('btn-no');
        const questionCard = document.getElementById('question-card');
        let hasStartedEscaping = false;

        function moveButton() {
            if (!hasStartedEscaping) {
                btnNo.classList.remove('relative');
                hasStartedEscaping = true;
            }

            const padding = 20;
            const btnWidth = btnNo.offsetWidth || 100;
            const btnHeight = btnNo.offsetHeight || 40;

            const maxX = window.innerWidth - btnWidth - padding;
            const maxY = window.innerHeight - btnHeight - padding;

            const randomX = Math.max(padding, Math.floor(Math.random() * maxX));
            const randomY = Math.max(padding, Math.floor(Math.random() * maxY));

            btnNo.style.position = 'fixed';
            btnNo.style.left = `${randomX}px`;
            btnNo.style.top = `${randomY}px`;
            
            const randomRot = (Math.random() - 0.5) * 20;
            btnNo.style.transform = `rotate(${randomRot}deg) scale(1.05)`;
        }

        btnNo.addEventListener('mouseover', moveButton);
        btnNo.addEventListener('touchstart', (e) => {
            e.preventDefault();
            moveButton();
        });
        btnNo.addEventListener('click', (e) => {
            e.preventDefault();
            moveButton();
        });

        // 2. CANVAS DE PARTÍCULAS DE CORAÇÕES NO FUNDO
        const canvas = document.getElementById('particle-canvas');
        const ctx = canvas.getContext('2d');

        let particles = [];
        let isCelebrating = false;

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class HeartParticle {
            constructor(isExplosion = false, x = 0, y = 0) {
                this.reset(isExplosion, x, y);
            }

            reset(isExplosion = false, x = 0, y = 0) {
                this.x = isExplosion ? x : Math.random() * canvas.width;
                this.y = isExplosion ? y : canvas.height + Math.random() * 20;
                this.size = Math.random() * 12 + 6;
                
                if (isExplosion) {
                    const angle = Math.random() * Math.PI * 2;
                    const speed = Math.random() * 8 + 2;
                    this.speedX = Math.cos(angle) * speed;
                    this.speedY = Math.sin(angle) * speed - 2;
                } else {
                    this.speedX = (Math.random() - 0.5) * 1.5;
                    this.speedY = -(Math.random() * 2 + 1);
                }

                this.color = Math.random() > 0.4 ? '#ff007f' : (Math.random() > 0.5 ? '#ff2a4b' : '#ffffff');
                this.alpha = Math.random() * 0.7 + 0.3;
                this.rotation = Math.random() * Math.PI * 2;
                this.rotSpeed = (Math.random() - 0.5) * 0.05;
                this.isExplosion = isExplosion;
                this.gravity = isExplosion ? 0.08 : 0;
            }

            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.rotation);
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = this.color;
                
                ctx.beginPath();
                const topCurveHeight = this.size * 0.3;
                ctx.moveTo(0, topCurveHeight);
                ctx.bezierCurveTo(0, 0, -this.size / 2, 0, -this.size / 2, topCurveHeight);
                ctx.bezierCurveTo(-this.size / 2, (this.size + topCurveHeight) / 2, 0, this.size, 0, this.size);
                ctx.bezierCurveTo(0, this.size, this.size / 2, (this.size + topCurveHeight) / 2, this.size / 2, topCurveHeight);
                ctx.bezierCurveTo(this.size / 2, 0, 0, 0, 0, topCurveHeight);
                ctx.closePath();
                ctx.fill();

                ctx.shadowColor = this.color;
                ctx.shadowBlur = 8;

                ctx.restore();
            }

            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                this.speedY += this.gravity;
                this.rotation += this.rotSpeed;

                if (this.isExplosion) {
                    this.alpha -= 0.008;
                }

                if (!this.isExplosion && (this.y < -20 || this.alpha <= 0)) {
                    this.reset();
                }
            }
        }

        const numParticles = 35;
        for (let i = 0; i < numParticles; i++) {
            particles.push(new HeartParticle());
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            for (let i = particles.length - 1; i >= 0; i--) {
                particles[i].update();
                particles[i].draw();

                if (particles[i].isExplosion && particles[i].alpha <= 0) {
                    particles.splice(i, 1);
                }
            }

            if (isCelebrating && particles.length < 120 && Math.random() < 0.3) {
                particles.push(new HeartParticle(false));
            }

            requestAnimationFrame(animateParticles);
        }

        window.onload = function() {
            animateParticles();
        };

        // 3. ÁUDIO ROMÂNTICO SINTETIZADO (Web Audio API)
        function playRomanticMelody() {
            try {
                const AudioContext = window.AudioContext || window.webkitAudioContext;
                if (!AudioContext) return;
                const audioCtx = new AudioContext();

                const notes = [
                    523.25, 659.25, 783.99, 1046.50,
                    880.00, 1046.50, 1174.66, 1318.51
                ];

                let noteIndex = 0;

                function playNextNote() {
                    if (!isCelebrating) return;

                    const osc = audioCtx.createOscillator();
                    const gain = audioCtx.createGain();

                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(notes[noteIndex % notes.length], audioCtx.currentTime);

                    gain.gain.setValueAtTime(0, audioCtx.currentTime);
                    gain.gain.linearRampToValueAtTime(0.15, audioCtx.currentTime + 0.1);
                    gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 1.2);

                    osc.connect(gain);
                    gain.connect(audioCtx.destination);

                    osc.start();
                    osc.stop(audioCtx.currentTime + 1.2);

                    noteIndex++;
                    setTimeout(playNextNote, 400);
                }

                playNextNote();
            } catch (e) {
                console.log("Audio API não suportada ou bloqueada");
            }
        }

        // 4. AÇÃO AO ACEITAR O PEDIDO ("SIM")
        function acceptProposal() {
            isCelebrating = true;
            playRomanticMelody();

            questionCard.classList.add('scale-75', 'opacity-0');
            
            setTimeout(() => {
                questionCard.classList.add('hidden');

                const celebrationCard = document.getElementById('celebration-card');
                celebrationCard.classList.remove('hidden');
                
                void celebrationCard.offsetWidth;
                
                celebrationCard.classList.remove('opacity-0', 'scale-90');
                celebrationCard.classList.add('opacity-100', 'scale-100');

                const centerX = window.innerWidth / 2;
                const centerY = window.innerHeight / 2;

                for (let i = 0; i < 80; i++) {
                    particles.push(new HeartParticle(true, centerX, centerY));
                }
            }, 400);
        }
    </script>
</body>
</html>

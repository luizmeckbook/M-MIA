
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MÜMIA | Renasça como Guerreiro</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap');
        
        body { background-color: #0a0a0a; color: white; font-family: 'Inter', sans-serif; }
        .accent-gradient { background: linear-gradient(90deg, #f97316 0%, #ea580c 100%); }
        .bg-card { background-color: #121212; border: 1px solid #1f1f1f; }
        .text-accent { color: #f97316; }
        .border-accent { border-color: #f97316; }
        
        /* Estilo para inputs */
        input, select, textarea {
            background-color: #121212 !important;
            border: 1px solid #333 !important;
            color: white !important;
            padding: 12px !important;
            border-radius: 8px !important;
        }
        input:focus { border-color: #f97316 !important; outline: none; }
    </style>
</head>
<body>

    <nav class="p-5 flex justify-between items-center border-b border-zinc-800 sticky top-0 bg-black/90 backdrop-blur-md z-50">
        <div class="flex items-center gap-2">
            <div class="w-10 h-10 accent-gradient rounded flex items-center justify-center font-black text-black">M</div>
            <h1 class="text-xl font-black tracking-widest italic">MÜMIA</h1>
        </div>
        <div class="flex items-center gap-4">
            <button id="admin-btn" onclick="toggleModal('admin-panel')" class="hidden bg-white text-black text-[10px] px-3 py-1 rounded font-bold">ADMIN</button>
            <button onclick="toggleModal('login-modal')" class="text-sm font-bold hover:text-accent transition">ÁREA DO ALUNO</button>
            <button onclick="toggleModal('signup-modal')" class="accent-gradient px-5 py-2 rounded-lg font-bold text-sm shadow-lg">INSCREVER-SE</button>
        </div>
    </nav>

    <section class="py-24 text-center px-6 border-b border-zinc-900">
        <div class="inline-flex items-center gap-2 text-[10px] font-bold text-accent border border-accent/30 px-3 py-1 rounded-full mb-6 uppercase tracking-widest">
            <i class="fas fa-fire"></i> Forjado no Fogo
        </div>
        <h2 id="hero-title" class="text-6xl md:text-8xl font-black uppercase mb-6 leading-none">RENASÇA <br> <span class="text-accent">COMO GUERREIRO.</span></h2>
        <p id="hero-desc" class="text-zinc-400 max-w-2xl mx-auto mb-10 text-lg">Boxing, Muay Thai e Jiu-Jitsu. Treine com profissionais e desperte o lutador que existe em você.</p>
        <div class="flex flex-col md:flex-row justify-center gap-4">
            <button class="accent-gradient px-8 py-4 rounded-xl font-black text-lg flex items-center justify-center gap-2">Aula Grátis <i class="fas fa-arrow-right"></i></button>
            <button class="border border-zinc-700 px-8 py-4 rounded-xl font-black text-lg hover:bg-zinc-900 transition">Quero me inscrever</button>
        </div>
    </section>

    <section class="grid grid-cols-2 md:grid-cols-4 gap-8 py-16 px-6 max-w-6xl mx-auto text-center border-b border-zinc-900">
        <div><h4 class="text-4xl font-black">500+</h4><p class="text-zinc-500 text-xs uppercase font-bold mt-2">Alunos Ativos</p></div>
        <div><h4 class="text-4xl font-black">12</h4><p class="text-zinc-500 text-xs uppercase font-bold mt-2">Títulos Regionais</p></div>
        <div><h4 class="text-4xl font-black">15</h4><p class="text-zinc-500 text-xs uppercase font-bold mt-2">Anos de Tatame</p></div>
        <div><h4 class="text-4xl font-black text-accent">3</h4><p class="text-zinc-500 text-xs uppercase font-bold mt-2">Modalidades</p></div>
    </section>

    <section class="py-20 px-6 max-w-6xl mx-auto">
        <h3 class="text-xs font-bold text-zinc-500 uppercase tracking-widest mb-4">Nossas Modalidades</h3>
        <h2 class="text-4xl font-black mb-12 italic uppercase">Escolha sua <span class="text-accent">Arma.</span></h2>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
            <div class="bg-card p-8 rounded-2xl group hover:border-accent transition">
                <h4 class="text-2xl font-black mb-2 uppercase">Boxing</h4>
                <p class="text-zinc-500 text-sm mb-6">Velocidade, técnica e potência das mãos.</p>
                <p id="price-box" class="text-xl font-bold">R$ 180<span class="text-xs text-zinc-600">/mês</span></p>
            </div>
            <div class="bg-card p-8 rounded-2xl group hover:border-accent transition">
                <h4 class="text-2xl font-black mb-2 uppercase">Muay Thai</h4>
                <p class="text-zinc-500 text-sm mb-6">Arte das oito armas. Força tailandesa.</p>
                <p id="price-muay" class="text-xl font-bold">R$ 180<span class="text-xs text-zinc-600">/mês</span></p>
            </div>
            <div class="bg-card p-8 rounded-2xl group border-accent transition">
                <h4 class="text-2xl font-black mb-2 uppercase">Jiu-Jitsu</h4>
                <p class="text-zinc-500 text-sm mb-6">Solo, alavanca e técnica. Imbatível no chão.</p>
                <p id="price-jiu" class="text-xl font-bold">R$ 200<span class="text-xs text-zinc-600">/mês</span></p>
            </div>
        </div>
    </section>

    <div id="login-modal" class="hidden fixed inset-0 bg-black/95 flex items-center justify-center p-6 z-[60]">
        <div class="bg-card p-8 rounded-3xl w-full max-w-md shadow-2xl">
            <h3 class="text-2xl font-black mb-6 italic uppercase">Área do Guerreiro</h3>
            <div class="flex flex-col gap-4">
                <input type="email" id="login-email" placeholder="Seu Gmail">
                <input type="password" id="login-pass" placeholder="Sua Senha">
                <button onclick="handleResetPassword()" class="text-right text-xs text-zinc-500 hover:text-accent font-bold uppercase">Esqueci a senha</button>
                <button onclick="login()" class="accent-gradient w-full py-4 rounded-xl font-black uppercase">Entrar</button>
                <button onclick="toggleModal('login-modal')" class="text-zinc-600 text-xs font-bold uppercase mt-4">Fechar</button>
            </div>
        </div>
    </div>

    <div id="admin-panel" class="hidden fixed inset-0 bg-black flex items-center justify-center p-6 z-[70]">
        <div class="bg-card p-8 rounded-3xl w-full max-w-2xl border-2 border-accent shadow-[0_0_50px_rgba(249,115,22,0.2)]">
            <div class="flex justify-between items-center mb-8 border-b border-zinc-800 pb-4">
                <h3 class="text-2xl font-black italic">GERENCIAMENTO GERAL</h3>
                <button onclick="toggleModal('admin-panel')" class="text-zinc-500 text-2xl">&times;</button>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                    <label class="text-[10px] font-black uppercase text-accent">Título do Site</label>
                    <input type="text" id="adm-title" class="w-full mt-1">
                </div>
                <div>
                    <label class="text-[10px] font-black uppercase text-accent">Preço Jiu-Jitsu</label>
                    <input type="text" id="adm-price-jiu" class="w-full mt-1">
                </div>
            </div>
            <button onclick="saveAdmin()" class="w-full bg-white text-black p-4 rounded-xl font-black uppercase mt-8 hover:bg-zinc-200">Salvar Mudanças</button>
        </div>
    </div>

    <script>
        // CONFIGURAÇÃO: Seu e-mail de administrador aqui
        const ADMIN_EMAILS = ["ruanassistec@gmail.com"];

        function toggleModal(id) { document.getElementById(id).classList.toggle('hidden'); }

        function login() {
            const email = document.getElementById('login-email').value.toLowerCase();
            localStorage.setItem('mumia_user', email);
            
            if(ADMIN_EMAILS.includes(email)) {
                alert("ACESSO ADMINISTRADOR LIBERADO.");
            } else {
                alert("Login efetuado.");
            }
            location.reload();
        }

        function handleResetPassword() {
            const email = document.getElementById('login-email').value;
            if(!email) return alert("Digite seu e-mail no campo acima.");
            alert("Enviamos um link de redefinição para o seu Gmail: " + email);
        }

        function checkUser() {
            const user = localStorage.getItem('mumia_user');
            if(user) {
                if(ADMIN_EMAILS.includes(user)) {
                    document.getElementById('admin-btn').classList.remove('hidden');
                }
            }
        }

        function saveAdmin() {
            const data = {
                title: document.getElementById('adm-title').value,
                priceJiu: document.getElementById('adm-price-jiu').value
            };
            localStorage.setItem('mumia_config', JSON.stringify(data));
            location.reload();
        }

        function loadConfig() {
            const cfg = JSON.parse(localStorage.getItem('mumia_config'));
            if(cfg) {
                if(cfg.title) document.getElementById('hero-title').innerText = cfg.title;
                if(cfg.priceJiu) document.getElementById('price-jiu').innerHTML = `R$ ${cfg.priceJiu}<span class="text-xs text-zinc-600">/mês</span>`;
            }
        }

        window.onload = () => { checkUser(); loadConfig(); };
    </script>
</body>
</html>

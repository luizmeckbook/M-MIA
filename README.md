
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MÜMIA | Renasça como Guerreiro</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap');
        body { background-color: #0a0a0a; color: white; font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
        .accent-gradient { background: linear-gradient(90deg, #f97316 0%, #ea580c 100%); }
        .bg-card { background-color: #121212; border: 1px solid #1f1f1f; }
        .text-accent { color: #f97316; }
        input, select { background-color: #000 !important; border: 1px solid #333 !important; color: white !important; padding: 12px !important; border-radius: 8px !important; width: 100%; outline: none; }
        input:focus { border-color: #f97316 !important; }
        .modal-open { overflow: hidden; }
    </style>
</head>
<body>

    <nav class="p-5 flex justify-between items-center border-b border-zinc-800 sticky top-0 bg-black/90 backdrop-blur-md z-50">
        <div class="flex items-center gap-2 cursor-pointer" onclick="window.scrollTo(0,0)">
            <div class="w-10 h-10 accent-gradient rounded flex items-center justify-center font-black text-black">M</div>
            <h1 class="text-xl font-black tracking-widest italic">MÜMIA</h1>
        </div>
        <div class="flex items-center gap-4">
            <button id="admin-btn" onclick="toggleModal('admin-panel')" class="hidden bg-white text-black text-[10px] px-3 py-1 rounded font-bold uppercase tracking-tighter">Painel Admin</button>
            <button onclick="openAuth('login')" class="text-xs font-bold hover:text-accent transition uppercase tracking-widest">Entrar</button>
            <button onclick="openAuth('signup')" class="accent-gradient px-5 py-2 rounded-lg font-bold text-xs shadow-lg uppercase">Cadastrar</button>
        </div>
    </nav>

    <section class="py-24 text-center px-6 border-b border-zinc-900">
        <div class="inline-flex items-center gap-2 text-[10px] font-bold text-accent border border-accent/30 px-3 py-1 rounded-full mb-6 uppercase tracking-widest">
            <i class="fas fa-fire"></i> Forjado no Fogo
        </div>
        <h2 id="hero-title" class="text-6xl md:text-8xl font-black uppercase mb-6 leading-none tracking-tighter">RENASÇA <br> <span class="text-accent">COMO GUERREIRO.</span></h2>
        <p class="text-zinc-400 max-w-2xl mx-auto mb-10 text-lg">Treine Boxing, Muay Thai e Jiu-Jitsu com os melhores. Sua jornada começa agora.</p>
        <div class="flex flex-col md:flex-row justify-center gap-4">
            <button onclick="document.getElementById('modalidades').scrollIntoView()" class="accent-gradient px-8 py-4 rounded-xl font-black text-lg flex items-center justify-center gap-2">Ver Modalidades <i class="fas fa-arrow-down"></i></button>
            <button onclick="openAuth('signup')" class="border border-zinc-700 px-8 py-4 rounded-xl font-black text-lg hover:bg-zinc-900 transition">Filiar-se à Mümia</button>
        </div>
    </section>

    <section id="modalidades" class="py-20 px-6 max-w-6xl mx-auto">
        <h2 class="text-4xl font-black mb-12 italic uppercase">Escolha sua <span class="text-accent">Arte.</span></h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
            <div class="bg-card p-8 rounded-2xl border-l-4 border-accent">
                <h4 class="text-2xl font-black mb-2 uppercase">Boxing</h4>
                <p class="text-zinc-500 text-sm mb-6">Velocidade e potência.</p>
                <p class="text-xl font-bold mb-6">R$ 180<span class="text-xs text-zinc-600">/mês</span></p>
                <button onclick="openAuth('signup')" class="w-full py-3 border border-zinc-700 rounded-lg font-bold text-xs uppercase hover:bg-zinc-800 transition">Selecionar</button>
            </div>
            <div class="bg-card p-8 rounded-2xl border-l-4 border-accent">
                <h4 class="text-2xl font-black mb-2 uppercase">Muay Thai</h4>
                <p class="text-zinc-500 text-sm mb-6">A arte das 8 armas.</p>
                <p class="text-xl font-bold mb-6">R$ 180<span class="text-xs text-zinc-600">/mês</span></p>
                <button onclick="openAuth('signup')" class="w-full py-3 border border-zinc-700 rounded-lg font-bold text-xs uppercase hover:bg-zinc-800 transition">Selecionar</button>
            </div>
            <div class="bg-card p-8 rounded-2xl border-l-4 border-accent">
                <h4 class="text-2xl font-black mb-2 uppercase">Jiu-Jitsu</h4>
                <p class="text-zinc-500 text-sm mb-6">Técnica e solo.</p>
                <p id="price-jiu" class="text-xl font-bold mb-6">R$ 200<span class="text-xs text-zinc-600">/mês</span></p>
                <button onclick="openAuth('signup')" class="w-full py-3 border border-zinc-700 rounded-lg font-bold text-xs uppercase hover:bg-zinc-800 transition">Selecionar</button>
            </div>
        </div>
    </section>

    <div id="auth-modal" class="hidden fixed inset-0 bg-black/95 flex items-center justify-center p-6 z-[60]">
        <div class="bg-card p-8 rounded-3xl w-full max-w-md shadow-2xl relative">
            <button onclick="toggleModal('auth-modal')" class="absolute top-4 right-4 text-zinc-600 hover:text-white"><i class="fas fa-times"></i></button>
            
            <div id="view-login">
                <h3 class="text-3xl font-black mb-2 italic uppercase tracking-tighter">Login</h3>
                <p class="text-zinc-500 text-xs mb-8 font-bold uppercase tracking-widest">Acesse seu painel</p>
                <div class="space-y-4">
                    <input type="email" id="login-email" placeholder="E-mail (Gmail)">
                    <input type="password" id="login-pass" placeholder="Sua Senia">
                    <button onclick="handleResetPassword()" class="text-right text-[10px] text-zinc-500 hover:text-accent font-bold uppercase block w-full">Esqueci a senha</button>
                    <button onclick="handleLogin()" class="accent-gradient w-full py-4 rounded-xl font-black uppercase text-sm shadow-lg">Entrar no Tatame</button>
                    <p class="text-center text-xs text-zinc-500 mt-6">Ainda não é um guerreiro? <button onclick="switchView('signup')" class="text-accent font-bold uppercase">Cadastre-se</button></p>
                </div>
            </div>

            <div id="view-signup" class="hidden">
                <h3 class="text-3xl font-black mb-2 italic uppercase tracking-tighter text-accent">Cadastro</h3>
                <p class="text-zinc-500 text-xs mb-8 font-bold uppercase tracking-widest">Crie sua conta agora</p>
                <div class="space-y-4">
                    <input type="text" id="reg-name" placeholder="Nome Completo">
                    <input type="email" id="reg-email" placeholder="Seu melhor E-mail">
                    <input type="tel" id="reg-phone" placeholder="Celular (WhatsApp)">
                    <input type="password" id="reg-pass" placeholder="Crie uma Senha">
                    <button onclick="handleRegister()" class="accent-gradient w-full py-4 rounded-xl font-black uppercase text-sm shadow-lg">Confirmar Inscrição</button>
                    <p class="text-center text-xs text-zinc-500 mt-6">Já tem conta? <button onclick="switchView('login')" class="text-accent font-bold uppercase">Fazer Login</button></p>
                </div>
            </div>
        </div>
    </div>

    <div id="admin-panel" class="hidden fixed inset-0 bg-black/98 flex items-center justify-center p-6 z-[70]">
        <div class="bg-card p-8 rounded-3xl w-full max-w-2xl border-2 border-accent">
            <div class="flex justify-between items-center mb-8 border-b border-zinc-800 pb-4">
                <h3 class="text-2xl font-black italic">PAINEL DO MESTRE</h3>
                <button onclick="toggleModal('admin-panel')" class="text-zinc-500 text-2xl">&times;</button>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div><label class="text-[10px] font-black uppercase text-accent">Título Hero</label><input type="text" id="adm-title"></div>
                <div><label class="text-[10px] font-black uppercase text-accent">Preço Jiu-Jitsu</label><input type="text" id="adm-price-jiu"></div>
            </div>
            <button onclick="saveAdmin()" class="w-full bg-white text-black p-4 rounded-xl font-black uppercase mt-8">Salvar Configurações</button>
        </div>
    </div>

    <script>
        // CONFIG: Altere seu email de administrador aqui
        const ADMIN_EMAILS = ["ruanassistec@gmail.com"];

        function toggleModal(id) {
            const modal = document.getElementById(id);
            modal.classList.toggle('hidden');
            document.body.classList.toggle('modal-open');
        }

        // Abre o modal de Auth já na tela certa
        function openAuth(view) {
            toggleModal('auth-modal');
            switchView(view);
        }

        function switchView(view) {
            document.getElementById('view-login').classList.toggle('hidden', view !== 'login');
            document.getElementById('view-signup').classList.toggle('hidden', view !== 'signup');
        }

        function handleLogin() {
            const email = document.getElementById('login-email').value.toLowerCase();
            if(!email) return alert("Digite seu e-mail.");
            
            localStorage.setItem('logged_user', email);
            if(ADMIN_EMAILS.includes(email)) alert("MODO ADMINISTRADOR ATIVADO.");
            location.reload();
        }

        function handleRegister() {
            const nome = document.getElementById('reg-name').value;
            const email = document.getElementById('reg-email').value;
            if(!nome || !email) return alert("Preencha todos os campos.");
            
            alert(`Bem-vindo à MÜMIA, ${nome}! Sua conta foi criada.`);
            localStorage.setItem('logged_user', email);
            location.reload();
        }

        function handleResetPassword() {
            const email = document.getElementById('login-email').value;
            if(!email) return alert("Coloque seu e-mail no campo acima primeiro.");
            alert("Enviamos as instruções de troca de senha para o Gmail: " + email);
        }

        function saveAdmin() {
            const data = {
                title: document.getElementById('adm-title').value,
                priceJiu: document.getElementById('adm-price-jiu').value
            };
            localStorage.setItem('mumia_config', JSON.stringify(data));
            location.reload();
        }

        window.onload = () => {
            const user = localStorage.getItem('logged_user');
            if(user && ADMIN_EMAILS.includes(user)) {
                document.getElementById('admin-btn').classList.remove('hidden');
            }
            
            const cfg = JSON.parse(localStorage.getItem('mumia_config'));
            if(cfg) {
                if(cfg.title) document.getElementById('hero-title').innerText = cfg.title;
                if(cfg.priceJiu) document.getElementById('price-jiu').innerHTML = `R$ ${cfg.priceJiu}<span class="text-xs text-zinc-600">/mês</span>`;
            }
        };
    </script>
</body>
</html>

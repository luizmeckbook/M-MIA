
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MUIMIA | Academia de Combate</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary-red: #cc0000;
            --dark-bg: #050505;
            --card-bg: #121212;
        }
        body { background-color: var(--dark-bg); color: white; font-family: 'Inter', sans-serif; }
        .red-gradient { background: linear-gradient(135deg, #ff0000 0%, #7a0000 100%); }
        .border-red { border-color: var(--primary-red); }
        .text-red { color: var(--primary-red); }
        .bg-red-muimia { background-color: var(--primary-red); }
        
        /* Estilo para a Logo */
        .logo-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        .logo-placeholder {
            width: 60px;
            height: 60px;
            background: #222;
            border: 2px solid var(--primary-red);
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            overflow: hidden;
        }
    </style>
</head>
<body>

    <nav class="p-4 flex justify-between items-center border-b border-zinc-800 sticky top-0 bg-black z-40">
        <div class="logo-container">
            <div class="logo-placeholder">
                <i class="fas fa-skull text-red text-2xl"></i> 
            </div>
            <h1 class="text-3xl font-black italic tracking-tighter text-red">MUIMIA</h1>
        </div>
        <div class="hidden md:flex space-x-8 font-bold uppercase text-sm">
            <a href="#modalidades" class="hover:text-red transition">Modalidades</a>
            <a href="#" class="hover:text-red transition">Horários</a>
            <button onclick="toggleModal('login-modal')" class="text-red border border-red px-6 py-1 rounded hover:bg-red-muimia hover:text-white transition">LOGIN</button>
        </div>
    </nav>

    <section class="relative h-[80vh] flex items-center justify-center text-center overflow-hidden">
        <div class="absolute inset-0 bg-cover bg-center opacity-40" style="background-image: url('https://images.unsplash.com/photo-1595078475328-1ab05d0a6a0e?auto=format&fit=crop&q=80');"></div>
        <div class="absolute inset-0 bg-gradient-to-t from-black via-transparent to-black"></div>
        
        <div class="relative z-10 px-4">
            <h2 class="text-7xl md:text-9xl font-black uppercase italic leading-none mb-4">ESMAGUE SEUS <span class="text-red">LIMITES</span></h2>
            <p class="text-xl md:text-2xl text-gray-300 mb-8 max-w-2xl mx-auto uppercase tracking-widest">Boxing • Muay Thai • Jiu-Jitsu • MMA</p>
            <button onclick="toggleModal('payment-modal')" class="red-gradient px-12 py-5 rounded-full font-black text-xl hover:scale-105 transition-transform shadow-[0_0_20px_rgba(204,0,0,0.5)]">MATRICULE-SE AGORA</button>
        </div>
    </section>

    <section id="modalidades" class="py-20 px-6">
        <h3 class="text-center text-4xl font-bold mb-16 uppercase italic">Nossas <span class="text-red">Disciplinas</span></h3>
        <div class="grid grid-cols-1 md:grid-cols-4 gap-4 max-w-7xl mx-auto">
            <div class="bg-zinc-900 p-8 rounded-lg border-l-4 border-red hover:bg-zinc-800 transition">
                <i class="fas fa-hand-fist text-4xl text-red mb-4"></i>
                <h4 class="text-xl font-bold mb-2">BOXING</h4>
                <p class="text-gray-400 text-sm">Técnica, agilidade e potência bruta.</p>
            </div>
            <div class="bg-zinc-900 p-8 rounded-lg border-l-4 border-red hover:bg-zinc-800 transition">
                <i class="fas fa-user-ninja text-4xl text-red mb-4"></i>
                <h4 class="text-xl font-bold mb-2">MUAY THAI</h4>
                <p class="text-gray-400 text-sm">A arte das oito armas.</p>
            </div>
            <div class="bg-zinc-900 p-8 rounded-lg border-l-4 border-red hover:bg-zinc-800 transition">
                <i class="fas fa-person-rays text-4xl text-red mb-4"></i>
                <h4 class="text-xl font-bold mb-2">JIU-JITSU</h4>
                <p class="text-gray-400 text-sm">Onde a técnica vence a força.</p>
            </div>
            <div class="bg-zinc-900 p-8 rounded-lg border-l-4 border-red hover:bg-zinc-800 transition">
                <i class="fas fa-skull-crossbones text-4xl text-red mb-4"></i>
                <h4 class="text-xl font-bold mb-2">MMA</h4>
                <p class="text-gray-400 text-sm">A combinação definitiva de todas as artes.</p>
            </div>
        </div>
    </section>

    <div id="login-modal" class="hidden fixed inset-0 bg-black/95 backdrop-blur-sm flex items-center justify-center p-4 z-50">
        <div class="bg-zinc-900 border border-zinc-800 p-8 rounded-2xl w-full max-w-md shadow-2xl">
            <div id="login-step">
                <h3 class="text-3xl font-black text-red italic mb-6">LOGIN DO ATLETA</h3>
                <input type="text" placeholder="CPF ou E-mail" class="w-full p-4 mb-4 bg-black border border-zinc-700 rounded-lg outline-none focus:border-red transition">
                <input type="password" placeholder="Senha" class="w-full p-4 mb-2 bg-black border border-zinc-700 rounded-lg outline-none focus:border-red transition">
                <button onclick="showForgot()" class="text-sm text-gray-400 hover:text-red mb-6 block w-full text-right">Esqueceu a senha?</button>
                <button class="w-full red-gradient p-4 rounded-lg font-black uppercase">Entrar no Tatame</button>
            </div>

            <div id="forgot-step" class="hidden">
                <h3 class="text-2xl font-bold mb-2 text-red">RECUPERAR ACESSO</h3>
                <p class="text-gray-400 text-sm mb-6">Enviaremos um código via SMS para o seu celular cadastrado.</p>
                <input type="tel" id="phone" placeholder="(00) 00000-0000" class="w-full p-4 mb-4 bg-black border border-zinc-700 rounded-lg text-white text-lg text-center">
                <button onclick="sendCode()" class="w-full bg-white text-black p-4 rounded-lg font-black uppercase mb-4 hover:bg-gray-200">ENVIAR CÓDIGO</button>
                
                <div id="code-input" class="hidden animate-bounce mt-4">
                    <input type="text" placeholder="CÓDIGO DE 6 DÍGITOS" class="w-full p-4 mb-4 bg-black border-2 border-red rounded-lg text-white text-center text-2xl font-bold tracking-widest outline-none">
                    <button class="w-full bg-green-600 text-white p-4 rounded-lg font-black uppercase hover:bg-green-700">Validar Código</button>
                </div>
            </div>
            <button onclick="toggleModal('login-modal')" class="mt-6 text-zinc-500 w-full text-center uppercase text-xs font-bold tracking-widest hover:text-white">Voltar</button>
        </div>
    </div>

    <div id="payment-modal" class="hidden fixed inset-0 bg-black/95 backdrop-blur-sm flex items-center justify-center p-4 z-50">
        <div class="bg-zinc-900 border border-zinc-800 p-8 rounded-2xl w-full max-w-2xl shadow-2xl">
            <div class="flex justify-between items-center mb-8">
                <h3 class="text-3xl font-black text-red italic">ASSINATURA MUIMIA</h3>
                <span class="bg-red-muimia px-3 py-1 rounded text-xs font-bold">RECORRENTE</span>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div>
                    <label class="block text-xs uppercase font-bold text-gray-500 mb-2 tracking-widest">Titular do Cartão</label>
                    <input type="text" class="w-full p-4 bg-black border border-zinc-800 rounded-lg focus:border-red outline-none">
                    
                    <label class="block text-xs uppercase font-bold text-gray-500 mt-6 mb-2 tracking-widest">Número do Cartão</label>
                    <div class="relative">
                        <input type="text" placeholder="**** **** **** ****" class="w-full p-4 bg-black border border-zinc-800 rounded-lg focus:border-red outline-none">
                        <i class="fab fa-cc-visa absolute right-4 top-4 text-2xl text-gray-600"></i>
                    </div>
                </div>
                <div>
                    <div class="flex gap-4">
                        <div class="w-1/2">
                            <label class="block text-xs uppercase font-bold text-gray-500 mb-2 tracking-widest">Validade</label>
                            <input type="text" placeholder="MM/AA" class="w-full p-4 bg-black border border-zinc-800 rounded-lg focus:border-red outline-none">
                        </div>
                        <div class="w-1/2">
                            <label class="block text-xs uppercase font-bold text-gray-500 mb-2 tracking-widest">CVC</label>
                            <input type="text" placeholder="123" class="w-full p-4 bg-black border border-zinc-800 rounded-lg focus:border-red outline-none">
                        </div>
                    </div>
                    <div class="mt-8 p-4 bg-zinc-800/50 rounded-lg border border-zinc-700">
                        <p class="text-sm text-gray-300">Valor: <span class="text-white font-bold">R$ 149,90 / mês</span></p>
                        <p class="text-[10px] text-gray-500 mt-1 uppercase">Cobrança automática via cartão de crédito. Cancele quando quiser.</p>
                    </div>
                </div>
            </div>
            
            <button class="w-full red-gradient p-5 rounded-xl font-black mt-10 text-xl shadow-lg hover:brightness-110">FINALIZAR MATRÍCULA</button>
            <button onclick="toggleModal('payment-modal')" class="mt-4 text-zinc-500 w-full text-center text-xs uppercase">Cancelar</button>
        </div>
    </div>

    <script>
        function toggleModal(id) {
            document.getElementById(id).classList.toggle('hidden');
        }

        function showForgot() {
            document.getElementById('login-step').classList.add('hidden');
            document.getElementById('forgot-step').classList.remove('hidden');
        }

        function sendCode() {
            const phone = document.getElementById('phone').value;
            if(phone.length > 8) {
                alert('Código enviado via SMS para: ' + phone);
                document.getElementById('code-input').classList.remove('hidden');
            } else {
                alert('Por favor, digite um celular válido.');
            }
        }
    </script>
</body>
</html>

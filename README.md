<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Volt E-bike | Bicicletas Elétricas em Fortaleza</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Cores da Volt E-bike */
        :root {
            --cor-primaria: #28a745; /* Verde Sustentabilidade */
            --cor-secundaria: #007bff; /* Azul Tecnologia */
            --cor-texto: #343a40;
            --cor-fundo: #f8f9fa;
        }

        .bg-volt-verde { background-color: var(--cor-primaria); }
        .text-volt-verde { color: var(--cor-primaria); }
        .bg-volt-azul { background-color: var(--cor-secundaria); }
        .text-volt-azul { color: var(--cor-secundaria); }
        .border-volt-verde { border-color: var(--cor-primaria); }

        /* Estilos customizados para o banner */
        .hero-banner {
            background-image: url('https://via.placeholder.com/1500x800.png?text=Banner+Volt+E-bike');
            background-size: cover;
            background-position: center;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col bg-gray-50 text-cor-texto">

    <header class="bg-white text-cor-texto shadow-sm p-4 flex justify-between items-center">
        <div class="flex items-center gap-4">
            <a href="index.html">
                <img src="Volt E-bike.png" alt="Logo Volt E-bike" class="h-12 w-12 rounded-lg" />
            </a>
            <h1 class="text-2xl font-bold text-volt-verde">Volt E-bike</h1>
        </div>
        <nav class="space-x-6">
            <a href="#home" class="hover:text-volt-azul">Início</a>
            <a href="#produtos" class="hover:text-volt-azul">Vendas</a>
            <a href="#aluguel" class="hover:text-volt-azul">Aluguel</a>
            <a href="#contato" class="hover:text-volt-azul">Contato</a>
        </nav>
    </header>

    <section id="home" class="hero-banner text-center py-16 text-white">
        <h2 class="text-4xl font-bold mb-2 text-volt-verde">Sua nova forma de se mover.</h2>
        <p class="text-lg mb-4 text-volt-azul">Bicicletas elétricas leves e com autonomia de até 50km por dia. Perfeitas para a cidade de Fortaleza.</p>
        <div class="flex justify-center gap-4">
            <a href="#produtos" class="bg-black text-white px-6 py-3 rounded-full font-semibold hover:bg-gray-800">Ver Modelos</a>
            <a href="#aluguel" class="bg-volt-verde text-white px-6 py-3 rounded-full font-semibold hover:opacity-80">Alugar / Assinar</a>
        </div>
    </section>

    <main class="flex-1 p-8 grid grid-cols-1 lg:grid-cols-3 gap-8">

        <section id="produtos" class="lg:col-span-2">
            <h3 class="text-2xl font-semibold mb-4 text-volt-azul">Nossos Modelos para Venda</h3>
            <div id="productsGrid" class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                </div>
        </section>

        <aside id="aluguel" class="bg-white rounded-2xl p-6 shadow">
            <h3 class="text-2xl font-semibold mb-4 text-volt-azul">Aluguel & Assinatura</h3>
            <p class="text-sm text-gray-600 mb-4">Escolha um plano diário ou por assinatura. Manutenção inclusa.</p>
            <div id="fleetList" class="space-y-4">
                </div>
            <div class="mt-6">
                <h4 class="font-semibold">Planos de Exemplo</h4>
                <ul class="text-sm text-gray-600 mt-2">
                    <li>**Diário:** Ideal para entregadores por período curto.</li>
                    <li>**Assinatura:** Manutenção + seguro simplificado.</li>
                </ul>
            </div>
        </aside>

        <aside class="lg:col-span-3 bg-white rounded-2xl p-6 shadow">
            <h3 class="text-2xl font-semibold mb-4 text-volt-azul">Carrinho</h3>
            <div id="cartArea">
                <p class="text-gray-600">Seu carrinho está vazio.</p>
            </div>
        </aside>

    </main>

    <footer id="contato" class="bg-black text-white p-6 text-center">
        <p>Acompanhe a gente: <a href="https://www.instagram.com/voltebikebr" target="_blank" class="hover:text-volt-verde font-semibold">@voltebikebr</a></p>
        <p>&copy; <span id="year"></span> Volt E-bike. Todos os direitos reservados.</p>
    </footer>

    <!-- Modal Aluguel -->
    <div id="rentalModal" class="fixed inset-0 bg-black/50 hidden items-center justify-center p-4">
        <div class="bg-white rounded-xl max-w-md w-full p-6">
            <h4 id="modalTitle" class="text-xl font-semibold mb-2">Alugar</h4>
            <p id="modalStatus" class="text-sm text-gray-600 mb-4">Status: </p>
            <div class="space-y-3">
                <div>
                    <label class="block text-sm font-medium">Plano</label>
                    <select id="modalPlan" class="mt-1 w-full border rounded px-3 py-2">
                        <option value="diario">Diário</option>
                        <option value="assinatura">Assinatura (mensal)</option>
                    </select>
                </div>
                <div id="modalDaily">
                    <label class="block text-sm font-medium">Dias</label>
                    <input id="modalDays" type="number" min="1" value="1" class="mt-1 w-full border rounded px-3 py-2" />
                    <div class="mt-2">Preço estimado: <strong id="modalPriceDay" class="text-volt-verde">R$ 0</strong></div>
                </div>
                <div id="modalMonthly" class="hidden">
                    <label class="block text-sm font-medium">Meses (assinatura)</label>
                    <input id="modalMonths" type="number" min="1" value="1" class="mt-1 w-full border rounded px-3 py-2" />
                    <div class="mt-2">Preço estimado: <strong id="modalPriceMonth" class="text-volt-verde">R$ 0</strong></div>
                </div>
                <div class="flex justify-end gap-3 mt-4">
                    <button id="modalCancel" class="px-4 py-2 border rounded">Cancelar</button>
                    <button id="modalConfirm" class="px-4 py-2 bg-volt-verde text-white rounded hover:opacity-80">Confirmar</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Dados iniciais (com imagem atualizada)
        const products = [
            { 
                id: 1, 
                name: "Modelo Urbano", 
                price: 4999.90, 
                img: "https://via.placeholder.com/600x400?text=Modelo+Urbano", 
                description: "Design ergonômico, ideal para o dia a dia e entregas." 
            },
            { 
                id: 2, 
                name: "Modelo Aventura", 
                price: 8990.00, 
                img: "https://github.com/erosvasconcelos05-ops/Volt-E-bike/assets/145278389/6f0677df-f773-4a16-a8a2-18eb63f10fcb", 
                description: "Potência extra e suspensão para terrenos mais desafiadores." 
            },
        ];

        let fleet = [
            { id: 101, model: "City E-Bike", type: "elétrica", status: "disponível", pricePerDay: 40, pricePerMonth: 850 },
            { id: 102, model: "Delivery Pro", type: "elétrica", status: "disponível", pricePerDay: 50, pricePerMonth: 990 }
        ];

        const cart = [];

        // Elementos DOM
        const productsGrid = document.getElementById('productsGrid');
        const fleetList = document.getElementById('fleetList');
        const cartArea = document.getElementById('cartArea');
        const yearSpan = document.getElementById('year');

        // Modal elements
        const rentalModal = document.getElementById('rentalModal');
        const modalTitle = document.getElementById('modalTitle');
        const modalStatus = document.getElementById('modalStatus');
        const modalPlan = document.getElementById('modalPlan');
        const modalDaily = document.getElementById('modalDaily');
        const modalMonthly = document.getElementById('modalMonthly');
        const modalDays = document.getElementById('modalDays');
        const modalMonths = document.getElementById('modalMonths');
        const modalPriceDay = document.getElementById('modalPriceDay');
        const modalPriceMonth = document.getElementById('modalPriceMonth');
        const modalCancel = document.getElementById('modalCancel');
        const modalConfirm = document.getElementById('modalConfirm');

        let selectedUnit = null;

        // Helpers
        function formatBRL(value) {
            return value.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
        }

        // Render produtos
        function renderProducts() {
            productsGrid.innerHTML = '';
            products.forEach(p => {
                const card = document.createElement('article');
                card.className = "bg-white rounded-2xl shadow p-4 hover:scale-105 transition-transform";
                card.innerHTML = `
                    <img src="${p.img}" alt="${p.name}" class="rounded-xl mb-3 w-full h-40 object-cover" />
                    <h4 class="font-semibold">${p.name}</h4>
                    <p class="text-sm text-gray-600">${p.description}</p>
                    <div class="mt-2 flex items-center justify-between">
                        <div class="text-volt-verde font-bold">${formatBRL(p.price)}</div>
                        <button data-id="${p.id}" class="addToCartBtn bg-black text-white px-3 py-1 rounded hover:opacity-80">Adicionar</button>
                    </div>
                `;
                productsGrid.appendChild(card);
            });

            // attach events
            document.querySelectorAll('.addToCartBtn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    const id = Number(e.currentTarget.dataset.id);
                    const prod = products.find(x => x.id === id);
                    addToCart(prod);
                });
            });
        }

        // Restante do JS permanece igual (fleet, cart, modal...)
        // ...

        // Inicialização
        function init() {
            yearSpan.textContent = new Date().getFullYear();
            renderProducts();
            renderFleet();
            renderCart();
        }

        init();
    </script>
</body>
</html>

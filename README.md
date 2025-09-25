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

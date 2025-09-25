<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Volt E-bike | Bicicletas Elétricas em Fortaleza</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="min-h-screen bg-gray-100">
  <header class="bg-white shadow p-4">
    <h1 class="text-2xl font-bold text-center text-green-600">Volt E-bike</h1>
    <p class="text-center text-gray-600">Bicicletas elétricas em Fortaleza</p>
  </header>

  <main class="p-6">
    <section>
      <h2 class="text-xl font-semibold mb-4">Modelos Disponíveis</h2>
      <div id="productsGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6"></div>
    </section>
  </main>

  <script>
    // Produtos
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
        img: "https://raw.githubusercontent.com/erosvasconcelos05-ops/Volt-E-bike/c1116dd21f13b804560a8f4a7b8a7a4a6a0e494c/Volt%20E-bike.png", 
        description: "Potência extra e suspensão para terrenos mais desafiadores." 
      },
    ];

    const productsGrid = document.getElementById('productsGrid');

    function formatBRL(value) {
      return value.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
    }

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
            <div class="text-green-600 font-bold">${formatBRL(p.price)}</div>
          </div>
        `;
        productsGrid.appendChild(card);
      });
    }

    renderProducts();
  </script>
</body>
</html>

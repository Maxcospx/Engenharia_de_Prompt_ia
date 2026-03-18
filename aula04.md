Transformar um instrucao vaga em um Prompt Mestre estruturado 

Tarefa inicial: Criar um site de doacao de animais.

<img width="1146" height="635" alt="Captura de tela 2026-03-10 223356" src="https://github.com/user-attachments/assets/07b990df-6dd5-4390-813c-053db76b6192" />

<img width="755" height="409" alt="Captura de tela 2026-03-17 210547" src="https://github.com/user-attachments/assets/476eeecd-2a71-484a-bec8-489f82a0d2f5" />

<img width="725" height="298" alt="Captura de tela 2026-03-17 210707" src="https://github.com/user-attachments/assets/509d6001-5422-4a72-a906-5a167a289c33" />

Exemplo de codigo base inicial em HTML:

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Adote um Amigo</title>
    <style>
        body { font-family: sans-serif; margin: 0; padding: 0; background-color: #f4f4f4; }
        header { background: #ff9900; color: white; padding: 1rem; text-align: center; }
        .container { display: flex; flex-wrap: wrap; justify-content: center; padding: 20px; }
        .card { background: white; margin: 15px; width: 250px; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); overflow: hidden; }
        .card img { width: 100%; height: 200px; object-fit: cover; }
        .card-info { padding: 15px; }
        .btn-adotar { display: block; background: #ff9900; color: white; text-align: center; padding: 10px; text-decoration: none; border-radius: 5px; }
    </style>
</head>
<body>

<header>
    <h1>🐶 Adote um Amigo 🐱</h1>
    <p>Encontre o amor da sua vida aqui!</p>
</header>

<div class="container">
    <div class="card">
        <img src="https://images.unsplash.com/photo-1543466835-00a7907e9de1" alt="Cachorro">
        <div class="card-info">
            <h3>Rex</h3>
            <p>Porte Médio • 2 anos</p>
            <p>Dócil, brincalhão e vacinado.</p>
            <a href="#" class="btn-adotar">Quero Adotar</a>
        </div>
    </div>

    <div class="card">
        <img src="https://images.unsplash.com/photo-1514888286974-6c03e2ca1dba" alt="Gato">
        <div class="card-info">
            <h3>Luna</h3>
            <p>Gata • 6 meses</p>
            <p>Calma e carinhosa.</p>
            <a href="#" class="btn-adotar">Quero Adotar</a>
        </div>
    </div>
</div>

</body>
</html>

No Segundo momento o Propmt foi o seguinte:

crie um código de um site de doação de animais domésticos, em que posso criar um usuário para que traga confiança do usuário, com radar de proximidade de usuários, tenha categorias de separação de animais em html.

E esses foram os resultados:

<img width="795" height="363" alt="Captura de tela 2026-03-17 212934" src="https://github.com/user-attachments/assets/e8479f35-0998-49ca-8a87-c9ecdd7737d5" />

E o codigo entregue foi o seguinte em HTML:

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PetMatch - Adote com Confiança</title>
    <style>
        :root { --primary: #6c5ce7; --secondary: #a29bfe; --bg: #f9f9fb; }
        body { font-family: 'Segoe UI', sans-serif; background: var(--bg); margin: 0; color: #333; }
        
        header { background: var(--primary); color: white; padding: 1rem 5%; display: flex; justify-content: space-between; align-items: center; }
        
        .hero { text-align: center; padding: 40px 20px; background: white; }
        
        /* Categorias */
        .categories { display: flex; justify-content: center; gap: 15px; padding: 20px; flex-wrap: wrap; }
        .cat-btn { padding: 10px 25px; border: 2px solid var(--primary); border-radius: 20px; cursor: pointer; background: white; transition: 0.3s; }
        .cat-btn:hover, .cat-btn.active { background: var(--primary); color: white; }

        /* Radar e Cards */
        .main-content { display: grid; grid-template-columns: 1fr 350px; gap: 20px; padding: 20px 5%; }
        .pet-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 20px; }
        .pet-card { background: white; border-radius: 15px; overflow: hidden; box-shadow: 0 4px 15px rgba(0,0,0,0.05); }
        .pet-card img { width: 100%; height: 150px; object-fit: cover; }
        .pet-info { padding: 15px; }
        
        /* Sidebar de Confiança/Radar */
        .sidebar { background: #fff; padding: 20px; border-radius: 15px; border: 1px solid #ddd; height: fit-content; }
        .user-badge { display: flex; align-items: center; gap: 10px; margin-bottom: 20px; border-bottom: 1px solid #eee; padding-bottom: 10px; }
        .verified { color: #00b894; font-size: 0.8rem; font-weight: bold; }
        
        .radar-box { background: #2d3436; color: #55efc4; padding: 15px; border-radius: 10px; font-family: monospace; text-align: center; }
        .radar-pulse { border: 2px solid #55efc4; border-radius: 50%; width: 50px; height: 50px; margin: 10px auto; animation: pulse 2s infinite; }
        
        @keyframes pulse { 0% { transform: scale(0.5); opacity: 1; } 100% { transform: scale(1.5); opacity: 0; } }
    </style>
</head>
<body>

<header>
    <h2>🐾 PetMatch</h2>
    <div id="user-area">
        <button onclick="loginSimulado()" style="cursor:pointer">Entrar / Cadastrar</button>
    </div>
</header>

<section class="hero">
    <h1>Encontre um amigo perto de você</h1>
    <p>Conectando doadores verificados e adotantes responsáveis.</p>
</section>

<div class="categories">
    <button class="cat-btn active">Todos</button>
    <button class="cat-btn">Cães</button>
    <button class="cat-btn">Gatos</button>
    <button class="cat-btn">Aves</button>
    <button class="cat-btn">Outros</button>
</div>

<main class="main-content">
    <div class="pet-grid" id="petGrid">
        </div>

    <aside class="sidebar">
        <div id="profile-display">
            <p>Faça login para ver usuários próximos.</p>
        </div>
        
        <div class="radar-box">
            <div class="radar-pulse"></div>
            <strong>Radar de Proximidade</strong>
            <p id="location-status">Detectando localização...</p>
        </div>
    </aside>
</main>

<script>
    // Lógica para Simular Confiança e Proximidade
    const pets = [
        { nome: "Bolinha", tipo: "Cães", distancia: "1.2km", img: "https://placedog.net/400/300?id=1" },
        { nome: "Miau", tipo: "Gatos", distancia: "0.5km", img: "https://placekitten.com/400/300" },
        { nome: "Thor", tipo: "Cães", distancia: "3.7km", img: "https://placedog.net/400/300?id=2" }
    ];

    function renderPets() {
        const grid = document.getElementById('petGrid');
        grid.innerHTML = pets.map(pet => `
            <div class="pet-card">
                <img src="${pet.img}" alt="${pet.nome}">
                <div class="pet-info">
                    <h3>${pet.nome}</h3>
                    <p>📍 a ${pet.distancia} de você</p>
                    <button class="cat-btn" style="width:100%">Ver Perfil</button>
                </div>
            </div>
        `).join('');
    }

    function loginSimulado() {
        const userArea = document.getElementById('profile-display');
        userArea.innerHTML = `
            <div class="user-badge">
                <div style="width:40px;height:40px;background:#ccc;border-radius:50%"></div>
                <div>
                    <strong>Marcos Vinicius</strong><br>
                    <span class="verified">✓ DOADOR VERIFICADO</span>
                </div>
            </div>
            <p><small>Sua conta traz mais segurança para o processo de adoção.</small></p>
        `;
        obterLocalizacao();
    }

    function obterLocalizacao() {
        if (navigator.geolocation) {
            navigator.geolocation.getCurrentPosition((pos) => {
                document.getElementById('location-status').innerText = "3 usuários ativos em sua região";
            });
        }
    }

    renderPets();
</script>

</body>
</html>







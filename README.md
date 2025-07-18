# Estamparia-site
index.html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Estamparia Criativa</title>
  <link rel="stylesheet" href="estilo.css"/>
</head>
<body>
  <header>
    <h1>🎨 Estamparia Criativa</h1>
    <nav>
      <ul>
        <li><a href="#inicio">Início</a></li>
        <li><a href="#produtos">Produtos</a></li>
        <li><a href="#pedido">Faça seu Pedido</a></li>
        <li><a href="#feedback">Opiniões</a></li>
        <li><a href="#contato">Contato</a></li>
      </ul>
    </nav>
  </header>

  <section id="inicio">
    <h2>Transforme sua ideia em arte estampada</h2>
    <p>Personalizamos camisetas, canecas, ecobags, quadros e mais!</p>
  </section>

  <section id="produtos">
    <h2>Nossos Produtos</h2>
    <ul class="produtos-lista">
      <li>Camisetas</li>
      <li>Canecas</li>
      <li>Ecobags</li>
      <li>Capinhas</li>
      <li>Quadros</li>
    </ul>
  </section>

  <section id="pedido">
    <h2>Faça seu Pedido</h2>
    <form>
      <label>Produto:
        <select name="produto">
          <option>Camiseta</option>
          <option>Caneca</option>
          <option>Ecobag</option>
        </select>
      </label>

      <label>Tamanho:
        <input type="text" name="tamanho" placeholder="P, M, G...">
      </label>

      <label>Largura/Altura (cm):
        <input type="text" name="dimensoes" placeholder="Ex: 30x40">
      </label>

      <label>Cor do produto:
        <input type="color" name="cor">
      </label>

      <label>Upload da arte:
        <input type="file" name="arquivo">
      </label>

      <div id="preview">
        <h3>Preview da sua estampa:</h3>
        <img id="mockup" src="https://via.placeholder.com/200x200.png?text=Mockup" alt="Mockup" style="max-width: 200px;">
        <p>Estampa será sobreposta aqui ao processar o pedido.</p>
      </div>

      <label>Observações:
        <textarea name="observacoes" placeholder="Escreva aqui o que deseja..."></textarea>
      </label>

      <label>Seu nome:
        <input type="text" name="nome">
      </label>

      <label>E-mail:
        <input type="email" name="email">
      </label>

      <button type="submit">Enviar Pedido</button>
    </form>
  </section>

  <section id="feedback">
    <h2>Sua Opinião Importa</h2>
    <form>
      <label>Nome (opcional):
        <input type="text" name="nome-feedback">
      </label>

      <label>Nota:
        <select>
          <option>⭐</option>
          <option>⭐⭐</option>
          <option>⭐⭐⭐</option>
          <option>⭐⭐⭐⭐</option>
          <option>⭐⭐⭐⭐⭐</option>
        </select>
      </label>

      <label>Comentário:
        <textarea placeholder="Conte como foi sua experiência..."></textarea>
      </label>

      <label>Foto do produto (opcional):
        <input type="file">
      </label>

      <button type="submit">Enviar Feedback</button>
    </form>
  </section>

  <footer id="contato">
    <p>📧 contato@estampariacriativa.com.br | 📱 WhatsApp: (99) 99999-9999</p>
    <p>&copy; 2025 Estamparia Criativa</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>

estilo.css

body {
  font-family: 'Poppins', sans-serif;
  margin: 0;
  padding: 0;
  background: linear-gradient(135deg, #fdd835, #ff4081);
  color: #333;
}

header {
  background: #fff;
  padding: 1em;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

header h1 {
  color: #ff4081;
}

nav ul {
  list-style: none;
  display: flex;
  justify-content: center;
  padding: 0;
}

nav li {
  margin: 0 1em;
}

nav a {
  text-decoration: none;
  color: #333;
  font-weight: bold;
}

section {
  padding: 2em;
  background: #fff;
  margin: 1em auto;
  width: 90%;
  max-width: 800px;
  border-radius: 10px;
}

.produtos-lista {
  display: flex;
  flex-wrap: wrap;
  gap: 1em;
  justify-content: space-around;
}

form {
  display: flex;
  flex-direction: column;
  gap: 1em;
}

input, select, textarea, button {
  padding: 0.8em;
  border-radius: 5px;
  border: 1px solid #ccc;
}

button {
  background: #ff4081;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background: #f50057;
}

footer {
  text-align: center;
  padding: 1em;
  background: #fff;
  margin-top: 2em;
}
script.js
document.addEventListener("DOMContentLoaded", () => {
  const pedidoForm = document.querySelector("#pedido form");
  const feedbackForm = document.querySelector("#feedback form");

  pedidoForm.addEventListener("submit", (e) => {
    e.preventDefault();
    alert("✅ Pedido enviado com sucesso!\\nAguarde nosso contato em breve.");
    pedidoForm.reset();
  });

  feedbackForm.addEventListener("submit", (e) => {
    e.preventDefault();
    alert("🎉 Obrigado pelo seu feedback!");
    feedbackForm.reset();
  });

  const fileInput = document.querySelector('input[type="file"]');
  fileInput.addEventListener("change", function () {
    const preview = document.getElementById("mockup");
    const reader = new FileReader();

    reader.onload = function (e) {
      preview.src = e.target.result;
    };

    if (fileInput.files[0]) {
      reader.readAsDataURL(fileInput.files[0]);
    }
  });
});
index.html

html

<form method="post" action="#">
  <label for="produto">Produto:</label>
  <select id="produto" name="produto" required>
    <option value="camiseta">Camiseta</option>
    <option value="caneca">Caneca</option>
    <option value="ecobag">Ecobag</option>
  </select>

  <label for="tamanho">Tamanho:</label>
  <input id="tamanho" type="text" name="tamanho" placeholder="P, M, G..." required>
  ...
</form>

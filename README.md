# Plataforma-ONG-entrega-
Plataforma web desenvolvida como protótipo acadêmico para a disciplina de Desenvolvimento Web. O objetivo é simular uma plataforma de apoio a ONGs, com páginas de projetos, voluntariado, doações, galeria e contato.
.html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Contato — Plataforma ONG (Protótipo)</title>
  <link rel="stylesheet" href="css/00-variables.css">
  <link rel="stylesheet" href="css/01-base.css">
  <link rel="stylesheet" href="css/02-layout.css">
  <link rel="stylesheet" href="css/03-components.css">
  <link rel="stylesheet" href="css/04-utils.css">
</head>
<body>
  <header class="site-header">
    <div class="container header-inner">
      <a class="logo" href="index.html"><img src="assets/images/logo.png" alt="Logo da Plataforma ONG"></a>
      <nav class="main-nav" aria-label="Navegação principal">
        <button class="hamburger" aria-label="Abrir menu" aria-expanded="false">☰</button>
        <ul class="nav-list">
          <li><a href="index.html">Início</a></li>
          <li><a href="projetos.html">Projetos</a></li>
          <li><a href="voluntariado.html">Voluntariado</a></li>
          <li><a href="doacoes.html">Doações</a></li>
          <li><a href="galeria.html">Galeria</a></li>
          <li><a href="transparencia.html">Transparência</a></li>
          <li><a href="contato.html" aria-current="page">Contato</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="contact">
      <h1>Fale conosco</h1>
      <p>Preencha o formulário abaixo para entrar em contato com a equipe da Plataforma ONG (protótipo acadêmico).</p>

      <form id="contactForm" novalidate>
        <div class="card">
          <label for="nome">Nome</label>
          <input id="nome" name="nome" type="text" required />

          <label for="email">E-mail</label>
          <input id="email" name="email" type="email" required />

          <label for="mensagem">Mensagem</label>
          <textarea id="mensagem" name="mensagem" required></textarea>

          <div aria-live="polite" id="contact-feedback" class="sr-only"></div>

          <button type="submit" class="btn primary mt-16">Enviar Mensagem</button>
        </div>
      </form>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container text-center">
      <p>© 2025 — Plataforma ONG (Protótipo) — Entrega acadêmica</p>
      <p>Contato: <a href="mailto:valdineiacordeiro246@gmail.com">valdineiacordeiro246@gmail.com</a></p>
    </div>
  </footer>

  <div id="toast" class="toast" aria-live="polite"></div>

  <script src="js/main.js"></script>
  <script src="js/form-validation.js"></script>
  <script>
    // Formulário de contato: reforço (caso queira feedback textual no elemento #contact-feedback)
    document.addEventListener('DOMContentLoaded', () => {
      const form = document.getElementById('contactForm');
      const feedback = document.getElementById('contact-feedback');

      form?.addEventListener('submit', (e) => {
        e.preventDefault();
        if (!form.checkValidity()) {
          form.reportValidity();
          feedback.textContent = 'Por favor, preencha os campos obrigatórios.';
          feedback.classList.remove('sr-only');
          showToast('Preencha os campos obrigatórios');
          return;
        }

        // Simulação de envio
        feedback.textContent = 'Mensagem enviada com sucesso (simulação).';
        feedback.classList.remove('sr-only');
        showToast('Mensagem enviada com sucesso (simulado).');
        form.reset();
      });
    });
  </script>
</body>
</html>

2) doacoes.html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Doações — Plataforma ONG (Protótipo)</title>
  <link rel="stylesheet" href="css/00-variables.css">
  <link rel="stylesheet" href="css/01-base.css">
  <link rel="stylesheet" href="css/02-layout.css">
  <link rel="stylesheet" href="css/03-components.css">
  <link rel="stylesheet" href="css/04-utils.css">
</head>
<body>
  <header class="site-header">
    <div class="container header-inner">
      <a class="logo" href="index.html"><img src="assets/images/logo.png" alt="Logo da Plataforma ONG"></a>
      <nav class="main-nav" aria-label="Navegação principal">
        <button class="hamburger" aria-label="Abrir menu" aria-expanded="false">☰</button>
        <ul class="nav-list">
          <li><a href="index.html">Início</a></li>
          <li><a href="projetos.html">Projetos</a></li>
          <li><a href="voluntariado.html">Voluntariado</a></li>
          <li><a href="doacoes.html" aria-current="page">Doações</a></li>
          <li><a href="galeria.html">Galeria</a></li>
          <li><a href="transparencia.html">Transparência</a></li>
          <li><a href="contato.html">Contato</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="donation">
      <h1>Contribua com nossos projetos</h1>
      <p>Este formulário é uma simulação para fins acadêmicos. Para produção, integre um gateway de pagamento seguro.</p>

      <form id="donationForm" novalidate>
        <div class="card">
          <label for="donor-name">Nome</label>
          <input id="donor-name" name="nome" type="text" required value="Valdineia Cordeiro Reinaldo Silva" />

          <label for="donor-email">E-mail</label>
          <input id="donor-email" name="email" type="email" required value="valdineiacordeiro246@gmail.com" />

          <label for="donation-value">Valor (R$)</label>
          <input id="donation-value" name="valor" type="number" min="1" step="0.01" inputmode="decimal" placeholder="100.00" required value="100.00" />

          <label for="destino">Destinar para</label>
          <select id="destino" name="destino" required>
            <option value="">Selecione</option>
            <option value="fundo-geral">Fundo Geral</option>
            <option value="oficina-digital">Oficina Digital</option>
            <option value="banco-alimentos">Banco de Alimentos</option>
          </select>

          <div aria-live="polite" id="donation-feedback" class="sr-only"></div>

          <button type="submit" class="btn primary mt-16">Simular Doação</button>
        </div>
      </form>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container text-center">
      <p>© 2025 — Plataforma ONG (Protótipo) — Entrega acadêmica</p>
    </div>
  </footer>

  <div id="toast" class="toast" aria-live="polite"></div>

  <script src="js/main.js"></script>
  <script>
    // Validação simples do formulário de doação (simulação)
    document.addEventListener('DOMContentLoaded', () => {
      const form = document.getElementById('donationForm');
      const feedback = document.getElementById('donation-feedback');

      form?.addEventListener('submit', (e) => {
        e.preventDefault();
        if (!form.checkValidity()) {
          form.reportValidity();
          feedback.textContent = 'Por favor, preencha corretamente os campos de doação.';
          feedback.classList.remove('sr-only');
          showToast('Preencha os campos de doação');
          return;
        }

        // Simulação de processamento
        const valor = parseFloat(document.getElementById('donation-value').value || 0);
        if (isNaN(valor) || valor <= 0) {
          feedback.textContent = 'Informe um valor de doação maior que R$ 0,00.';
          feedback.classList.remove('sr-only');
          showToast('Informe um valor válido');
          return;
        }

        feedback.textContent = `Doação simulada de R$ ${valor.toFixed(2)} registrada (simulado). Obrigada!`;
        feedback.classList.remove('sr-only');
        showToast('Doação simulada realizada (simulado).');
        form.reset();
      });
    });
  </script>
</body>
</html>

3) galeria.html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Galeria — Plataforma ONG (Protótipo)</title>
  <link rel="stylesheet" href="css/00-variables.css">
  <link rel="stylesheet" href="css/01-base.css">
  <link rel="stylesheet" href="css/02-layout.css">
  <link rel="stylesheet" href="css/03-components.css">
  <link rel="stylesheet" href="css/04-utils.css">
  <style>
    /* Estilo local rápido para grid de galeria (pode ficar no css principal se preferir) */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
      gap: var(--space-16);
    }
    .gallery-grid figure { margin: 0; }
    .gallery-grid img { width:100%; height:auto; border-radius:8px; display:block; }
    .gallery-caption { margin-top:8px; font-size:var(--font-size-sm); color:var(--neutral-500); }
  </style>
</head>
<body>
  <header class="site-header">
    <div class="container header-inner">
      <a class="logo" href="index.html"><img src="assets/images/logo.png" alt="Logo da Plataforma ONG"></a>
      <nav class="main-nav" aria-label="Navegação principal">
        <button class="hamburger" aria-label="Abrir menu" aria-expanded="false">☰</button>
        <ul class="nav-list">
          <li><a href="index.html">Início</a></li>
          <li><a href="projetos.html">Projetos</a></li>
          <li><a href="voluntariado.html">Voluntariado</a></li>
          <li><a href="doacoes.html">Doações</a></li>
          <li><a href="galeria.html" aria-current="page">Galeria</a></li>
          <li><a href="transparencia.html">Transparência</a></li>
          <li><a href="contato.html">Contato</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main class="container">
    <section aria-labelledby="galeria-title">
      <h1 id="galeria-title">Galeria de Atividades</h1>
      <p>Galeria com imagens de atividades — use as imagens em <code>assets/images/</code> ou substitua por fotos reais.</p>

      <div class="gallery-grid">
        <!-- Exemplo: repita/cole até ter 20 imagens -->
        <figure>
          <img src="assets/images/projeto1.jpg" alt="Oficina digital com computadores">
          <figcaption class="gallery-caption">Oficina Digital — turma 2024</figcaption>
        </figure>

        <figure>
          <img src="assets/images/projeto1.jpg" alt="Momento de leitura com crianças">
          <figcaption class="gallery-caption">Programa de Leitura</figcaption>
        </figure>

        <figure>
          <img src="assets/images/projeto1.jpg" alt="Voluntários organizando doações">
          <figcaption class="gallery-caption">Banco de Alimentos</figcaption>
        </figure>

        <!-- Duplicate placeholders to reach 20 if necessário -->
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 4</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 5</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 6</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 7</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 8</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 9</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 10</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 11</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 12</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 13</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 14</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 15</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 16</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 17</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 18</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 19</figcaption></figure>
        <figure><img src="assets/images/projeto1.jpg" alt="Atividade placeholder"><figcaption class="gallery-caption">Galeria 20</figcaption></figure>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container text-center">
      <p>© 2025 — Plataforma ONG (Protótipo) — Entrega acadêmica</p>
    </div>
  </footer>

  <script src="js/main.js"></script>
</body>
</html>

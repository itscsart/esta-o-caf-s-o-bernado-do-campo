<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Estação Café</title>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --creme:#f3e7d7;
      --creme-claro:#fff4e7;
      --ferrugem:#a3472f;
      --ferrugem-escuro:#5b2619;
      --linha:rgba(163,71,47,.38);
    }

    *{margin:0;padding:0;box-sizing:border-box;}

    html{scroll-behavior:smooth;}

    body{
      background:var(--creme);
      color:var(--ferrugem);
      font-family:Arial, Helvetica, sans-serif;
      overflow-x:hidden;
    }

    h1,h2,h3,.logo-name,.footer-title{font-family:'Cinzel',serif;}

    header{
      width:100%;
      height:126px;
      background:var(--creme-claro);
      border-top:4px solid var(--ferrugem-escuro);
      border-bottom:1px solid var(--linha);
      display:flex;
      align-items:center;
      justify-content:space-between;
      padding:0 7.4%;
    }

    .logo{
      width:155px;
      text-align:center;
      color:var(--ferrugem);
      flex-shrink:0;
    }

    .logo-circle{
      width:86px;
      height:86px;
      margin:0 auto 5px;
      border:1.5px solid var(--ferrugem);
      border-radius:50%;
      display:flex;
      align-items:center;
      justify-content:center;
      position:relative;
      font-size:34px;
      line-height:1;
    }

    .logo-circle::after{
      content:"";
      position:absolute;
      inset:9px;
      border:1px solid var(--ferrugem);
      border-bottom-color:transparent;
      border-radius:50%;
    }

    .logo-name{
      display:block;
      font-size:20px;
      font-weight:700;
      line-height:1;
    }

    .logo-sub{
      display:block;
      font-size:8px;
      text-transform:uppercase;
      margin-top:4px;
      font-weight:700;
    }

    nav{
      display:flex;
      align-items:center;
      justify-content:flex-end;
      gap:34px;
      font-size:13px;
      font-weight:700;
      text-transform:uppercase;
    }

    nav a{
      color:var(--ferrugem);
      text-decoration:none;
      white-space:nowrap;
    }

    .btn{
      background:var(--ferrugem);
      color:var(--creme-claro);
      border:0;
      border-radius:5px;
      padding:13px 30px;
      font-size:13px;
      font-weight:700;
      text-transform:uppercase;
      cursor:pointer;
      transition:.25s ease;
    }

    .btn:hover{background:#7e3322;transform:translateY(-2px);}

    .hero{
      height:462px;
      position:relative;
      display:flex;
      align-items:center;
      padding:0 7.4%;
      background-image:
        linear-gradient(90deg,rgba(243,231,215,.96) 0%,rgba(243,231,215,.78) 35%,rgba(243,231,215,.04) 69%),
        url('./assets/hero.jpg');
      background-size:cover;
      background-position:center center;
      border-bottom:0;
      overflow:hidden;
    }

    .hero-content{
      width:510px;
      animation:fadeUp .8s ease both;
    }

    @keyframes fadeUp{
      from{opacity:0;transform:translateY(24px)}
      to{opacity:1;transform:translateY(0)}
    }

    .hero h1{
      color:var(--ferrugem);
      font-size:49px;
      line-height:1.12;
      letter-spacing:.3px;
      margin-bottom:22px;
    }

    .hero p{
      color:var(--ferrugem-escuro);
      font-size:19px;
      line-height:1.5;
      width:390px;
      margin-bottom:26px;
    }

    .arrow{
      width:45px;
      height:45px;
      border:1px solid var(--ferrugem);
      border-radius:50%;
      display:flex;
      align-items:center;
      justify-content:center;
      color:var(--ferrugem);
      font-size:28px;
      position:absolute;
      top:50%;
      transform:translateY(-50%);
      background:rgba(243,231,215,.32);
      z-index:3;
    }

    .arrow.left{left:25px;}
    .arrow.right{right:25px;}

    .products-section{
      background:linear-gradient(180deg,#fff1e3 0%,var(--creme) 100%);
      padding-bottom:48px;
    }

    .section-title{
      text-align:center;
      padding:51px 7.4% 31px;
    }

    .title-row{
      display:flex;
      justify-content:center;
      align-items:center;
      gap:28px;
      margin-bottom:16px;
    }

    .title-row::before,.title-row::after{
      content:"";
      width:216px;
      height:1px;
      background:var(--ferrugem);
      opacity:.78;
    }

    .section-title h2{
      color:var(--ferrugem);
      font-size:34px;
      line-height:1;
      letter-spacing:2px;
      white-space:nowrap;
    }

    .section-title p{
      color:var(--ferrugem-escuro);
      font-size:16px;
      line-height:1.5;
    }

    .section-title .mini-cup{
      display:inline-block;
      color:var(--ferrugem);
      font-size:21px;
      margin:0 14px;
      vertical-align:middle;
    }

    .cards{
      display:grid;
      grid-template-columns:repeat(4,1fr);
      gap:22px;
      padding:0 3.3%;
    }

    .card{
      background:rgba(255,244,231,.62);
      border:1px solid var(--linha);
      border-radius:8px;
      overflow:hidden;
      text-align:center;
      min-height:592px;
      transition:.3s ease;
    }

    .card:hover{
      transform:translateY(-8px);
      box-shadow:0 18px 40px rgba(91,38,25,.16);
    }

    .photo{
      height:288px;
      width:100%;
      background-size:cover;
      background-position:center;
    }

    .bolo{background-image:url('https://images.unsplash.com/photo-1578985545062-69928b1d9587?auto=format&fit=crop&w=900&q=90');}
    .paoqueijo{background-image:url('https://images.unsplash.com/photo-1598373182133-52452f7691ef?auto=format&fit=crop&w=900&q=90');}
    .paoitaliano{background-image:url('https://images.unsplash.com/photo-1509440159596-0249088772ff?auto=format&fit=crop&w=900&q=90');}
    .doceleite{background-image:url('https://images.unsplash.com/photo-1606326608690-4e0281b1e588?auto=format&fit=crop&w=900&q=90');}

    .card-body{
      padding:25px 22px 27px;
      min-height:304px;
      display:flex;
      flex-direction:column;
      align-items:center;
    }

    .icon{
      width:54px;
      height:54px;
      margin-bottom:13px;
      display:flex;
      align-items:center;
      justify-content:center;
      color:var(--ferrugem);
    }

    .icon svg{
      width:45px;
      height:45px;
      stroke:var(--ferrugem);
      stroke-width:1.7;
      fill:none;
    }

    .card h3{
      color:var(--ferrugem);
      font-size:21px;
      margin-bottom:12px;
      line-height:1.1;
    }

    .card p{
      color:var(--ferrugem-escuro);
      font-size:15px;
      line-height:1.45;
      width:240px;
      max-width:100%;
      margin:0 auto;
      flex:1;
    }

    .small-line{
      width:28px;
      height:1px;
      background:var(--ferrugem);
      margin:19px 0;
    }

    .outline{
      background:transparent;
      color:var(--ferrugem);
      border:1px solid var(--ferrugem);
      padding:11px 25px;
    }

    .history{
      margin:0 3.3%;
      border-top:1px solid var(--ferrugem);
      display:grid;
      grid-template-columns:1.12fr 1.1fr 1fr .75fr;
      gap:33px;
      align-items:center;
      padding:34px 0 35px;
    }

    .train-art{
      min-height:150px;
      display:flex;
      align-items:center;
      justify-content:center;
      color:var(--ferrugem);
      font-size:98px;
      opacity:.88;
    }

    .history h2{
      color:var(--ferrugem);
      font-size:28px;
      line-height:1.1;
      margin-bottom:10px;
    }

    .history h3{
      color:var(--ferrugem);
      font-size:21px;
      line-height:1.2;
      margin-bottom:10px;
    }

    .history p{
      color:var(--ferrugem-escuro);
      font-size:15px;
      line-height:1.55;
    }

    .history .divider{
      border-left:1px solid var(--linha);
      padding-left:34px;
      min-height:145px;
      display:flex;
      flex-direction:column;
      justify-content:center;
    }

    .stamp{
      width:120px;
      height:120px;
      border:1px solid var(--ferrugem);
      border-radius:50%;
      display:flex;
      align-items:center;
      justify-content:center;
      text-align:center;
      margin:auto;
      color:var(--ferrugem);
      font-family:'Cinzel',serif;
      font-size:14px;
      line-height:1.38;
      text-transform:uppercase;
    }

    footer{
      height:74px;
      background:linear-gradient(90deg,#9d3e28,#b84a2e);
      color:var(--creme-claro);
      display:flex;
      align-items:center;
      justify-content:center;
      gap:36px;
      padding:0 7.4%;
    }

    .footer-icon{font-size:36px;line-height:1;}

    .footer-title{
      font-size:25px;
      font-weight:700;
      white-space:nowrap;
    }

    footer p{
      font-size:14px;
      white-space:nowrap;
    }

    footer .outline{
      border-color:var(--creme-claro);
      color:var(--creme-claro);
      padding:10px 28px;
      white-space:nowrap;
    }

    @media(max-width:1100px){
      nav{gap:18px;font-size:12px;}
      .cards{grid-template-columns:repeat(2,1fr);padding:0 5%;}
      .history{grid-template-columns:1fr;margin:0 5%;}
      .history .divider{border-left:0;padding-left:0;}
      footer{height:auto;padding:22px 5%;flex-wrap:wrap;text-align:center;}
    }

    @media(max-width:720px){
      header{height:112px;padding:0 5%;}
      nav{display:none;}
      .logo-circle{width:68px;height:68px;font-size:28px;}
      .logo-name{font-size:16px;}
      .hero{height:500px;padding:0 8%;background-position:center right;}
      .hero h1{font-size:36px;}
      .hero p{width:auto;font-size:17px;}
      .arrow{display:none;}
      .title-row::before,.title-row::after{width:48px;}
      .section-title h2{font-size:25px;white-space:normal;}
      .cards{grid-template-columns:1fr;}
      .card{min-height:auto;}
      .photo{height:250px;}
      footer{flex-direction:column;gap:14px;}
      footer p,.footer-title{white-space:normal;}
    }
  </style>
</head>
<body>
  <header>
    <div class="logo">
      <div class="logo-circle">☕</div>
      <span class="logo-name">ESTAÇÃO CAFÉ</span>
      <span class="logo-sub">O café de quem faz história</span>
    </div>

    <nav>
      <a href="#cardapio">Cardápio⌄</a>
      <a href="#clube">Clube Estação</a>
      <a href="#gift">Gift Card</a>
      <a href="#loja">Encontrar Loja</a>
      <a href="#app">App Estação</a>
      <a href="#eventos">Eventos</a>
      <button class="btn">Comprar</button>
    </nav>
  </header>

  <main>
    <section class="hero">
      <div class="arrow left">‹</div>
      <div class="arrow right">›</div>

      <div class="hero-content">
        <h1>Café que conecta histórias</h1>
        <p>Grãos selecionados e torrados para momentos únicos.</p>
        <button class="btn">Conheça nossos produtos</button>
      </div>
    </section>

    <section class="products-section" id="cardapio">
      <div class="section-title">
        <div class="title-row">
          <h2>Nossos Produtos Caseiros</h2>
        </div>
        <p>Feitos com ingredientes selecionados e muito <span class="mini-cup">☕</span>, para você saborear o que é feito de verdade.</p>
      </div>

      <div class="cards">
        <article class="card">
          <div class="photo bolo"></div>
          <div class="card-body">
            <div class="icon">
              <svg viewBox="0 0 64 64"><path d="M12 30h40v22H12z"/><path d="M16 30l16-14 16 14"/><path d="M32 16v-6"/><path d="M28 10c0-4 8-4 8 0"/></svg>
            </div>
            <h3>Bolos Caseiros</h3>
            <p>Receitas tradicionais feitas no dia, com sabor que lembra casa de vó.</p>
            <div class="small-line"></div>
            <button class="btn outline">Saiba mais</button>
          </div>
        </article>

        <article class="card">
          <div class="photo paoqueijo"></div>
          <div class="card-body">
            <div class="icon">
              <svg viewBox="0 0 64 64"><circle cx="32" cy="32" r="19"/><circle cx="25" cy="27" r="2"/><circle cx="38" cy="28" r="2"/><circle cx="30" cy="39" r="2"/></svg>
            </div>
            <h3>Pão de Queijo</h3>
            <p>Crocante por fora, macio por dentro e feito com queijo de verdade.</p>
            <div class="small-line"></div>
            <button class="btn outline">Saiba mais</button>
          </div>
        </article>

        <article class="card">
          <div class="photo paoitaliano"></div>
          <div class="card-body">
            <div class="icon">
              <svg viewBox="0 0 64 64"><path d="M11 39c5-16 36-18 43 0v9H11z"/><path d="M23 31c4 4 7 5 12 5"/><path d="M34 27c4 4 8 5 13 5"/></svg>
            </div>
            <h3>Pão Italiano</h3>
            <p>Casquinha crocante, miolo leve e fresquinho como tem que ser.</p>
            <div class="small-line"></div>
            <button class="btn outline">Saiba mais</button>
          </div>
        </article>

        <article class="card">
          <div class="photo doceleite"></div>
          <div class="card-body">
            <div class="icon">
              <svg viewBox="0 0 64 64"><path d="M20 20h24l-2 34H22z"/><path d="M18 14h28v6H18z"/><path d="M25 10h14"/></svg>
            </div>
            <h3>Doce de Leite</h3>
            <p>Cremoso e irresistível, feito com leite selecionado e receita especial.</p>
            <div class="small-line"></div>
            <button class="btn outline">Saiba mais</button>
          </div>
        </article>
      </div>

      <section class="history">
        <div class="train-art">🚂</div>

        <div>
          <h2>Nossa História</h2>
          <p>A Estação Café nasceu em São Bernardo do Campo com o propósito de valorizar o que é feito com dedicação, tempo e paixão. Mais que café, entregamos experiências que conectam pessoas e constroem histórias.</p>
          <br>
          <button class="btn outline">Conheça mais</button>
        </div>

        <div class="divider">
          <h3>Grãos Selecionados</h3>
          <p>Sustentabilidade e qualidade em cada etapa do nosso processo.</p>
        </div>

        <div class="stamp">Feito com amor<br>para você</div>
      </section>
    </section>
  </main>

  <footer id="clube">
    <div class="footer-icon">☕</div>
    <div class="footer-title">Faça parte do Clube Estação</div>
    <p>Ofertas exclusivas, descontos e benefícios para quem ama café.</p>
    <button class="btn outline">Saiba mais</button>
  </footer>
</body>
</html>

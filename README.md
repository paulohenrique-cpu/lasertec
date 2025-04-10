<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Orçamento Gamer - Lasertec</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <img src="images/logo.png" alt="Logo Lasertec" class="logo">
    <h1>Monte Seu PC Gamer</h1>

    <form id="orcamentoForm" action="https://formsubmit.co/SEU_EMAIL_AQUI" method="POST">
      <input type="hidden" name="_subject" value="Novo orçamento de PC - Lasertec">
      <input type="hidden" name="_template" value="box">
      <input type="hidden" id="detalhes" name="Orçamento">

      <label for="cpuMarca">Escolha o tipo de processador:</label>
      <select id="cpuMarca" onchange="filtrarComponentes()">
        <option value="">Selecione</option>
        <option value="amd">AMD</option>
        <option value="intel">Intel</option>
      </select>

      <div id="componentes"></div>

      <div id="total">Total: R$0</div>

      <input type="email" name="email" required placeholder="Seu e-mail para receber o orçamento">
      <button type="submit">Enviar Orçamento</button>
    </form>
  </div>

  <script>
    const componentesData = {
      amd: [
        { nome: "AMD Ryzen 5 5600X", preco: 950, imagem: "images/ryzen5-5600x.png" },
        { nome: "AMD Ryzen 7 5800X", preco: 1450, imagem: "images/ryzen7-5800x.png" },
        { nome: "Placa-Mãe B450", preco: 600, imagem: "images/b450.png" },
        { nome: "Placa-Mãe X570", preco: 950, imagem: "images/x570.png" },
      ],
      intel: [
        { nome: "Intel Core i5 12400F", preco: 1100, imagem: "images/i5-12400f.png" },
        { nome: "Intel Core i7 12700K", preco: 1850, imagem: "images/i7-12700k.png" },
        { nome: "Placa-Mãe B660", preco: 750, imagem: "images/b660.png" },
        { nome: "Placa-Mãe Z690", preco: 1200, imagem: "images/z690.png" },
      ],
      comuns: [
        { nome: "Memória RAM 16GB DDR4", preco: 350, imagem: "images/ram16.png" },
        { nome: "Memória RAM 32GB DDR4", preco: 650, imagem: "images/ram32.png" },
        { nome: "SSD NVMe 1TB", preco: 480, imagem: "images/ssd-nvme-1tb.png" },
        { nome: "SSD SATA 1TB", preco: 400, imagem: "images/ssd-sata-1tb.png" },
        { nome: "HD 2TB", preco: 350, imagem: "images/hdd-2tb.png" },
        { nome: "Gabinete Gamer RGB", preco: 450, imagem: "images/gabinete-rgb.png" },
        { nome: "Fonte 600W 80 Plus", preco: 300, imagem: "images/fonte-600w.png" },
        { nome: "Fonte 750W Modular", preco: 520, imagem: "images/fonte-750w.png" },
        { nome: "Water Cooler 240mm", preco: 450, imagem: "images/watercooler-240mm.png" },
        { nome: "Cooler RGB", preco: 180, imagem: "images/cooler-r

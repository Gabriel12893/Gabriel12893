<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estudos Bíblicos Pessoais</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #fffbea;
            color: #333;
            margin: 0;
            padding: 20px;
        }
        header {
            text-align: center;
            padding: 20px;
            background-color: #ffebcd;
            border-bottom: 1px solid #ddd;
        }
        header h1 {
            margin: 0;
        }
        nav {
            margin: 20px 0;
            text-align: center;
        }
        nav a {
            margin: 0 10px;
            text-decoration: none;
            color: #333;
        }
        section {
            margin: 20px 0;
        }
        .search-bar {
            text-align: center;
            margin: 20px 0;
        }
        .highlight {
            background-color: #fffacd;
        }
        .download-link {
            display: block;
            margin-top: 10px;
            text-align: right;
        }
    </style>
    <script>
        function highlightText() {
            var text = window.getSelection().toString();
            if (text) {
                document.execCommand('hiliteColor', false, '#fffacd');
            }
        }

        function readAloud(text) {
            var speech = new SpeechSynthesisUtterance(text);
            window.speechSynthesis.speak(speech);
        }
    </script>
</head>
<body>
    <header>
        <h1>Estudos Bíblicos Pessoais</h1>
    </header>

    <nav>
        <a href="#genesis">Gênesis</a>
        <a href="#exodus">Êxodo</a>
        <!-- Adicione links para outros livros aqui -->
    </nav>

    <div class="search-bar">
        <input type="text" id="search" placeholder="Buscar livros e capítulos...">
        <button onclick="search()">Buscar</button>
    </div>

    <section id="genesis">
        <h2>Gênesis</h2>
        <p onclick="highlightText()">No princípio, Deus criou os céus e a terra. (Gênesis 1:1)</p>
        <button onclick="readAloud('No princípio, Deus criou os céus e a terra.')">Ler em voz alta</button>
        <a class="download-link" href="genesis.pdf" download>Download do estudo</a>
    </section>

    <section id="exodus">
        <h2>Êxodo</h2>
        <p onclick="highlightText()">E Deus falou todas estas palavras: "Eu sou o Senhor, o teu Deus, que te tirei do Egito, da terra da escravidão." (Êxodo 20:1-2)</p>
        <button onclick="readAloud('E Deus falou todas estas palavras: Eu sou o Senhor, o teu Deus, que te tirei do Egito, da terra da escravidão.')">Ler em voz alta</button>
        <a class="download-link" href="exodus.pdf" download>Download do estudo</a>
    </section>

    <!-- Adicione seções para outros livros aqui -->

    <script>
        function search() {
            var query = document.getElementById('search').value.toLowerCase();
            var sections = document.querySelectorAll('section');
            sections.forEach(function(section) {
                if (section.textContent.toLowerCase().includes(query)) {
                    section.style.display = 'block';
                } else {
                    section.style.display = 'none';
                }
            });
        }
    </script>
</body>
</html>


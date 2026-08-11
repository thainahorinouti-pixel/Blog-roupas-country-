<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blog Completo - HTML, CSS & JavaScript</title>
    
    <style>
        /* --- 1. VARIÁVEIS E TEMAS --- */
        :root {
            --bg-color: #f5efe6;
            --text-color: #3e2723;
            --primary-color: #8d6e63;
            --primary-dark: #5d4037;
            --border-color: #d7ccc8;
            --card-bg: #ffffff;
            --shadow: rgba(0, 0, 0, 0.08);
        }

        body.dark-theme {
            --bg-color: #1e1b18;
            --text-color: #e0d8d0;
            --primary-color: #a1887f;
            --primary-dark: #d7ccc8;
            --border-color: #4e342e;
            --card-bg: #2d2623;
            --shadow: rgba(0, 0, 0, 0.4);
        }

        /* --- 2. RESET E REGRAS GERAIS --- */
        *, *::before, *::after {
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding: 0;
            line-height: 1.6;
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        /* --- 3. HEADER E FERRAMENTAS --- */
        header {
            background-color: var(--primary-color);
            color: #ffffff;
            padding: 2.5rem 1rem;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 2.2rem;
            letter-spacing: -0.5px;
        }

        header p {
            margin: 0.5rem 0 0 0;
            font-style: italic;
            opacity: 0.9;
        }

        .header-tools {
            margin-top: 1.5rem;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        #search-input {
            padding: 0.6rem 1rem;
            border-radius: 20px;
            border: none;
            outline: none;
            width: 260px;
            font-size: 0.9rem;
            box-shadow: 0 2px 6px rgba(0,0,0,0.1);
        }

        #theme-toggle {
            background-color: transparent;
            border: 2px solid #ffffff;
            color: #ffffff;
            padding: 0.5rem 1.2rem;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.2s ease;
        }

        #theme-toggle:hover {
            background-color: #ffffff;
            color: var(--primary-color);
        }

        /* --- 4. CONTEÚDO PRINCIPAL E GRID --- */
        main {
            max-width: 900px;
            width: 90%;
            margin: 2rem auto;
        }

        .section-title {
            color: var(--primary-dark);
            margin-bottom: 1.5rem;
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 0.5rem;
        }

        .articles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 1.5rem;
        }

        /* --- 5. CARDS DE ARTIGO --- */
        article {
            background-color: var(--card-bg);
            padding: 1.5rem;
            border-left: 5px solid var(--primary-color);
            border-radius: 8px;
            box-shadow: 0 4px 10px var(--shadow);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: transform 0.2s ease, box-shadow 0.2s ease, background-color 0.3s ease;
        }

        article:hover {
            transform: translateY(-4px);
            box-shadow: 0 6px 14px var(--shadow);
        }

        article h3 {
            margin-top: 0;
            color: var(--primary-dark);
        }

        article p {
            font-size: 0.95rem;
            flex-grow: 1;
        }

        a.read-more {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            margin-top: 1rem;
            display: inline-block;
            transition: color 0.2s ease;
        }

        a.read-more:hover {
            color: var(--primary-dark);
            text-decoration: underline;
        }

        /* --- 6. FOOTER --- */
        footer {
            text-align: center;
            padding: 1.5rem;
            background-color: var(--card-bg);
            border-top: 1px solid var(--border-color);
            margin-top: 3rem;
            font-size: 0.9rem;
        }

        /* --- 7. RESPONSIVIDADE --- */
        @media (max-width: 600px) {
            header h1 {
                font-size: 1.8rem;
            }

            .header-tools {
                flex-direction: column;
            }

            #search-input {
                width: 100%;
                max-width: 300px;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>Diário de Desenvolvimento</h1>
        <p>Anotações, projetos e dicas sobre desenvolvimento web</p>

        <div class="header-tools">
            <input type="text" id="search-input" placeholder="Buscar artigos..." aria-label="Buscar artigos">
            <button id="theme-toggle" aria-label="Alternar Tema">🌙 Modo Escuro</button>
        </div>
    </header>

    <main>
        <section>
            <h2 class="section-title">Últimas Publicações</h2>
            
            <div class="articles-grid" id="articles-container">
                <article>
                    <h3>HTML5 Semântico</h3>
                    <p>Entenda como utilizar elementos semânticos para estruturar páginas mais acessíveis e amigáveis para motores de busca.</p>
                    <a href="#" class="read-more">Leia mais &rarr;</a>
                </article>

                <article>
                    <h3>Layouts com CSS Grid</h3>
                    <p>Aprenda a construir layouts responsivos e flexíveis em duas dimensões com poucas linhas de código CSS.</p>
                    <a href="#" class="read-more">Leia mais &rarr;</a>
                </article>

                <article>
                    <h3>Manipulação de DOM com JS</h3>
                    <p>Descubra como interagir com elementos HTML e criar experiências dinâmicas utilizando JavaScript puro.</p>
                    <a href="#" class="read-more">Leia mais &rarr;</a>
                </article>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 Diário de Desenvolvimento. Todos os direitos reservados.</p>
    </footer>

    <script>
        // --- MODO ESCURO / CLARO ---
        const themeBtn = document.getElementById('theme-toggle');
        const body = document.body;

        // Recupera preferência salva no navegador
        if (localStorage.getItem('theme') === 'dark') {
            body.classList.add('dark-theme');
            themeBtn.textContent = '☀️ Modo Claro';
        }

        themeBtn.addEventListener('click', () => {
            body.classList.toggle('dark-theme');
            const isDark = body.classList.contains('dark-theme');

            themeBtn.textContent = isDark ? '☀️ Modo Claro' : '🌙 Modo Escuro';
            localStorage.setItem('theme', isDark ? 'dark' : 'light');
        });

        // --- FILTRO DE BUSCA EM TEMPO REAL ---
        const searchInput = document.getElementById('search-input');
        const articles = document.querySelectorAll('#articles-container article');

        searchInput.addEventListener('input', (e) => {
            const searchTerm = e.target.value.toLowerCase().trim();

            articles.forEach(article => {
                const title = article.querySelector('h3').textContent.toLowerCase();
                const text = article.querySelector('p').textContent.toLowerCase();

                if (title.includes(searchTerm) || text.includes(searchTerm)) {
                    article.style.display = 'flex';
                } else {
                    article.style.display = 'none';
                }
            });
        });
    </script>
</body>
</html>

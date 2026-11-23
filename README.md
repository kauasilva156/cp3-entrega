# Handshake

Quiz de tecnologia sobre **redes e internet**: HTTP, HTTPS, DNS, IP, URL, métodos e códigos de status.

**Site publicado (HTTPS):** _cole aqui o link do GitHub Pages_
**Repositório:** _cole aqui o link do GitHub_

## Tema

Escolhemos redes e internet porque é a base de tudo o que a web faz: todo site, aplicativo e jogo online depende desses conceitos. O quiz ensina o que acontece "nos bastidores" quando se abre uma página. O nome *Handshake* vem do "aperto de mãos" entre cliente e servidor ao iniciar uma conexão.

## Integrantes e papéis

| Nome | RM | O que construiu |
|------|----|-----------------|
| _Nome 1_ | _RM_ | Página inicial e campo de nome (`index.html`, `js/inicio.js`) |
| _Nome 2_ | _RM_ | Tela de jogo, pontuação e ranking (`jogo.html`, `js/jogo.js`) |
| _Nome 3_ | _RM_ | Identidade visual e acessibilidade (`css/style.css`, `img/`) |
| _Nome 4_ | _RM_ | Banco de perguntas e documentação (`perguntas.json`, README) |

## Regras do jogo

1. Digite seu nome (mínimo de 2 caracteres) e clique em **Jogar**.
2. São **10 perguntas** de múltipla escolha, em ordem aleatória, uma por vez.
3. Cada acerto vale **1 ponto**; a pontuação máxima é 10.
4. Depois de responder, você vê se acertou, a explicação e o link da fonte. Não é possível trocar a resposta.
5. No fim aparecem sua pontuação e o **ranking da sessão** (top 5). Em caso de empate, quem pontuou primeiro fica à frente.
6. **Jogar novamente** recomeça sem recarregar a página; o ranking é mantido.

## Como executar

O jogo carrega o `perguntas.json` com `fetch`:

- **Online:** acesse o link do site publicado.
- **Local:** extensão **Live Server** do VS Code, ou `python -m http.server` na pasta e abrir `http://localhost:8000`.
- **Duplo clique no `index.html`:** o navegador bloqueia o `fetch`; nesse caso o jogo usa `js/perguntas-reserva.js`, uma cópia gerada do JSON.

**Ao editar o `perguntas.json`, rode `python gerar-reserva.py`** para atualizar a reserva.

## Estrutura do projeto

| Arquivo | Função |
|---------|--------|
| `index.html`, `js/inicio.js` | Página inicial e nome do jogador |
| `jogo.html`, `js/jogo.js` | Perguntas, feedback, pontuação, ranking e replay |
| `css/style.css` | Identidade visual (paleta escura azul/verde/dourada; Space Grotesk e Inter) |
| `img/logo.svg` | Logotipo e favicon |
| `perguntas.json` | Banco de 10 perguntas (fonte dos dados) |
| `js/perguntas-reserva.js`, `gerar-reserva.py` | Cópia de segurança gerada do JSON |

## Ranking (`sessionStorage`)

Ao terminar a partida, o jogo lê a lista salva em `sessionStorage` (chave `ranking`) com `JSON.parse`, acrescenta `{nome, pontos, total}`, grava de novo com `JSON.stringify`, ordena por pontos e exibe o top 5. Persiste entre partidas e ao recarregar a mesma aba, e some ao fechá-la. Para conferir: DevTools (F12) → Application → Session Storage.

## Acessibilidade e responsividade: o que verificamos

- **Teclado:** jogamos o quiz inteiro só com Tab, Enter (e Espaço), do nome ao replay. O foco vai para a pergunta, depois para o botão "Próxima", depois para o título final. Há link "Pular para o conteúdo".
- **Foco visível:** contorno amarelo de 3 px em todos os controles (links, botões, alternativas e campo de nome).
- **Contraste:** texto com no mínimo 4,5:1 contra o fundo em todas as telas e estados (acerto, erro, ranking).
- **Cor não é a única pista:** acerto e erro aparecem com texto ("Resposta correta ✓", "Incorreta ✗ — a certa era B"), etiqueta na alternativa ("✓ Correta", "✗ Sua resposta") e borda tracejada no erro. As posições do ranking têm número e texto.
- **`alt`:** o logotipo tem texto alternativo descritivo.
- **Leitores de tela:** o feedback usa `role="status"`; o erro do nome usa `role="alert"`; `lang="pt-BR"` em todas as páginas.
- **Responsivo:** sem rolagem horizontal em 320, 390, 768, 1280 e 1920 px; alternativas em uma coluna no celular.
- **Testado em:** _liste aqui os navegadores e dispositivos que o grupo usou_.

## Publicação e entrega

1. GitHub: **Settings → Pages → Deploy from a branch → `main` / root** (HTTPS automático).
2. Tag da entrega: **Releases → Create a new release** criando a tag `cp3-entrega` (ou `git tag -a cp3-entrega -m "Entrega final" && git push origin cp3-entrega`).

## Fontes das perguntas

As explicações e os links de cada pergunta vêm da documentação da MDN Web Docs (developer.mozilla.org).

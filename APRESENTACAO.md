# Roteiro da apresentação (Aula 13)

## Antes de começar
- [ ] Abrir o site publicado (HTTPS) em uma aba **nova**: o ranking começa zerado.
- [ ] Testar o jogo inteiro na véspera, em pelo menos dois dispositivos.
- [ ] Ter o link à mão (QR Code ou link curto).
- [ ] Clicar em todos os "Ver fonte" para conferir os links.
- [ ] Conferir o link no Blackboard e a tag `cp3-entrega` no repositório.

## Demonstração (cerca de 3 min)
1. Página inicial: nome, tema, descrição. Digitar o nome.
2. Responder só com o teclado (Tab/Enter) para mostrar a acessibilidade; errar uma de propósito para mostrar o feedback textual.
3. Tela final: pontuação e ranking. **Jogar novamente** e mostrar que o ranking cresce.
4. DevTools → Application → Session Storage → `ranking`.

## Fala de cada integrante (30 s)
| Integrante | Mostrar e explicar |
|------------|--------------------|
| Nome 1 | `index.html` e `inicio.js`: validação do nome e `sessionStorage.setItem("jogador")` |
| Nome 2 | `jogo.js`: `fetch` do JSON, `responder()`, `avancar()`, pontuação |
| Nome 3 | `style.css`: variáveis de cor, foco visível, responsivo, contraste |
| Nome 4 | `perguntas.json`: estrutura, fontes, revisão do português |

Todos devem saber explicar qualquer parte. Ensaiem trocando de parte.

## Perguntas prováveis (adaptem com suas palavras)
- **Por que esse tema?** Redes e internet são a base de todo software web; queríamos um tema que ajudasse colegas a entender o que acontece por trás de uma página.
- **Como o ranking funciona?** No fim da partida o código lê a lista do `sessionStorage` (`JSON.parse`), adiciona nome e pontos, salva (`JSON.stringify`), ordena por pontos (empate: quem jogou primeiro) e mostra o top 5. Dura enquanto a aba estiver aberta.
- **Por que `fetch` e por que existe a reserva?** As perguntas ficam fora do código, no JSON. Ao abrir o arquivo com duplo clique o navegador bloqueia o `fetch`; a reserva evita a tela vazia.
- **Como garantiram acessibilidade?** Teclado, foco visível, contraste de pelo menos 4,5:1, texto e ícone além da cor, `alt`, `lang`, `aria-live`.
- **O que foi mais difícil?** _Respondam com a experiência real do grupo (ex.: conflitos no Git, contraste, ranking)._

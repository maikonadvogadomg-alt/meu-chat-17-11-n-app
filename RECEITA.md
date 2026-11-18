# 🧬 Receita para recriar: Meu Chat

_Gerada sem IA, lendo 38 arquivo(s). Serve para remontar este app como HTML modular — com qualquer IA, um arquivo por vez._

## 1. O que é

- **Nome:** Meu Chat
- **Partes de código:** 31 (1 tela, 29 logica, 0 servidor, 0 dados, 1 estilo)
- **Tem servidor (rotas /api):** não — dá para ser só HTML
- **Peças de fora (bibliotecas):** nenhuma

## 2. Estrutura modular proposta

```
index.html            ← a página; chama os módulos NA ORDEM
css/app.css           ← o visual
js/00-core.js         ← a "locomotiva": cria window.APP (registrar, guardar, avisar)
js/10-base.js         ← Meu Chat — 00-base.js: peças comuns (MC) (era js/00-base.js)
js/15-banco.js        ← Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho (era js/10-banco.js)
js/20-nuvem.js        ← Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua (era js/12-nuvem.js)
js/25-entrada.js      ← Meu Chat — 14-entrada.js · 🔑 TELA DE LOGIN NA ENTRADA (17/11) Igual à (era js/14-entrada.js)
js/30-provedores.js   ← Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenR (era js/20-provedores.js)
js/35-memoria.js      ← Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. (era js/30-memoria.js)
js/40-contextos.js    ← Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que vo (era js/33-contextos.js)
js/45-guia.js         ← 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual  (era js/34-guia.js)
js/50-jeito.js        ← Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança d (era js/35-jeito.js)
js/55-gasto.js        ← Meu Chat — 36-gasto.js · 💰 QUANTO GASTOU (17/11) Igual ao da Monica:  (era js/36-gasto.js)
js/60-arquivos.js     ← Meu Chat — 37-arquivos.js · 📎 ARQUIVOS, 📦 ZIP e 🔤 ACENTOS (17/11) - (era js/37-arquivos.js)
js/65-codigos.js      ← Meu Chat — 38-codigos.js · 🧪 MEUS CÓDIGOS (17/11) Igual ao playground (era js/38-codigos.js)
js/70-qr.js           ← Meu Chat — 39-qr.js · 🔳 LER QR CODE (17/11) Aponta a câmera (ou escol (era js/39-qr.js)
js/75-voz.js          ← Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS (era js/40-voz.js)
js/80-internet.js     ← Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Cla (era js/50-internet.js)
js/85-previa.js       ← Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: (era js/60-previa.js)
js/90-texto.js        ← Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, li (era js/70-texto.js)
js/91-chat.js         ← Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, li (era js/80-chat.js)
js/92-config.js       ← Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instru (era js/85-config.js)
js/93-cofre.js        ← Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (era js/87-cofre.js)
js/94-backup.js       ← Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajus (era js/90-backup.js)
js/95-ponte-lab.js    ← 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratór (era js/95-ponte-lab.js)
js/96-cofre-arquivo.js← 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Ch (era js/lib/cofre-arquivo.js)
js/97-guia-maikon.js  ← 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mi (era js/lib/guia-maikon.js)
js/98-guia-versoes.js ← 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, (era js/lib/guia-versoes.js)
js/98-nuvem-neon.js   ← 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HT (era js/lib/nuvem-neon.js)
js/98-nuvem-embutida.js← ☁️ SUPABASE EMBUTIDO (17/11) Estas duas informações são PÚBLICAS de pr (era js/nuvem-embutida.js)
js/98-voz-francisco.js← !/usr/bin/env python3 -*- coding: utf-8 -*- (era voz-francisco.py)
js/98-inicio.js       ← Meu Chat (era index.html)
js/99-app.js          ← o último: monta a tela com o que embarcou
```

## 3. As partes, uma por uma

| # | Era | Vira | Tipo | O que faz | Usa |
|---|---|---|---|---|---|
| 1 | `js/00-base.js` | `js/10-base.js` | logica | Meu Chat — 00-base.js: peças comuns (MC) | — |
| 2 | `js/10-banco.js` | `js/15-banco.js` | logica | Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho — não some ao fecha | — |
| 3 | `js/12-nuvem.js` | `js/20-nuvem.js` | logica | Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua funcionando SEM int | — |
| 4 | `js/14-entrada.js` | `js/25-entrada.js` | logica | Meu Chat — 14-entrada.js · 🔑 TELA DE LOGIN NA ENTRADA (17/11) Igual à Replit: abriu o Meu | — |
| 5 | `js/20-provedores.js` | `js/30-provedores.js` | logica | Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenRouter, OpenAI, DeepS | — |
| 6 | `js/30-memoria.js` | `js/35-memoria.js` | logica | Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. A IA guarda sozinha | — |
| 7 | `js/33-contextos.js` | `js/40-contextos.js` | logica | Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que você LIGA e DESLIGA. D | — |
| 8 | `js/34-guia.js` | `js/45-guia.js` | logica | 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual e COMO USAR, passo a | — |
| 9 | `js/35-jeito.js` | `js/50-jeito.js` | logica | Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança drástica" quando troc | — |
| 10 | `js/36-gasto.js` | `js/55-gasto.js` | logica | Meu Chat — 36-gasto.js · 💰 QUANTO GASTOU (17/11) Igual ao da Monica: embaixo de cada resp | — |
| 11 | `js/37-arquivos.js` | `js/60-arquivos.js` | logica | Meu Chat — 37-arquivos.js · 📎 ARQUIVOS, 📦 ZIP e 🔤 ACENTOS (17/11) - 🔤 Lê qualquer text | — |
| 12 | `js/38-codigos.js` | `js/65-codigos.js` | logica | Meu Chat — 38-codigos.js · 🧪 MEUS CÓDIGOS (17/11) Igual ao playground do jurídico origina | — |
| 13 | `js/39-qr.js` | `js/70-qr.js` | logica | Meu Chat — 39-qr.js · 🔳 LER QR CODE (17/11) Aponta a câmera (ou escolhe um print) e o tex | — |
| 14 | `js/40-voz.js` | `js/75-voz.js` | logica | Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS "motores" de voz (⚙ | — |
| 15 | `js/50-internet.js` | `js/80-internet.js` | logica | Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Claude pesquisam sozinh | — |
| 16 | `js/60-previa.js` | `js/85-previa.js` | logica | Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: abre a página como  | — |
| 17 | `js/70-texto.js` | `js/90-texto.js` | logica | Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, listas, links, blocos  | — |
| 18 | `js/80-chat.js` | `js/91-chat.js` | logica | Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, lista de conversas). C | — |
| 19 | `js/85-config.js` | `js/92-config.js` | logica | Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instruções, tema | — |
| 20 | `js/87-cofre.js` | `js/93-cofre.js` | logica | Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (👁 ver, 📋 copiar) | — |
| 21 | `js/90-backup.js` | `js/94-backup.js` | logica | Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajustes) e restaurar SEM | — |
| 22 | `js/95-ponte-lab.js` | `js/95-ponte-lab.js` | logica | 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratório (aba 🤖 IA), o La | — |
| 23 | `js/99-app.js` | css/app.css | logica | Meu Chat — 99-app.js: liga tudo quando abre | — |
| 24 | `js/lib/cofre-arquivo.js` | `js/96-cofre-arquivo.js` | logica | 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Chat e no que vier dep | — |
| 25 | `js/lib/guia-maikon.js` | `js/97-guia-maikon.js` | logica | 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mini SK, Meu Chat…). A | — |
| 26 | `js/lib/guia-versoes.js` | `js/98-guia-versoes.js` | logica | 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, e COMO USAR (passo  | — |
| 27 | `js/lib/nuvem-neon.js` | `js/98-nuvem-neon.js` | logica | 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HTML. Você cola o ende | — |
| 28 | `js/nuvem-embutida.js` | `js/98-nuvem-embutida.js` | logica | ☁️ SUPABASE EMBUTIDO (17/11) Estas duas informações são PÚBLICAS de propósito (todo site q | — |
| 29 | `voz-francisco.py` | `js/98-voz-francisco.js` | logica | !/usr/bin/env python3 -*- coding: utf-8 -*- | — |
| 30 | `css/app.css` | css/app.css | estilo | — | — |
| 31 | `index.html` | `js/98-inicio.js` | tela | Meu Chat | manifest.json, icon-192.png, app.css, 00-base.js |

## 4. Montar passo a passo (cada bloco é um pedido pronto: 📋 Copiar → colar na IA)

### Passo 0 — combinar as regras com a IA

```text
Vamos recriar o app "Meu Chat" como HTML MODULAR, que abre pelo index.html, sem servidor e sem nada da Replit.
Regras: (1) index.html chama os arquivos js/ na ordem, antes do </body>; (2) js/00-core.js cria window.APP com APP.registrar(modulo), APP.guardar(chave, valor) em IndexedDB/localStorage e APP.avisar(texto); (3) cada arquivo js/NN-nome.js cuida de UM assunto, começa com (function (APP) { e termina com })(window.APP); (4) js/99-app.js vem por último e monta a tela com os módulos registrados; (5) textos em português do Brasil.
Vou pedir UM arquivo por vez. Responda só com o arquivo completo, sem cortar nada. Primeiro: crie index.html, css/app.css e js/00-core.js.
```

### Passo 1 — `js/10-base.js` (era `js/00-base.js`, 43 linhas)

```text
Crie js/10-base.js. Ele faz: Meu Chat — 00-base.js: peças comuns (MC).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 2 — `js/15-banco.js` (era `js/10-banco.js`, 26 linhas)

```text
Crie js/15-banco.js. Ele faz: Meu Chat — 10-banco.js: onde tudo fica guardado (IndexedDB do aparelho — não some ao fechar).
No app original ele tinha estas funções/partes: abrir, req, loja.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 3 — `js/20-nuvem.js` (era `js/12-nuvem.js`, 311 linhas)

```text
Crie js/20-nuvem.js. Ele faz: Meu Chat — 12-nuvem.js · ☁️ NUVEM (Supabase) — 17/11 - O chat continua funcionando SEM internet: tudo fica no aparelho (IndexedDB). - Com a nuvem ligada, ele COPIA para o Supabase e traz de volta em qualquer aparelho (celular, PC, outro celular) entrando com o mesmo e-mail e senha.
No app original ele tinha estas funções/partes: temEmb, cfg, sessao, ehNeon, neonConn, logado, ligada, auth, traduzir, guardarSessao, token, rest, mod, horaUnica, marcar, ganchos, marcarPrefs, prefsViajam.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 4 — `js/25-entrada.js` (era `js/14-entrada.js`, 76 linhas)

```text
Crie js/25-entrada.js. Ele faz: Meu Chat — 14-entrada.js · 🔑 TELA DE LOGIN NA ENTRADA (17/11) Igual à Replit: abriu o Meu Chat em qualquer lugar (celular, PC, PWA, APK) → e-mail + senha → as conversas, a memória, os códigos guardados E as chaves de IA aparecem. Ninguém cola endereço. Só aparece quando o Supabase vem EMBUTIDO (js/nuvem-embutida.js) e você ainda não entrou aqui.
No app original ele tinha estas funções/partes: dentroDeOutroApp, precisa, mostrar, msg, recuperacao.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 5 — `js/30-provedores.js` (era `js/20-provedores.js`, 249 linhas)

```text
Crie js/30-provedores.js. Ele faz: Meu Chat — 20-provedores.js: conversar com as IAs (Gemini, Groq, OpenRouter, OpenAI, DeepSeek, Claude). - Várias chaves; quando uma acaba (limite/cota), passa sozinho para a próxima ("revezar"). - Busca a lista de modelos de verdade na hora de testar a chave (nada de nome velho chumbado). - As chaves ficam SÓ neste aparelho.
No app original ele tinha estas funções/partes: detectar, procurarOllama, chaves, salvarChaves, pontoGemini, listarModelos, pontoLivre, geracao, modeloDe, testarChave, erroLegivel, corsAviso, ehLimite, cabAnthropic, lerSSE, estimar, pedir, parcial.
Ele chamava estes endereços: http://127.0.0.1:11434/api/tags. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 6 — `js/35-memoria.js` (era `js/30-memoria.js`, 77 linhas)

```text
Crie js/35-memoria.js. Ele faz: Meu Chat — 30-memoria.js: 🧠 a memória que vai junto em TODA conversa. A IA guarda sozinha o que for importante escrevendo [[lembrar: …]] no fim da resposta (o app tira isso do texto, guarda e mostra "🧠 guardei"). [[esquecer: …]] apaga.
No app original ele tinha estas funções/partes: texto, salvar, lembrar, esquecer, aplicarMarcas, guiaParaPergunta, tamanhoTexto, sistema, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 7 — `js/40-contextos.js` (era `js/33-contextos.js`, 178 linhas)

```text
Crie js/40-contextos.js. Ele faz: Meu Chat — 33-contextos.js: 📌 CONTEXTOS — "cartões" de assunto que você LIGA e DESLIGA. Diferente da 🧠 memória (que vale para sempre e vai em tudo): um contexto é o resumo de um assunto ou de uma conversa (por exemplo, o que você vinha fazendo com o Claude), para a IA não começar do zero. Ligado = vai junto em toda conversa. Desligado = fica guardado, sem gastar.
No app original ele tinha estas funções/partes: lista, gravar, semear, esconder, tokens, ligados, texto, pintarChip, pintar, novo, clique.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 8 — `js/45-guia.js` (era `js/34-guia.js`, 39 linhas)

```text
Crie js/45-guia.js. Ele faz: 🧭 Painel do Guia (16/11): o que é cada app do Maikon, a versão atual e COMO USAR, passo a passo. 🔊 lê em voz alta (voz Francisco ou a do aparelho) · 🤖 Perguntar: o chat explica aquele app.
No app original ele tinha estas funções/partes: textoDe, pintar, iniciar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 9 — `js/50-jeito.js` (era `js/35-jeito.js`, 56 linhas)

```text
Crie js/50-jeito.js. Ele faz: Meu Chat — 35-jeito.js: 🎭 O JEITO DE CADA IA. Para não ter "mudança drástica" quando troca de IA: um jeito de conversar que vale para TODAS (parceiro, calmo, honesto) e, se quiser, um jeito só de uma (ex.: o Perplexity como pesquisador jurídico que sempre traz as fontes). Tudo editável em ⚙️ → 🎭 Jeito de cada IA.
No app original ele tinha estas funções/partes: geral, deUma, texto, pintar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 10 — `js/55-gasto.js` (era `js/36-gasto.js`, 101 linhas)

```text
Crie js/55-gasto.js. Ele faz: Meu Chat — 36-gasto.js · 💰 QUANTO GASTOU (17/11) Igual ao da Monica: embaixo de cada resposta aparece quantos "tokens" foram e quanto custou, e o painel 💰 mostra o gasto de hoje, da semana e do mês, por IA. - "Entrada" = tudo que vai junto na pergunta: regras, memória, guia, contextos e o HISTÓRICO da conversa.
No app original ele tinha estas funções/partes: tabela, dolar, geminiPago, preco, custo, mil, reais, texto, dia, registrar, somar, pintar, linhaT, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 11 — `js/60-arquivos.js` (era `js/37-arquivos.js`, 70 linhas)

```text
Crie js/60-arquivos.js. Ele faz: Meu Chat — 37-arquivos.js · 📎 ARQUIVOS, 📦 ZIP e 🔤 ACENTOS (17/11) - 🔤 Lê qualquer texto com os acentos certos: tenta UTF-8 e, se não for, Windows-1252/Latin-1 (era o "negócio de UTF-8" que fazia outros sites não lerem o arquivo). - 📦 Projeto .zip: abre AQUI DENTRO, mostra a árvore, deixa ver cada arquivo e você marca.
No app original ele tinha estas funções/partes: lerTexto, textoDoArquivo, tokens, mil, abrirZip, conta, pintar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 12 — `js/65-codigos.js` (era `js/38-codigos.js`, 52 linhas)

```text
Crie js/65-codigos.js. Ele faz: Meu Chat — 38-codigos.js · 🧪 MEUS CÓDIGOS (17/11) Igual ao playground do jurídico original: cada código que a IA fizer tem o botão 💾 Guardar. Ficam aqui, com nome, e vão para a nuvem (com o login, aparecem em qualquer aparelho). Abrir = abre no ▶ playground (ver funcionando e mexer). Nada some sem você confirmar.
No app original ele tinha estas funções/partes: todos, gravar, tituloDe, guardar, pintar, clique, atualizar, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 13 — `js/70-qr.js` (era `js/39-qr.js`, 69 linhas)

```text
Crie js/70-qr.js. Ele faz: Meu Chat — 39-qr.js · 🔳 LER QR CODE (17/11) Aponta a câmera (ou escolhe um print) e o texto do QR vai para a caixa de mensagem. Entende os QR em sequência do Colecionador ("1 de 5, 2 de 5…"): junta sozinho, em qualquer ordem.
No app original ele tinha estas funções/partes: carregar, descompactar, detector, parar, entregar, juntar, abrir, laco.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 14 — `js/75-voz.js` (era `js/40-voz.js`, 227 linhas)

```text
Crie js/75-voz.js. Ele faz: Meu Chat — 40-voz.js: 🎤 falar (ditado) e 🔊 ouvir a resposta. 🔊 DOIS "motores" de voz (⚙️ → Voz): - 📱 "Voz do aparelho" (o padrão): funciona com QUALQUER IA (Gemini, Groq, Claude, Ollama…), grátis e sem limite. Você escolhe a voz (as ⭐ são as naturais), a velocidade e o tom.
No app original ele tinha estas funções/partes: podeOuvir, ouvir, parar, marcar, paraFala, pedacos, noPC, motor, temAndroid, temNavegador, natural, vozesAparelho, cfgVoz, falarFrase, enfileirar, verificarFim, pararAparelho, fluxo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 15 — `js/80-internet.js` (era `js/50-internet.js`, 58 linhas)

```text
Crie js/80-internet.js. Ele faz: Meu Chat — 50-internet.js: 🌐 pesquisar e 🔗 ler links. - Gemini e Claude pesquisam sozinhos (a busca vem embutida neles). - As outras IAs: usa a SUA chave de busca (Serper, Tavily ou Brave), se tiver, e manda os resultados junto. - Link na mensagem: o app lê a página (pelo leitor r.jina.ai, grátis) e manda o texto para a IA.
No app original ele tinha estas funções/partes: buscar, lerLink, preparar.
Ele chamava estes endereços: https://google.serper.dev/search, https://api.tavily.com/search, https://api.search.brave.com/res/v1/web/search?count=8&country=BR&search_lang=pt-br&q=, https://r.jina.ai/. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 16 — `js/85-previa.js` (era `js/60-previa.js`, 86 linhas)

```text
Crie js/85-previa.js. Ele faz: Meu Chat — 60-previa.js: 👁 ver o código funcionando, na hora. - HTML: abre a página como ela é. - TSX / JSX (React): monta com React + Babel + Tailwind (pela internet) e mostra o componente. Os erros aparecem embaixo, em vermelho.
No app original ele tinha estas funções/partes: paginaHTML, paginaReact, falha, req, App, tipoDe, abrir.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 17 — `js/90-texto.js` (era `js/70-texto.js`, 46 linhas)

```text
Crie js/90-texto.js. Ele faz: Meu Chat — 70-texto.js: mostra a resposta da IA bonitinha (negrito, listas, links, blocos de código com 📋 copiar, ⤓ baixar e 👁 ver funcionando).
No app original ele tinha estas funções/partes: inline, render, ligar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 18 — `js/91-chat.js` (era `js/80-chat.js`, 266 linhas)

```text
Crie js/91-chat.js. Ele faz: Meu Chat — 80-chat.js: a conversa (mensagens, fotos, mandar, parar, lista de conversas). Cada conversa fica guardada no aparelho. Vai para a IA: a memória + as últimas mensagens.
No app original ele tinha estas funções/partes: nova, abrirConversa, guardar, reduzir, anexar, pintarAnexos, htmlMsg, dedup, hora, pintar, mandar, responder, depois, comparar, juntar, tela, escolherComparar, resumirSePrecisar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 19 — `js/92-config.js` (era `js/85-config.js`, 115 linhas)

```text
Crie js/92-config.js. Ele faz: Meu Chat — 85-config.js: ⚙️ chaves das IAs, modelo, busca, voz, instruções, tema.
No app original ele tinha estas funções/partes: opcoesVoz, pintar, clique, mudou, aplicarTema, abrir.
Ele chamava estes endereços: voz-francisco.py. Em HTML, ligue cada um à função equivalente do módulo certo.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 20 — `js/93-cofre.js` (era `js/87-cofre.js`, 96 linhas)

```text
Crie js/93-cofre.js. Ele faz: Meu Chat — 87-cofre.js: 🔐 Cofre de chaves. Mostra cada chave guardada (👁 ver, 📋 copiar) e leva SÓ as chaves para outro app/aparelho num arquivo trancado com senha — o mesmo arquivo do Mini SK (js/lib/cofre-arquivo.js).
No app original ele tinha estas funções/partes: todas, pintar, status, conteudo, baixar, trazer, selarTexto, trazerTexto.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 21 — `js/94-backup.js` (era `js/90-backup.js`, 44 linhas)

```text
Crie js/94-backup.js. Ele faz: Meu Chat — 90-backup.js: 💾 backup de tudo (conversas + memória + ajustes) e restaurar SEM APAGAR NADA.
No app original ele tinha estas funções/partes: gerar, baixar, restaurar.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 22 — `js/95-ponte-lab.js` (era `js/95-ponte-lab.js`, 20 linhas)

```text
Crie js/95-ponte-lab.js. Ele faz: 🔬 Ponte com o Laboratório: quando o Meu Chat está DENTRO do Laboratório (aba 🤖 IA), o Laboratório pode mandar texto para a caixa de escrever (o plano do projeto, a memória, a comparação A × B). Só aceita mensagens da própria página (mesmo endereço).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 23 — `js/96-cofre-arquivo.js` (era `js/lib/cofre-arquivo.js`, 61 linhas)

```text
Crie js/96-cofre-arquivo.js. Ele faz: 🔐 Arquivo de chaves do Maikon — o MESMO formato no Mini SK, no Meu Chat e no que vier depois. Guarda SÓ as chaves (IA, GitHub, Expo, pesquisa e "Minhas chaves"), trancadas com uma senha sua (AES-GCM 256 + PBKDF2 com 250 mil voltas — sem a senha, o arquivo não abre). Assim dá para levar as chaves de um app/aparelho para outro sem passar pelo WhatsApp.
No app original ele tinha estas funções/partes: b64, deB64, chaveDaSenha, normal, selar, abrir, contar, mascara.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 24 — `js/97-guia-maikon.js` (era `js/lib/guia-maikon.js`, 118 linhas)

```text
Crie js/97-guia-maikon.js. Ele faz: 🧭 Guia das ferramentas do Maikon — o MESMO texto em todos os apps (Mini SK, Meu Chat…). A IA de cada app lê isto sozinha: assim ela já sabe o que ele tem, para que serve cada coisa, e quando é melhor mandar para outra ferramenta ou "levar para o Claude". Para atualizar: troque este arquivo nos apps (o Claude manda a versão nova junto).
No app original ele tinha estas funções/partes: resumoParaClaude, esconder.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 25 — `js/98-guia-versoes.js` (era `js/lib/guia-versoes.js`, 178 linhas)

```text
Crie js/98-guia-versoes.js. Ele faz: 🧭 Guia das VERSÕES — o que é cada app do Maikon, qual a versão atual, e COMO USAR (passo a passo). Uma fonte só: o painel 🧭 do Meu Chat mostra isto para ele ler, e a IA recebe o mesmo texto (junto do guia-maikon.js) para saber explicar. Atualizado pelo Claude a cada versão nova.
No app original ele tinha estas funções/partes: texto.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 26 — `js/98-nuvem-neon.js` (era `js/lib/nuvem-neon.js`, 73 linhas)

```text
Crie js/98-nuvem-neon.js. Ele faz: 🐘 Nuvem pelo NEON (17/11) — usada pelo Meu Chat e pelo SK Jurídico HTML. Você cola o endereço do banco (a "connection string" postgresql://…) e pronto: o app cria a tabela SOZINHO (não precisa rodar nada em inglês no site do Neon). ⚠ Esse endereço tem a SENHA do banco: fica só no seu aparelho (como uma chave de IA),.
No app original ele tinha estas funções/partes: traduzir, preparar, upsert, listar, conv.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 27 — `js/98-nuvem-embutida.js` (era `js/nuvem-embutida.js`, 11 linhas)

```text
Crie js/98-nuvem-embutida.js. Ele faz: ☁️ SUPABASE EMBUTIDO (17/11) Estas duas informações são PÚBLICAS de propósito (todo site que usa Supabase tem elas dentro). Quem protege os seus dados é o LOGIN (e-mail e senha) e a regra "cada um vê o seu" da tabela. Com elas aqui dentro, em qualquer aparelho o app abre a tela de login: e-mail + senha e pronto.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 28 — `js/98-voz-francisco.js` (era `voz-francisco.py`, 134 linhas)

```text
Crie js/98-voz-francisco.js. Ele faz: !/usr/bin/env python3 -*- coding: utf-8 -*-.
No app original ele tinha estas funções/partes: _listar, _falar, Voz, _cabecalhos, do_OPTIONS, _json, _pedido, do_GET, do_POST, _tratar, log_message.
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 29 — `js/98-inicio.js` (era `index.html`, 135 linhas)

```text
Crie js/98-inicio.js. Ele faz: Meu Chat.
Ele usa o que já foi criado em: js/10-base.js, js/15-banco.js, js/98-nuvem-embutida.js, js/98-nuvem-neon.js, js/20-nuvem.js, js/25-entrada.js, js/30-provedores.js, js/35-memoria.js, js/40-contextos.js, js/45-guia.js, js/50-jeito.js, js/55-gasto.js, js/60-arquivos.js, js/65-codigos.js, js/70-qr.js, js/75-voz.js, js/80-internet.js, js/85-previa.js, js/90-texto.js, js/91-chat.js, js/96-cofre-arquivo.js, js/98-guia-versoes.js, js/97-guia-maikon.js, js/92-config.js, js/93-cofre.js, js/94-backup.js, js/95-ponte-lab.js (pelo APP).
Registre com APP.registrar({ nome, icone, abrir }). Devolva só o arquivo completo.
```

### Passo 30 — `js/99-app.js` e conferir

```text
Crie js/99-app.js: ele olha APP.modulos e monta o menu/abas com um botão para cada módulo. Depois, me mande o index.html atualizado com todos os <script src="js/…"> na ordem certa: js/00-core.js, js/10-base.js, js/15-banco.js, js/20-nuvem.js, js/25-entrada.js, js/30-provedores.js, js/35-memoria.js, js/40-contextos.js, js/45-guia.js, js/50-jeito.js, js/55-gasto.js, js/60-arquivos.js, js/65-codigos.js, js/70-qr.js, js/75-voz.js, js/80-internet.js, js/85-previa.js, js/90-texto.js, js/91-chat.js, js/92-config.js, js/93-cofre.js, js/94-backup.js, js/95-ponte-lab.js, js/96-cofre-arquivo.js, js/97-guia-maikon.js, js/98-guia-versoes.js, js/98-nuvem-neon.js, js/98-nuvem-embutida.js, js/98-voz-francisco.js, js/98-inicio.js, js/99-app.js.
```

## 5. Conferir no final

- [ ] Abrir o index.html na prévia: aparece a tela sem erro (▤ console vazio)?
- [ ] Cada botão abre a sua parte?
- [ ] Fechar e abrir de novo: os dados continuam?
- [ ] Nada com "replit", "REPL_", "@workspace" no código (🏗️ Preparar confere).
- [ ] 📱 PWA → deixar instalável; 📦 APK ou 🖥️ .exe.

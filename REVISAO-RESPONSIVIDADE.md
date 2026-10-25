# Revisão da interface — Desvendando o Céu Austral

**Data:** 19/10/2026  
**Escopo:** versão estática (`site-html/`), alterações compartilhadas de acessibilidade/contato na aplicação React, favicons, referências locais, HTML/CSS/JavaScript e TSX.

## Resumo das melhorias aplicadas

- Abaixo de **430 px**, os cartões de atividade empilham a fotografia acima do título e da descrição e usam uma proporção consistente de 16:9. Isso remove a coluna estreita de texto e o espaço vazio observado em cartões longos no celular.
- Ajustada a cor dos pequenos rótulos de seção para **`#815700`**, com contraste calculado de **6.37:1** sobre branco (mínimo recomendado para texto normal: 4,5:1). O dourado claro continua reservado a fundos escuros, onde é mais legível.
- Adicionado o link “Pular para o conteúdo principal” e o destino `#conteudo`, incluindo na versão React, para melhorar navegação por teclado.
- O endereço de telefone permanece visível como texto e não aparece como botão de ligação; os links de WhatsApp continuam funcionais.
- Favicon SVG corresponde byte a byte ao arquivo do usuário; o ICO é mantido como fallback nas duas versões publicáveis.
- Mantidas a alternância de tema claro/escuro, o menu móvel, o comportamento de galeria e o suporte a `prefers-reduced-motion`.

## Matriz de responsividade no Chromium

A versão estática foi renderizada no **Chromium headless 144.0.7559.96** com Playwright e testada em **30 combinações**: 15 larguras e dois temas (claro/escuro).

Larguras: 320 px, 360 px, 375 px, 390 px, 414 px, 600 px, 760 px, 768 px, 820 px, 980 px, 1024 px, 1080 px, 1180 px, 1280 px, 1440 px.

| Verificação | Resultado |
|---|---:|
| Combinações de viewport/tema | 30 |
| Casos com rolagem horizontal indevida | 0 |
| Erros de carregamento de imagem no Chromium, somados nas configurações | 0 |
| Imagens com dimensões inválidas, somadas nas configurações | 0 |
| Interseções geométricas entre região da foto e corpo do cartão de atividade | 0 |
| Erros de console / exceções JavaScript | 0 / 0 |

A matriz completa está em `docs/chromium-responsive-matrix.csv`.

## Testes funcionais realizados no Chromium

- Tema: clique alterna de claro para escuro (`data-theme=dark`, `aria-pressed=true`) e retorna para claro.
- Menu móvel: abre com `aria-expanded=true` e fecha ao selecionar a navegação para Atividades (`aria-expanded=false`).
- Galeria: a primeira imagem abre em visualização ampliada; Escape fecha a visualização e o texto alternativo da imagem aberta é preenchido.
- Teclado: o link de pulo ao conteúdo é o primeiro ponto de foco e aparece quando recebe foco.
- As fotografias de carregamento tardio foram provocadas ao percorrer a página antes da matriz de testes.

## Auditoria estrutural

- `site-html/index.html`: 53 links, todos com destino; 12 fragmentos internos e todos resolvidos; 17 IDs sem duplicidade.
- **39 referências locais de imagem** foram encontradas no HTML, representando 18 arquivos; nenhum arquivo referenciado está ausente ou corrompido. Há 40 elementos de imagem no documento; a imagem da caixa de ampliação inicia sem `src` e é preenchida quando a galeria abre.
- Nenhum link com `target="_blank"` sem `rel="noopener noreferrer"` na versão estática ou na rota React; links externos da rota React foram padronizados para esse atributo de segurança.
- A rota React foi auditada por AST: os seis hrefs de fragmento utilizados apontam para IDs existentes e os 17 imports locais de imagem existem.
- Nenhum link `tel:`; números de telefone são texto e WhatsApp continua como hiperlink.
- Ambos os scripts embutidos passam em `node --check`; o CSS estático e `src/styles.css` não reportam erros de parsing.
- Os arquivos TSX verificados não têm diagnósticos de sintaxe ao passar por `typescript.transpileModule`. **Isso é uma checagem sintática, não substitui o build completo**.

## Nota de transparência sobre o método

A política administrativa do ambiente bloqueia a navegação do Chromium por URL, inclusive `file://`. Para efetuar uma inspeção real de layout e comportamento sem desativar esse controle, a página estática original foi carregada com `document.set_content()` no Chromium e seus próprios arquivos locais foram embutidos temporariamente como `data:` URLs **somente no conteúdo usado para teste**. O HTML/CSS/JavaScript efetivamente renderizado é o do projeto, mas isso não equivale a verificar o deployment via URL.

O aplicativo React/TanStack foi inspecionado estaticamente e teve seus TSX analisados sintaticamente, porém **não foi iniciado em um servidor Vite nem submetido a um build de produção** nesta sessão, pois suas dependências não estavam instaladas no ambiente. Para um lançamento final, recomenda-se executar `npm install` e `npm run build` no ambiente de publicação e verificar o endereço publicado.

## Arquivos para consulta

- `docs/chromium-responsive-matrix.csv` — medidas por largura e tema.
- `docs/LINKS-AUDIT.md` — destinos internos e externos.
- `docs/static-audit.json` — resultados estruturados de auditoria.

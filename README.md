# Desvendando o Céu Austral — site institucional

Site responsivo do Museu de Ciências Desvendando o Céu Austral, iniciativa de extensão da Universidade Federal Rural de Pernambuco (UFRPE).

## Conteúdo incluído

- Proposta de popularização da ciência e formação de monitores.
- Linha do tempo com registros públicos desde 2014, passando pelas mostras e ações itinerantes, visitas ao OASI, eventos de divulgação e inauguração do Museu em 2026.
- Descrições de observações astronômicas, oficinas de foguetes, teatro científico, mediação, palestras, visitas técnicas e ações itinerantes.
- Seção sobre o Observatório Astronômico do Sertão de Itaparica (OASI), a cooperação com o Observatório Nacional e a relação com a Semana POP.
- Contextualização das ações educativas ligadas a Santa Filomena e ao Meteorito Serra do Magé, em Alagoinha.
- Galeria baseada no acervo local de 16 fotografias recebido no projeto e na fotografia da equipe diante da cúpula do observatório. As imagens de conteúdo foram convertidas para WebP para reduzir o peso e melhorar o carregamento em celulares.
- Contatos, WhatsApp, Instagram e e-mail do Museu.
- Links de referência para notícias institucionais da UFRPE, Observatório Nacional, ALEPE e outros registros de atividades.

## Desenvolvimento local

O projeto usa Vite, React, TypeScript, TanStack Start, Tailwind CSS e lucide-react. Para executar localmente, instale as dependências e rode o servidor de desenvolvimento:

```sh
npm install
npm run dev
```

Para gerar a versão de produção:

```sh
npm run build
```

## Observação editorial

O site distingue cooperações e ações documentadas de convênios jurídicos específicos: não presume que todas as atividades sejam regidas por um instrumento formal permanente. As datas e registros históricos têm links para fontes públicas quando disponíveis.


## Ajustes para celular

- Navegação móvel com área rolável, botões táteis maiores e fechamento automático após selecionar uma seção.
- Layout mobile-first, textos ajustados para telas estreitas, ancoragem de seções considerando a barra fixa e suporte a áreas seguras do telefone.
- Galeria com visualização ampliada; a imagem pode ser fechada tocando fora dela ou pressionando Escape em teclado.
- Imagens locais de atividades servidas em WebP para economizar transferência de dados.


## Versão HTML estática (sem React)

A pasta `site-html/` contém uma versão completa em HTML, CSS e JavaScript nativo. Ela é independente das dependências do aplicativo React e usa imagens locais do acervo. Para testar, abra `site-html/index.html`. Para hospedar apenas a versão estática, envie todo o conteúdo de `site-html/` para a raiz pública do serviço de hospedagem; mantenha a subpasta `assets/` ao lado de `index.html`. Consulte `site-html/README.md` para instruções.


## Identidade visual

O cabeçalho, o rodapé e os favicons usam agora o Cruzeiro do Sul representado somente pelas cinco estrelas, sem aro circular, retícula ou enfeites. O título do site também foi padronizado sem glifos decorativos.

## Revisão de interface e favicon (19/10/2026)

- Atualizado o favicon para o Cruzeiro do Sul branco sobre fundo azul-ciano, com URL versionada para reduzir o risco de cache antigo. O SVG está em `public/favicon.svg` e `site-html/favicon.svg`; há também um ICO de fallback.
- O tema claro/escuro continua disponível no site estático e na aplicação React/TanStack, salvando a escolha em `localStorage` quando permitido e respeitando a preferência de tema do sistema na primeira visita.
- Os resultados, limites e métodos da revisão estão em `docs/LINKS-AUDIT.md` e `docs/REVISAO-RESPONSIVIDADE.md`.
- Para publicar o site estático, envie todo o conteúdo de `site-html/`. Para reconstruir a aplicação, instale as dependências e execute `npm run build`.


## Revisão final de interface e navegação (19/10/2026)

- A versão HTML estática foi testada no Chromium headless em 15 larguras (320–1440 px), nos temas claro e escuro: 30 combinações, sem transbordamento horizontal e sem erros de carregamento de imagem nos testes.
- Em telas de até 430 px, os cartões de atividades organizam imagem e descrição verticalmente para melhorar leitura e evitar desalinhamento visual.
- Melhorado o contraste dos rótulos pequenos e adicionado link de teclado “Pular para o conteúdo principal”.
- Incluídas a matriz `docs/chromium-responsive-matrix.csv`, a auditoria `docs/LINKS-AUDIT.md` e o resumo estruturado `docs/static-audit.json`. A auditoria cobre os links do HTML estático e os principais destinos/imagens da rota React/TanStack.
- Limitação documentada: o Chromium foi executado com o HTML estático carregado via `document.set_content()` porque o ambiente bloqueia navegação por URL. O app React/TanStack teve seus TSX verificados sintaticamente, mas não teve build de produção nesta sessão por falta de dependências instaladas.

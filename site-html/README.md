# Site HTML estático — Desvendando o Céu Austral

Esta pasta é uma versão estática, independente e responsiva do site institucional. Não precisa de React, npm, servidor Node ou bibliotecas externas para funcionar.

## Como visualizar
- Abra `index.html` no navegador.
- As fotografias são locais e estão em `assets/`, portanto o site não depende de imagens remotas para a galeria e o conteúdo principal.

## Como publicar
Para hospedagem estática (por exemplo GitHub Pages, Netlify ou servidor institucional), envie **todo o conteúdo desta pasta** — `index.html`, `favicon.svg`, `favicon.ico`, `README.md` e `assets/` — para a pasta pública do projeto. Não envie somente o arquivo HTML, pois as fotografias são arquivos separados.

## Recursos
- Layout mobile-first, menu móvel e botões com área adequada para toque.
- Galeria com visualização ampliada, fechamento por toque fora da imagem ou tecla Escape e bloqueio da rolagem de fundo.
- Imagens WebP do acervo local do projeto, carregadas sob demanda quando apropriado.
- Linha do tempo, descrição das atividades, seção do OASI, parcerias, fontes e contatos oficiais.
- A página distingue registros documentados de inferências e não presume que toda cooperação configure convênio formal permanente.

## Fontes
Os links institucionais e históricos estão listados na seção “Consulte as fontes e os registros” da página.

## Identidade visual
O ícone e a marca usam somente as cinco estrelas do Cruzeiro do Sul, sem círculo ao redor.
- Alternância acessível entre tema claro e escuro, com preferência salva no navegador.
- Favicon Cruzeiro do Sul atualizado com fallback ICO e URL versionada para diminuir problemas de cache.


## Revisão de responsividade (19/10/2026)
- No Chromium headless, foram verificados 15 tamanhos de tela entre 320 px e 1440 px nos temas claro e escuro. A matriz está em `../docs/chromium-responsive-matrix.csv`.
- Em até 430 px, cada cartão de atividade coloca a foto acima da descrição, com proporção de imagem consistente.
- Os links internos e imagens locais foram auditados; ver `../docs/LINKS-AUDIT.md`.
- O teste de Chromium carregou o HTML através de conteúdo local (o ambiente bloqueia navegação por URL); veja `../docs/REVISAO-RESPONSIVIDADE.md` para o método e os limites.

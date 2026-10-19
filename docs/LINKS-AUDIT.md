# Auditoria de links e hiperlinks

**Data:** 19/10/2026  
**Arquivos auditados:** `site-html/index.html` e os atributos JSX da rota `src/routes/index.tsx`.

## Integridade interna

- **53 links** `<a>` no documento; nenhum está sem `href` ou com `href` vazio.
- **12 links de fragmento interno**; todos apontam para IDs existentes.
- **17 IDs**; nenhum ID duplicado.
- **39 referências locais de imagem** em 18 arquivos distintos; não há arquivos ausentes nem imagens inválidas.
- Todos os links externos que abrem em nova aba têm `rel="noopener noreferrer"` nas versões estática e React/TanStack. Na rota React foram verificados 8 nós JSX de âncora com `target="_blank"`, todos com os dois tokens de segurança; o link do WhatsApp é gerado por uma lista de dois contatos.
- Os números de telefone são exibidos como texto; não há links `tel:`. Os dois links de WhatsApp permanecem ativos.
- A versão estática contém 40 ocorrências HTTP(S), distribuídas em 22 URLs externas únicas. A rota React contém 20 constantes nomeadas para destinos externos e uma expressão de WhatsApp usada pelos dois contatos; os destinos correspondem ao mesmo conjunto de 22 URLs.

## Verificação de destinos externos

Abertura foi consultada com a ferramenta de leitura web em 19/10/2026. “Abertura confirmada” quer dizer que a ferramenta conseguiu ler a página, não é uma garantia permanente do destino. “Não confirmado” não significa que esteja quebrado: bloqueios anti-bot, autenticação, redirecionamentos, links de compartilhamento ou limitações do verificador podem impedir a leitura.

### Abertura confirmada (12 URLs)

- Página principal histórica do projeto (Wix): https://astronomiaufrpe.wixsite.com/desvendando
- Relato da IV Mostra de Astronomia (2014): https://desvendandoufrpe.blogspot.com/2014/05/o-que-aconteceu-iv-mostra-de-astronomia.html
- Atividade em Serra Talhada (2014): https://desvendandoufrpe.blogspot.com/2014/09/desvendando-o-ceu-austral-participa-de.html
- OASI na Semana Nacional de Ciência e Tecnologia de 2021 (Observatório Nacional): https://www.gov.br/observatorio/pt-br/assuntos/areas-de-atuacao/astronomia-e-astrofisica/oasi/impacton/noticias/oasi-recebe-visitantes-na-semana-nacional-de-ciencia-e-tecnologia-2021
- OASI de portas abertas na SNCT 2022 (Observatório Nacional): https://www.gov.br/observatorio/pt-br/assuntos/noticias/observatorio-astronomico-do-sertao-de-itaparica-oasi-on-de-portas-abertas-na-snct-2022
- Notícia da inauguração do Museu de Ciências (UFRPE): https://www.ufrpe.br/es/not%C3%ADcias/ufrpe-inaugura-museu-de-ci%C3%AAncias-desvendando-o-c%C3%A9u-austral/
- Notícia da Semana POP (UFRPE): https://ufrpe.br/not%C3%ADcias/semana-de-populariza%C3%A7%C3%A3o-da-ci%C3%AAncia-no-semi%C3%A1rido-chega-%C3%A0-d%C3%A9cima-edi%C3%A7%C3%A3o/
- Página institucional do OASI (Observatório Nacional): https://www.gov.br/observatorio/pt-br/assuntos/areas-de-atuacao/astronomia-e-astrofisica/oasi
- Registro de visita técnica ao OASI (Observatório Nacional): https://www.gov.br/observatorio/pt-br/assuntos/areas-de-atuacao/astronomia-e-astrofisica/oasi/impacton/noticias/visita-tecnica-ao-oasi-2013-27-de-maio-de-2022/
- Clipping da Secti de 2020: https://sectipe.blogspot.com/2020/10/clipmail-secti-08102020.html
- Referência sobre o meteorito Serra do Magé: https://www.museuitinerante.com/serra-do-mag%C3%A9
- Atividade no IFPE de Belo Jardim (2014): https://desvendandoufrpe.blogspot.com/2014/09/desvendando-o-ceu-austral-participa-de_16.html

### Não confirmado pela ferramenta (10 URLs)

- Registro da III Semana da Popularização da Ciência no Semiárido (Wix): https://astronomiaufrpe.wixsite.com/desvendando/single-post/2017/05/29/iii-semana-da-populariza%C3%A7%C3%A3o-da-ci%C3%AAncia-no-semi%C3%A1rido-monteiro
- Programação da Torre Malakoff (Secretaria de Cultura de PE): https://www.cultura.pe.gov.br/canal/espacosculturais/programacao-no-observatorio-da-torre-malakoff-convida-interessados-em-astronomia/
- Ação de popularização da astronomia na ALEPE: https://www.alepe.pe.gov.br/2023/09/20/comissao-de-ciencia-e-tecnologia-realiza-acao-para-popularizar-a-astronomia/
- Registro no SIGAA/UFRPE: https://sigs.ufrpe.br/sigaa/public/programa/noticias_desc.jsf?id=400&lc=pt_BR&noticia=42351205
- Página atribuída à Prefeitura de Alagoinha (Globgov): https://www.globgov.com/BR/Alagoinha/542516145768365/Prefeitura-Municipal-de-Alagoinha-PE
- Pasta compartilhada de fotografias no Google Drive: https://drive.google.com/drive/folders/1LGv4pSrye9NgpvY-9K5fTtsJt1vxiGj4?usp=sharing
- Perfil do projeto no Instagram: https://www.instagram.com/desvendandoceuaustral?obrf=am80NDhvcHRkZ2U1
- Publicação da UFRPE no Facebook: https://www.facebook.com/UFRPEoficial/posts/samyr-pessoa-da-silva-esse-foi-o-nome-escolhido-por-71-dos-estudantes-da-ufrpe-p/3466004156789113/
- WhatsApp do contato institucional 1: https://wa.me/5581988094943
- WhatsApp do contato institucional 2: https://wa.me/5581986545345

## Recomendação

Os links internos e caminhos de recursos locais passaram a validação estrutural. Antes de divulgação pública, abra manualmente os dez destinos não confirmados em um navegador comum, especialmente o Drive (permissões da pasta), Instagram/Facebook e WhatsApp. Não removi nenhum link somente porque a ferramenta automatizada não conseguiu consultá-lo.

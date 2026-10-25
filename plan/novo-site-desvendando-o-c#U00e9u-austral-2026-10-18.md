# Atualização do site — Desvendando o Céu Austral

Site de uma página longa, responsivo, em português, com identidade visual de céu austral: fundo azul-noite, estrelas sutis, detalhes em azul celeste/dourado, títulos serifados e texto sem serifa.

## O que já está implementado

- Título e favicon com o Cruzeiro do Sul.
- Abertura com proposta de popularização da ciência e acesso rápido a atividades e contatos.
- Seção de missão, extensão universitária, formação de monitores e memória da contribuição de Samyr Pessoa, com links para registros públicos.
- Linha do tempo com eventos documentados de 2015 a outubro de 2026, cada marco com um link de referência.
- Doze cartões de atividades, cada um com foto, ícone e descrição: observação noturna e solar, reconhecimento do céu, foguetes, teatro científico, histórias, palestras, oficinas, Museu, astrofotografia, visitas técnicas e ações itinerantes.
- Galeria em mosaico com ampliação de imagens.
- Seção específica para o OASI em Itacuruba: pesquisa de pequenos corpos do Sistema Solar, telescópio robótico, visitas técnicas, formação científica e Semana POP.
- Seção de parcerias, cooperações e convênios, com atenção a OASI/Observatório Nacional, INSA, Espaço Ciência/SECTI-PE, escolas e prefeituras.
- Contexto histórico e educativo dos meteoritos de Santa Filomena e Serra do Magé/Alagoinha.
- Bloco de fontes e registros institucionais, além de WhatsApp, Instagram, e-mail e acesso à pasta de fotos.
- Menu responsivo para celular.

## Fotografias

O site mantém as 16 imagens que já estavam no ZIP original (`src/assets/drive/`) e acrescenta a imagem de equipe enviada na conversa (`src/assets/oasi-equipe.jpg`). A pasta online do Drive não pôde ser listada diretamente neste ambiente; o ZIP inclui um link para ela, para consulta e futuras atualizações.

## Cuidado editorial

O site distingue registros de atividades e cooperações documentadas de convênios jurídicos específicos: não presume que toda iniciativa seja regida por um instrumento formal permanente. Os textos da linha do tempo e da seção de fontes apontam para registros públicos quando disponíveis.

## Desenvolvimento local

O projeto usa Vite, React, TypeScript, TanStack Start, Tailwind CSS e lucide-react.

```sh
npm install
npm run dev
npm run build
```

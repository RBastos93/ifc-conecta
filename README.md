# IFC Conecta — Guia para novos estudantes

Portal escolar voltado para ajudar estudantes recém-ingressados (calouros) a se
localizarem no campus. O site reúne, em um só lugar, informações sobre os
cursos, os eventos e os primeiros passos do dia a dia escolar.

> Este é um projeto acadêmico da disciplina de Desenvolvimento Web. Ele **não
> representa oficialmente** o Instituto Federal Catarinense.

## Problema identificado

Todo início de semestre, novos estudantes chegam cheios de dúvidas: onde fica
cada setor, como funcionam matrícula, biblioteca e refeitório, quais eventos
existem e para quem pedir ajuda. Essas informações costumam estar espalhadas em
vários lugares, o que torna a adaptação mais confusa do que precisa ser.

O **IFC Conecta** resolve isso organizando tudo em páginas simples, com uma
navegação fácil, para que qualquer calouro consiga se virar sozinho desde o
primeiro dia.

## Público-alvo

- Estudantes recém-ingressados (calouros);
- Famílias que querem conhecer melhor o campus;
- Visitantes interessados nos cursos e eventos.

## Identidade visual

A paleta se chama **"Azul Acadêmico & Âmbar"**. Ela foi montada seguindo alguns
fundamentos de design, e não só por gosto pessoal:

- **Harmonia de cores:** o azul (cor principal) e o âmbar (cor de ação) são
  cores complementares — ficam em lados opostos do círculo cromático, então
  criam um contraste forte e agradável;
- **Psicologia das cores:** o azul passa confiança e seriedade (combina com
  ambiente de estudo); o ciano traz frescor e ideia de tecnologia; o âmbar é
  quente e otimista, por isso é usado para chamar a atenção nos botões;
- **Regra 60-30-10:** cerca de 60% da tela é neutra (fundos claros), 30% é azul
  (cabeçalho, estrutura) e 10% é âmbar (ações). Isso evita poluição visual;
- **Escala de tokens:** cada cor tem vários tons (do 50 ao 900), como nos
  _design systems_ profissionais. Assim fica fácil manter a consistência.

Paleta principal:

| Cor                           | Papel         | Exemplo de uso                  |
| ----------------------------- | ------------- | ------------------------------- |
| Azul-marinho (`#1e3a8a`)      | Cor de marca  | Cabeçalho, títulos, logo        |
| Azul (`#3b6fe0`)              | Apoio         | Capas de cards, foco dos campos |
| Ciano (`#06b6d4`)             | Secundária    | Detalhes, sobretítulos          |
| Âmbar (`#f59e0b`)             | Ação / acento | Botões, destaques, passos       |
| Slate (`#0f172a` → `#f8fafc`) | Neutros       | Texto e fundos                  |

Outras decisões de design:

- **Tipografia:** **Poppins** nos títulos e **Inter** no texto, com tamanhos em
  escala modular (cada tamanho segue uma proporção, não valores aleatórios);
- **Espaçamento em ritmo:** margens e espaços seguem uma mesma escala, deixando
  o visual organizado;
- **Acessibilidade:** contraste pensado para leitura, foco visível no teclado,
  link para pular ao conteúdo e respeito a `prefers-reduced-motion`.

Todas essas cores e medidas estão como variáveis no arquivo
`css/base/tokens.css`, por isso a identidade visual fica igual em todas as
páginas.

### Organização dos arquivos por aba

Cada página (aba do portal) fica na sua própria pasta, com o HTML e o CSS
daquela página juntos. O que é comum a todas as páginas fica em `css/base/`:

- **`css/base/`** — o que é comum a todas as páginas (variáveis em
  `tokens.css`, estrutura em `layout.css` e componentes em `componentes.css`);
- **`inicio/`, `cursos/`, `eventos/`, `guia/`, `contato/`** — cada aba com seu
  próprio arquivo de estilos (e o HTML, exceto o início, que usa o `index.html`
  da raiz por ser a página principal do site).

Cada página carrega, nesta ordem: `reset.css`, os três arquivos de `base/` e,
por último, o CSS da sua própria pasta. Assim o código fica mais fácil de achar
e de manter.

## Autoria

Projeto desenvolvido por **Rodrigo Alysson** durante as atividades de
Desenvolvimento Web.

## Páginas desenvolvidas

| Página          | Arquivo                | Descrição                                     |
| --------------- | ---------------------- | --------------------------------------------- |
| Início          | `index.html`           | Boas-vindas e principais destaques do portal  |
| Cursos          | `cursos/cursos.html`   | Resumo dos cursos técnicos oferecidos         |
| Eventos         | `eventos/eventos.html` | Lista dos próximos eventos do campus          |
| Guia do calouro | `guia/guia.html`       | Passo a passo dos primeiros dias de aula      |
| Contato         | `contato/contato.html` | Formulário de contato e telefones dos setores |

Todas as páginas estão conectadas por um menu de navegação presente no cabeçalho.

## Mapa de páginas

```text
Início (index.html)
├── Cursos (cursos/cursos.html)
├── Eventos (eventos/eventos.html)
├── Guia do calouro (guia/guia.html)
└── Contato (contato/contato.html)
```

Qualquer página pode ser acessada a partir do menu, então a navegação não é
apenas em uma direção — o menu aparece igual em todas as telas.

## Wireframe (estrutura visual)

O layout segue a mesma estrutura em todas as páginas:

```text
+-------------------------------------------------+
| CABEÇALHO (logo + nome do portal)               |
+-------------------------------------------------+
| MENU (Início | Cursos | Eventos | Guia | Contato)|
+-------------------------------------------------+
|                                                 |
|  CONTEÚDO PRINCIPAL                              |
|  - título da seção                              |
|  - texto de apoio                               |
|  - cards / listas / formulário                  |
|  - bloco lateral (dica)                         |
|                                                 |
+-------------------------------------------------+
| RODAPÉ (sobre + navegação + créditos)           |
+-------------------------------------------------+
```

## Tecnologias utilizadas

- HTML5 (com elementos semânticos);
- CSS3 (Flexbox, variáveis, gradientes e media queries);
- Google Fonts (fontes Poppins e Inter);
- ícones e ilustrações em SVG feitos no projeto;
- Visual Studio Code;
- Git e GitHub.

## Como executar o projeto

1. Baixe ou clone o repositório;
2. abra a pasta do projeto no Visual Studio Code;
3. abra o arquivo `index.html` com a extensão **Live Server** ou direto no
   navegador;
4. navegue entre as páginas usando o menu do topo.

## Estrutura dos arquivos

```text
ifc-conecta/
├── index.html
├── cursos.html
├── eventos.html
├── guia.html
├── contato.html
├── css/
│   ├── reset.css              (reset básico do navegador)
│   └── base/                  (estilos compartilhados por todas as páginas)
│       ├── tokens.css         (variáveis: cores, fontes, espaços)
│       ├── layout.css         (cabeçalho, menu, seções, rodapé)
│       └── componentes.css    (botões, cards, etiquetas, dica, listas)
├── inicio/
│   └── inicio.css             (destaque e faixa de números da página inicial)
├── cursos/
│   ├── cursos.html
│   └── cursos.css
├── eventos/
│   ├── eventos.html
│   └── eventos.css
├── guia/
│   ├── guia.html
│   └── guia.css               (passos em linha do tempo)
├── contato/
│   ├── contato.html
│   └── contato.css            (formulário)
├── js/            (será usada na Versão 2)
├── images/
│   ├── logo.svg       (logotipo do portal)
│   └── hero.svg       (ilustração da página inicial)
└── README.md

Os ícones das seções e dos cards são SVG escritos direto no HTML (inline),
para ficarem nítidos e mudarem de cor pelo CSS.
```

## Link da aplicação publicada

> A publicar via GitHub Pages. Substituir pelo endereço real após a publicação:
> `https://SEU-USUARIO.github.io/ifc-conecta/`

## Capturas de tela

> Adicionar aqui as imagens do portal rodando no navegador (desktop e celular)
> antes da entrega.

## Funcionalidades planejadas para a Versão 2

Na Versão 1 o portal usa apenas HTML e CSS. Abaixo estão as interações que
pretendo desenvolver com JavaScript na Versão 2.

| Funcionalidade          | Página         | Elementos envolvidos                     | Ação do usuário                                     | Comportamento esperado                                                    | Importância                                                   |
| ----------------------- | -------------- | ---------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Menu para celular       | Todas          | Botão de menu e lista `.menu__lista`     | Tocar no botão do menu                              | Mostrar ou esconder os links de navegação                                 | Deixa a navegação mais confortável em telas pequenas          |
| Filtro de eventos       | `eventos.html` | Botões de categoria e os cards de evento | Clicar em uma categoria (esporte, cultura, ciência) | Exibir somente os eventos da categoria escolhida                          | Ajuda o estudante a achar rápido o tipo de evento que procura |
| Validação do formulário | `contato.html` | Campos do formulário e área de mensagem  | Enviar o formulário                                 | Conferir se os campos estão preenchidos e mostrar avisos claros           | Evita envios vazios e orienta o usuário                       |
| Tema claro e escuro     | Todas          | Botão de tema e o `body`                 | Clicar no botão de tema                             | Trocar as cores entre claro e escuro e salvar a escolha no `localStorage` | Melhora o conforto de leitura e lembra a preferência          |

### Detalhamento das funcionalidades

**1. Menu para celular**

- Página: todas as páginas do portal;
- Elementos: um botão novo no cabeçalho e a lista `.menu__lista`;
- Ação do usuário: tocar no botão quando estiver no celular;
- Comportamento esperado: a lista de links aparece ou some ao tocar;
- Importância: em telas pequenas o menu ocupa muito espaço, então escondê-lo
  melhora a experiência.

**2. Filtro de eventos**

- Página: `eventos.html`;
- Elementos: botões de categoria e os `article.card` dos eventos;
- Ação do usuário: clicar em uma categoria;
- Comportamento esperado: apenas os eventos daquela categoria continuam
  visíveis;
- Importância: facilita encontrar o evento certo sem precisar ler todos.

**3. Validação do formulário de contato**

- Página: `contato.html`;
- Elementos: os campos `nome`, `email`, `assunto` e `mensagem`;
- Ação do usuário: clicar em "Enviar mensagem";
- Comportamento esperado: se algum campo estiver vazio ou o e-mail inválido,
  aparece um aviso explicando o que corrigir;
- Importância: garante que a mensagem chegue completa e orienta quem está
  enviando.

**4. Tema claro e escuro**

- Página: todas;
- Elementos: um botão de tema no cabeçalho e o `body`;
- Ação do usuário: clicar no botão de tema;
- Comportamento esperado: as cores do portal mudam e a escolha fica salva com
  `localStorage` para a próxima visita;
- Importância: dá mais conforto de leitura e mostra atenção à experiência do
  usuário.

> Este planejamento pode ser ajustado durante o desenvolvimento. Qualquer
> mudança será atualizada aqui no `README.md`.

## Referências utilizadas

- [MDN Web Docs](https://developer.mozilla.org/pt-BR/) — documentação de HTML e
  CSS;
- [Google Fonts](https://fonts.google.com/) — fontes Poppins e Inter;
- Materiais da disciplina de Desenvolvimento Web;
- Ícones no estilo de linha inspirados em bibliotecas livres, redesenhados em
  SVG no próprio projeto;
- Ilustrações criadas no próprio projeto em formato SVG.

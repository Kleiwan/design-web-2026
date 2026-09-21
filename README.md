# Tarefa 33: Página pessoal com DaisyUI

Página pessoal de **Kleiwan Paulo Justino Pinheiro Ludugero**, estudante de Informática para Internet (IFRN), construída com componentes DaisyUI e complementada com Tailwind CSS. Tudo está em um único `index.html`, carregando DaisyUI e Tailwind por CDN, sem JavaScript próprio.

## 1. Componentes DaisyUI utilizados

| Componente | Onde aparece |
|---|---|
| `navbar` (`navbar-start`, `navbar-center`, `navbar-end`) | Barra fixa no topo, com logo, links das seções, toggle de tema e botão de contato |
| `menu menu-horizontal` | Links de navegação dentro da navbar (visíveis a partir de telas médias) |
| `hero` (`hero-content`) | Bloco de abertura com nome, descrição e botões |
| `avatar placeholder` | Círculo com as iniciais "KL" no hero |
| `btn` (`btn-primary`, `btn-outline btn-secondary`, `btn-ghost`, `btn-sm`) | Hero, navbar, cards e formulário |
| `badge` (`badge-primary`, `badge-secondary`, `badge-accent`, `badge-outline`, `badge-lg`) | Habilidades e interesses na seção "Sobre mim" e tecnologias dentro dos cards |
| `card` (`card-body`, `card-title`, `card-actions`) | Três cards de projetos e o card do formulário |
| `alert alert-info` | Seção de contato, com e-mail e GitHub |
| `input`, `textarea`, `form-control`, `label` | Formulário de contato (nome, e-mail e mensagem) |
| `toggle theme-controller` | Navbar: alterna entre `garden` e `forest` sem JavaScript |
| `footer footer-center` | Rodapé |

## 2. Justificativa de escolha: navbar + hero

Usei **os dois**, cada um com uma função:

- **navbar**: navegação fixa e identificação constante. Como a página tem quatro seções, o visitante pode pular para qualquer uma sem rolar tudo. Também abriga o botão de ação ("Fale comigo") e o seletor de tema.
- **hero**: a primeira impressão. Ele apresenta meu nome completo e uma frase sobre quem sou, com dois botões de ação. Só a navbar seria pequena demais para isso, e só o hero deixaria a página sem navegação.

## 3. Pontos de ajuste com Tailwind

1. **Grid dos cards de projetos** (`grid gap-6 md:grid-cols-2 lg:grid-cols-3`). O `card` do DaisyUI define a aparência de cada card, mas não como eles se organizam na tela. Usei o grid do Tailwind para ter 1 coluna no celular, 2 no tablet e 3 no desktop. Também usei `h-full` e `mt-auto` para os botões ficarem alinhados no fim, mesmo com descrições de tamanhos diferentes.
2. **Hero e badges**: o `hero` traz a estrutura, mas a altura mínima usei `min-h-[70vh]` (Tailwind) para ele ocupar boa parte da tela. Nas badges, `flex flex-wrap gap-2` faz elas quebrarem de linha no mobile sem estourar a largura, algo que a classe `badge` sozinha não resolve.

Também usei `sticky top-0 z-10` na navbar, `scroll-mt-16` nas seções (para o título não ficar escondido atrás da navbar ao clicar nos links) e `max-w-prose` nos textos para limitar a largura das linhas.

## 4. Reflexão sobre temas

Testei dois temas: **garden** (claro, verdes suaves) e **forest** (escuro, verdes profundos). A troca é feita pelo toggle na navbar, que altera o `data-theme` via `theme-controller`, e todo o resto se adapta porque usei só cores semânticas do DaisyUI (`bg-base-100`, `bg-base-200`, `text-base-content`, `btn-primary`, etc.), sem nenhuma cor fixa.

O tema **garden** ficou mais coerente com o conteúdo. Como falo de jardinagem e pássaros, o fundo claro e o verde natural combinam com o assunto e deixam a leitura confortável. O **forest** também ficou legível e com bom contraste, e funciona melhor à noite, mas o clima fica mais sério do que o restante da página, que é leve.

> *Nota do autor: ajustar esta seção com a minha própria impressão depois de testar os dois temas no navegador.*

## 5. Responsividade

- Celular: cards em 1 coluna, links da navbar ocultos (ficam o logo, o toggle e o botão de contato) e botões do hero que quebram linha.
- Tablet: cards em 2 colunas.
- Desktop: cards em 3 colunas e links de navegação visíveis; formulário e alerta lado a lado na seção de contato.

## 6. Como executar

Abra o `index.html` no navegador. É necessário estar conectado à internet, pois DaisyUI e Tailwind são carregados por CDN.

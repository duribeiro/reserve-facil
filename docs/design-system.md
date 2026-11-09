# Design system ReserveFácil

Aplicado ao restaurante fictício Ulivo. Fica no Figma, numa única página, **Design System**, com 7 seções lado a lado (Capa, Cores, Tipografia, Espaço e sombras, Ícones, Componentes, Assets): [abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=22-2). Decisão: [7](../pipeline/decisions/interface/0007-design-system-com-variaveis-e-dois-modos.md). Marca e referências: [padrao-visual.md](../referencias/padrao-visual.md).

## Regra de ouro

Nenhuma tela usa cor, fonte, espaçamento ou raio solto. Tudo vem de uma variável ou de um estilo desta página, e todo elemento repetido é uma instância de componente. Trocar o valor na variável muda o sistema inteiro.

## Variáveis (111)

| Coleção | O que tem | Modos |
|---|---|---|
| Primitives | 43 cores brutas: verde, terracota, creme, carvão, cinza e cores de aviso. Não se usam nas telas | Valor |
| Color | 44 cores semânticas: `bg/`, `text/`, `border/`, `feedback/`. É o que as telas usam. `bg/brand` (verde) é a cor da ação principal; `bg/inverse` (carvão) e `text/on-inverse` servem a fundos escuros; `bg/accent` (terracota) é só destaque; `bg/glass`, `bg/glass-dark` e `border/glass` são os vidros translúcidos | **Ulivo** (alta fidelidade) e **Wireframe** (cinzas) |
| Spacing | 12 passos em pixels: `space/2` até `space/64` | Valor |
| Radius | 6 raios: `radius/none` até `radius/xl` e `radius/full` | Valor |
| Size | 6 tamanhos: altura de controle (`size/control/sm`, `md`, `lg`) e ícones (`size/icon/sm`, `md`, `lg`) | Valor |

Cada variável tem escopo definido (só aparece onde faz sentido) e nome para código no formato `var(--color-bg-page)`.

**Trocar de restaurante:** crie um modo novo na coleção Color e aponte cada cor semântica para a paleta do restaurante. O logo é o único componente com cores fixas e deve ser substituído.

## Estilos de texto (14)

| Grupo | Estilos | Fonte |
|---|---|---|
| Título | Display 48, H1 36, H2 28, H3 22 | Cormorant Garamond SemiBold |
| Texto | Corpo G 18, Corpo 16, Corpo P 14, Legenda 12 | DM Sans Regular |
| Rótulo | Rótulo 14, Rótulo P 12, Botão 16, Botão P 14, Overline 12 | DM Sans Medium |
| Número | Estatística 28 | DM Sans Bold |

Só duas fontes no arquivo: Cormorant Garamond e DM Sans.

## Efeitos (5)

Sombra sm, md e lg, Foco anel (contorno terracota usado em campo e botão com foco) e Vidro desfoque (fundo desfocado com sombra suave, para cartões e botões sobre fotos).

## Ícones (47)

Biblioteca [Lucide](https://lucide.dev) (licença ISC), contorno de 2 px em grade de 24. Cada ícone é um componente `Icone/nome` e a cor vem de variável de texto. Tamanhos 16, 20 ou 24. O menu inferior já usa a propriedade Ícone (troca de instância).

## Assets

Fotos e mockups da marca Ulivo, com regras em [assets.md](assets.md).

## Componentes (16 famílias)

| Componente | Variantes e estados | Propriedades editáveis |
|---|---|---|
| Botão | Estilo (Primary verde, Secondary contorno, Text, Danger, Inverse creme para fundo escuro) x Estado (Default, Hover, Pressed, Focus, Disabled), 48 px | Rótulo |
| Botão pequeno | Os mesmos 25, 36 px, para tabelas | Rótulo |
| Chip | Selected (On, Off) x Estado (Default, Hover, Disabled) | Rótulo |
| Status | Tom: Neutro, Sucesso, Alerta, Perigo, Info | Rótulo |
| Campo | Estado: Default, Focus, Filled, Error, Disabled | Rótulo, Valor, Ajuda |
| Alerta | Tom: Info, Sucesso, Alerta, Perigo | Título, Mensagem |
| Cartão | Estilo: Contorno, Suave, Vidro (escuro e translúcido, sobre fotos) | Sobretítulo, Título, Detalhe |
| Número | um | Rótulo, Valor |
| Mensagem WhatsApp | um | Mensagem |
| Barra superior | Voltar: Sim, Não | Título |
| Menu inferior | Aba (Ativa: Sim, Não, com ícone trocável), menu pronto e versão flutuante de vidro | Rótulo, Ícone |
| Item do menu lateral | Estado: Default, Hover, Ativo | Rótulo |
| Célula de tabela | Tipo: Cabeçalho, Corpo | Texto |
| Diálogo | um, com botão de perigo e botão secundário | Título, Mensagem |
| Imagem | um | Rótulo |
| Logo | Fundo: Verde, Creme, Carvão | nenhuma |

## Como usar

- Monte telas só com instâncias. Se faltar uma peça, crie o componente aqui antes de usá-la.
- Verde escuro e carvão dominam a tela, creme é a superfície clara. Terracota é só destaque, cerca de 5% da tela: símbolo, link, anel de foco e detalhes pequenos. Nunca em botão principal ([decisão 8](../pipeline/decisions/interface/0008-laranja-so-destaque-botao-principal-verde.md)).
- Uma ação principal por tela, em botão verde. Sobre fundo escuro, use o botão Inverse.
- Botão de perigo só para desfazer algo (cancelar reserva).
- Campo mostra o texto de ajuda apenas no erro ou quando preenchido.
- Para ver o wireframe com as mesmas peças, troque o modo da moldura para Wireframe.

## Fora desta versão

Caixa de seleção, interruptor, calendário e seletor de horário completo. Entram quando uma tela precisar.

## Estilo da alta fidelidade

Inspirado no app da referência Bean & Bloom: muitas fotos e banners, cartões e botões de vidro translúcido sobre as fotos, folhas creme com cantos arredondados no topo, menu inferior flutuante. Cliente em celular, atendente em tablet e gerente em computador, com banner de foto no topo das telas da equipe. As telas ficam na página **Alta fidelidade** do Figma.

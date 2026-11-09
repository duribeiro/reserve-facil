# Design system ReserveFácil

Aplicado ao restaurante fictício Ulivo. Fica no Figma, numa única página, **Design System**, com 7 seções lado a lado (Capa, Cores, Tipografia, Espaço e sombras, Ícones, Componentes, Assets): [abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=22-2). Decisão: [7](../pipeline/decisions/interface/0007-design-system-com-variaveis-e-dois-modos.md). Marca e referências: [padrao-visual.md](../referencias/padrao-visual.md).

## Regra de ouro

Nenhuma tela usa cor, fonte, espaçamento ou raio solto. Tudo vem de uma variável ou de um estilo desta página, e todo elemento repetido é uma instância de componente. Trocar o valor na variável muda o sistema inteiro.

## Variáveis (131)

| Coleção | O que tem | Modos |
|---|---|---|
| Primitives | 61 cores brutas: verde, terracota, creme, carvão, cinza e cores de aviso. Não se usam nas telas | Valor |
| Color | 46 cores semânticas: `bg/`, `text/`, `border/`, `feedback/`. É o que as telas usam. `bg/brand` (verde) é a cor da ação principal; `bg/inverse` (carvão) e `text/on-inverse` servem a fundos escuros; `bg/accent` (terracota) é só destaque; `bg/glass`, `bg/glass-dark` e `border/glass` são os vidros translúcidos | **Ulivo** (tema escuro da alta fidelidade) e **Wireframe** (cinzas) |
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

## Tema escuro

A alta fidelidade é escura, na proporção da marca ([decisão 11](../pipeline/decisions/interface/0011-tema-escuro-na-alta-fidelidade.md)):

| Camada | Cor | Quanto da tela |
|---|---|---|
| Fundo | carvão `#0B0A09` | cerca de 50% |
| Cards e painéis | verde escuro em degradê, de `#1B2A23` a `#0E1713` | cerca de 30% |
| Texto e botão principal | creme `#F7F2EA` | cerca de 15% |
| Destaque | terracota `#D9622B` | cerca de 5% |

- **Card nunca é cor chapada:** usa o degradê diagonal de verde escuro, com borda fina.
- **Botão principal é creme com texto carvão.** O verde não teria contraste sobre o fundo escuro.
- **Texto sobre foto** usa `text/on-photo` e `text/on-photo-muted`, que são claros nos dois modos.
- **Foto que encontra o fundo** recebe um degradê para o carvão, nunca corte seco.

## Efeitos (5)

Sombra sm, md e lg, Foco anel (contorno terracota usado em campo e botão com foco) e Vidro desfoque (fundo desfocado com sombra suave, para cartões e botões sobre fotos).

## Ícones (48)

Biblioteca [Lucide](https://lucide.dev) (licença ISC), contorno de 2 px em grade de 24. Cada ícone é um componente `Icone/nome` e a cor vem de variável de texto. Tamanhos 16, 20 ou 24. O menu inferior e os botões usam a propriedade Ícone (troca de instância). O `Icone/emblema-ulivo` é o ramo de oliveira da marca e substitui qualquer ícone genérico quando o assunto é a marca.

## Assets

Fotos e mockups da marca Ulivo, com regras em [assets.md](assets.md).

## Componentes (24 famílias)

O gráfico de barras foi retirado: use o gráfico de área.

| Componente | Variantes e estados | Propriedades editáveis |
|---|---|---|
| Botão | Estilo (Primary verde, Secondary contorno, Text, Danger, Inverse creme para fundo escuro) x Estado (Default, Hover, Pressed, Focus, Disabled), 48 px | Rótulo, Tem ícone, Ícone |
| Botão pequeno | Os mesmos 25, 36 px, para tabelas | Rótulo, Tem ícone, Ícone |
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
| Ação rápida | um | Rótulo, Ícone |
| Cabeçalho de seção | um | Título, Link |
| Card de conteúdo | um, horizontal com foto, etiqueta e botão | Etiqueta, Título, Descrição |
| Card vertical | um, foto no topo | Título, Detalhe, Ícone |
| Banner | um, foto escurecida com botão creme | Sobretítulo, Título, Descrição |
| Item de lista | um, foto + status + seta | Título, Detalhe |
| Gráfico de área | um, duas curvas com degradê | Título, Variação, Comparação |
| Número com variação | um, ícone + valor + comparação | Valor, Rótulo, Variação, Ícone |

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

Inspirado no app da referência Bean & Bloom e no painel da referência de dashboard. As telas ficam na página **Alta fidelidade** do Figma. Decisão: [10](../pipeline/decisions/interface/0010-composicao-rica-nas-telas.md).

**Cliente, no celular**
- Fundo carvão. Cards em degradê de verde escuro.
- A foto do topo **funde com o fundo creme** por um degradê, sem borda nem corte seco. É o que dá o ar de página de venda.
- Título em serifa grande sobre a área já clara, com uma frase curta embaixo.
- Cartões e botões de vidro translúcido quando ficam sobre a foto.
- Conteúdo em seções, cada uma com cabeçalho e atalho "Ver tudo": atalhos com ícone, grade de ambientes, card de prato e banner de evento.
- Menu flutuante com 4 abas: Início, Reservar, Minhas reservas e Perfil.

**Equipe, no tablet e no computador**
- Mesmo tema escuro, no estilo do painel da referência Vision UI.
- Tabela sem linhas pesadas: cabeçalho em maiúsculas pequenas, separador fino só entre linhas, bastante respiro.
- Menu lateral com ícone em cada item e o item ativo em verde.
- Banner de foto no topo com o botão principal em creme.
- Linha de indicadores com ícone, valor grande e comparação com o período anterior.
- Gráfico de área, barras de proporção e tabelas com ícone e duas linhas por célula.

**Regra dos ícones:** todo botão de ação, item de menu e linha de tabela leva um ícone que ajuda a reconhecer a ação. Ícone sem rótulo só em botão redondo de vidro (voltar, buscar, notificação).

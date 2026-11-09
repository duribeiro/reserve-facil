# Design system ReserveFácil

Aplicado ao restaurante fictício Ulivo. Fica no Figma, numa única página, **Design System**, com 7 seções lado a lado (Capa, Cores, Tipografia, Espaço e sombras, Ícones, Componentes, Assets): [abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=22-2). Decisão: [7](../pipeline/decisions/interface/0007-design-system-com-variaveis-e-dois-modos.md). Marca e referências: [padrao-visual.md](../referencias/padrao-visual.md).

## Regra de ouro

Nenhuma tela usa cor, fonte, espaçamento ou raio solto. Tudo vem de uma variável ou de um estilo desta página, e todo elemento repetido é uma instância de componente. Trocar o valor na variável muda o sistema inteiro.

## Variáveis (205)

| Coleção | O que tem | Modos |
|---|---|---|
| Primitives | 106 cores brutas: verde, terracota, creme, carvão, cinza, cores de aviso e versões transparentes para degradê. Não se usam nas telas | Valor |
| Color | 72 cores semânticas: `bg/`, `text/`, `border/`, `feedback/`. É o que as telas usam. `bg/brand` (verde) é a cor da ação principal; `bg/inverse` (verde) e `text/on-inverse` servem aos blocos verdes; as variáveis terminadas em `-clear` são a ponta transparente dos degradês; `bg/accent` (terracota) é só destaque; `bg/glass`, `bg/glass-dark` e `border/glass` são os vidros translúcidos | **Ulivo** (claro, creme e verde), **Ulivo escuro** e **Wireframe** (cinzas) |
| Spacing | 13 passos em múltiplos de 4: `space/0` até `space/96` | Valor |
| Radius | 8 raios em múltiplos de 4: `radius/none` até `radius/2xl`, `radius/slide` (40) e `radius/full` | Valor |
| Size | 6 tamanhos: altura de controle (`size/control/sm`, `md`, `lg`) e ícones (`size/icon/sm`, `md`, `lg`) | Valor |

Cada variável tem escopo definido (só aparece onde faz sentido) e nome para código no formato `var(--color-bg-page)`.

**Trocar de restaurante:** crie um modo novo na coleção Color e aponte cada cor semântica para a paleta do restaurante. O logo é o único componente com cores fixas e deve ser substituído.

## Estilos de texto (25)

| Grupo | Estilos | Fonte |
|---|---|---|
| Título | Display 48, H1 36, H2 28, H3 22 | Cormorant Garamond SemiBold |
| Texto | Corpo G 18, Corpo 16, Corpo P 14, Legenda 12 | DM Sans Regular |
| Rótulo | Rótulo 14, Rótulo P 12, Botão 16, Botão P 14, Overline 12 | DM Sans Medium |
| Número | Estatística 28 | DM Sans Bold |
| Slide | Capa 152, Título 72, Subtítulo 40, Corpo 32, Rótulo 28, Legenda 24, Overline 24, Número 72, Amostra 152, Mega 200, Destaque 56 | Cormorant Garamond e DM Sans. Só na apresentação |

Só duas fontes no arquivo: Cormorant Garamond e DM Sans.

## Cores e proporção

A combinação vem das referências do café, medida por script ([decisão 12](../pipeline/decisions/interface/0012-creme-e-verde-medidos-na-referencia-do-cafe.md)):

| Camada | Cor | Quanto da tela |
|---|---|---|
| Fundo e cartões | creme `#F4ECE2`, cartão `#FBF6EF`, bloco suave `#EFE6D8` | cerca de 65% |
| Blocos, botão principal, menu lateral | verde `#1F3226` | cerca de 30% |
| Destaque | terracota `#D9622B` | cerca de 5% |
| Texto | verde quase preto `#16251C`, secundário `#6B645D` | |

- **Cartão é claro**, sem borda, com sombra suave. Nunca cor escura chapada.
- **Botão principal é verde com texto creme.** Sobre bloco verde, use o botão Inverse.
- **Texto sobre foto** usa `text/on-photo` só dentro de bloco verde.
- **Foto que encontra o fundo** recebe um degradê para o creme, nunca corte seco.

## Padrões aprovados pelo dono

[Decisão 13](../pipeline/decisions/interface/0013-alta-fidelidade-aprovada-destaque-verde.md).

- **Destaque é verde:** item ativo, botão e seleção. Terracota fica no símbolo, em links, etiquetas e no gráfico.
- **Menu lateral** em degradê, de `bg/brand-hover` no topo para `bg/brand-pressed` embaixo. Item ativo em creme.
- **Campo sempre com ícone** à esquerda, que diz o que ele pede: calendário em data, pessoas em quantidade, cadeado em senha.
- **Caixa de ícone:** Suave sobre cartão claro, Claro sobre bloco suave, Verde no item ativo, Nenhum no menu verde.
- **Sombra sem corte:** quadro que contém sombra fica com o recorte desligado. Só a tela e o quadro arredondado com foto recortam.

## Efeitos (8)

Sombra sm, md e lg, Foco anel (contorno terracota usado em campo e botão com foco) e Vidro desfoque (fundo desfocado com sombra suave, para cartões e botões sobre fotos).

Na versão 2: Claro/cartao e Escuro/cartao (sombra em camadas com luz na borda) e Escuro/brilho menta (brilho discreto em gráficos).

## Ícones (48)

Biblioteca [Lucide](https://lucide.dev) (licença ISC), contorno de 2 px em grade de 24. Cada ícone é um componente `Icone/nome` e a cor vem de variável de texto. Tamanhos 16, 20 ou 24. O menu inferior e os botões usam a propriedade Ícone (troca de instância). O `Icone/emblema-ulivo` é o ramo de oliveira da marca e substitui qualquer ícone genérico quando o assunto é a marca.

## Assets

Fotos e mockups da marca Ulivo, com regras em [assets.md](assets.md).

## Componentes (27 famílias)

O gráfico de barras foi retirado: use o gráfico de área.

| Componente | Variantes e estados | Propriedades editáveis |
|---|---|---|
| Botão | Estilo (Primary verde, Secondary contorno, Text, Danger, Inverse creme para fundo escuro) x Estado (Default, Hover, Pressed, Focus, Disabled), 48 px | Rótulo, Tem ícone, Ícone |
| Botão pequeno | Os mesmos 25, 36 px, para tabelas | Rótulo, Tem ícone, Ícone |
| Chip | Selected (On, Off) x Estado (Default, Hover, Disabled) | Rótulo |
| Status | Tom: Neutro, Sucesso, Alerta, Perigo, Info | Rótulo |
| Campo | Estado: Default, Focus, Filled, Error, Disabled. Fundo branco (`bg/field`) | Rótulo, Valor, Ajuda, Tem ícone, Ícone |
| Alerta | Tom: Info, Sucesso, Alerta, Perigo | Título, Mensagem |
| Cartão | Estilo: Contorno, Suave, Vidro (translúcido, sobre fotos) | Sobretítulo, Título, Detalhe |
| Número | um | Rótulo, Valor |
| Mensagem WhatsApp | um | Mensagem |
| Barra superior | Voltar: Sim, Não | Título |
| Menu inferior | Aba (Ativa: Sim, Não, com ícone trocável), menu pronto e versão larga de cantos arredondados no topo | Rótulo, Ícone |
| Barra de status | um, com hora, sinal, wi-fi e bateria | nenhuma |
| Item do menu lateral | Estado: Default, Hover, Ativo. Usa a Caixa de ícone | Rótulo, Ícone da caixa |
| Caixa de ícone | Fundo: Suave, Claro, Verde, Nenhum. 32 x 32 com ícone de 20 | Ícone |
| Célula de tabela | Tipo: Cabeçalho, Corpo | Texto |
| Diálogo | um, com botão de perigo e botão secundário | Título, Mensagem |
| Imagem | um | Rótulo |
| Logo | Fundo: Verde, Creme, Carvão | nenhuma |
| Ação rápida | um | Rótulo, Ícone |
| Cabeçalho de seção | um | Título, Link |
| Card de conteúdo | um, horizontal com foto, etiqueta e botão | Etiqueta, Título, Descrição |
| Card vertical | um, foto no topo | Título, Detalhe, Ícone |
| Banner | um, bloco verde com foto à direita e botão creme | Sobretítulo, Título, Descrição |
| Item de lista | um, foto + status + seta | Título, Detalhe |
| Gráfico de área | um, duas curvas com degradê | Título, Variação, Comparação |
| Número com variação | um, ícone + valor + comparação | Valor, Rótulo, Variação, Ícone |

## Painel da versão 2

Indicador rico, Avatar, Card vertical v2, Card de conteúdo v2 e Banner v2. As versões v2 dos cartões usam foto com transparência real e substituem as antigas nas telas oficiais. As antigas ficam só para o backup.

## Modo escuro

Terceiro modo da coleção Color. Trocar o modo do quadro muda a tela inteira.

| Camada | Cor |
|---|---|
| Fundo | degradê de `#163A2F` a `#070E0B`, com luzes verdes, latão e terracota |
| Cartão | vidro escuro de `#1B2C26` a `#0B1310`, com borda iluminada no topo |
| Campo e cabeçalho de tabela | mais escuros que o cartão, `#070F0B` e `#0A130F` |
| Destaques | sálvia `#86C6A6`, latão `#DDB871`, terracota e creme |

- Fotos noturnas no lugar das diurnas.
- Brilho sempre discreto: é um restaurante.
- Grão por cima da tela inteira, nos dois modos.

## Regras de imagem e gráfico

- **Foto em cartão some por transparência** na própria imagem, com suavização gradual. Nunca faixa de cor por cima.
- Miniatura arredondada solta dentro do cartão mantém recorte normal.
- **Gráfico de área** mostra o balão ao lado de duas linhas tracejadas que se cruzam no ponto.
- **Medidor circular** começa em degradê.

## Slides

Título do slide, Rodapé do slide, Cartão de slide e Linha de slide. Só na apresentação, em 1920 x 1080, com texto de pelo menos 24.

## Como usar

- Monte telas só com instâncias. Se faltar uma peça, crie o componente aqui antes de usá-la.
- Creme domina o fundo e os cartões, verde floresta fica nos blocos e botões. Terracota é só destaque, cerca de 5% da tela: símbolo, link, anel de foco e detalhes pequenos. Nunca em botão principal ([decisão 8](../pipeline/decisions/interface/0008-laranja-so-destaque-botao-principal-verde.md)).
- Uma ação principal por tela, em botão verde. Sobre bloco verde, use o botão Inverse.
- Botão de perigo só para desfazer algo (cancelar reserva).
- Campo mostra o texto de ajuda apenas no erro ou quando preenchido.
- Para ver o wireframe com as mesmas peças, troque o modo da moldura para Wireframe.

## Fora desta versão

Caixa de seleção, interruptor, calendário e seletor de horário completo. Entram quando uma tela precisar.

## Estilo da alta fidelidade

Inspirado no app da referência Bean & Bloom e no painel da referência de dashboard. As telas ficam na página **Alta fidelidade** do Figma. Decisão: [10](../pipeline/decisions/interface/0010-composicao-rica-nas-telas.md).

**Cliente, no celular**
- Fundo creme. Cartões claros, com blocos verdes em alternância.
- A foto do topo **funde com o fundo creme** por um degradê, sem borda nem corte seco. É o que dá o ar de página de venda.
- Título em serifa, verde, sobre a área já clara, com uma frase curta embaixo.
- Cartões e botões de vidro translúcido quando ficam sobre a foto.
- Conteúdo em seções, cada uma com cabeçalho em caixa alta e atalho "Ver tudo": atalhos com ícone, grade de ambientes, card de prato e banner de evento.
- Menu inferior claro com 4 abas: Início, Reservar, Minhas reservas e Perfil.

**Equipe, no tablet e no computador**
- Fundo creme com menu lateral verde, na composição da referência Vision UI.
- Tabela sem linhas pesadas: cabeçalho em maiúsculas pequenas, separador fino só entre linhas, bastante respiro.
- Menu lateral com ícone em cada item e o item ativo em creme.
- Banner de foto no topo com o botão principal em creme.
- Linha de indicadores com ícone, valor grande e comparação com o período anterior.
- Gráfico de área, barras de proporção e tabelas com ícone e duas linhas por célula.

**Regra dos ícones:** todo botão de ação, item de menu e linha de tabela leva um ícone que ajuda a reconhecer a ação. Ícone sem rótulo só em botão redondo de vidro (voltar, buscar, notificação).

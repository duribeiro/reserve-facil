# Design system ReserveFácil

Aplicado ao restaurante fictício Ulivo. Fica no Figma, na página **Design System**: [abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=22-2). Decisão: [7](../pipeline/decisions/interface/0007-design-system-com-variaveis-e-dois-modos.md). Marca e referências: [padrao-visual.md](../referencias/padrao-visual.md).

## Regra de ouro

Nenhuma tela usa cor, fonte, espaçamento ou raio solto. Tudo vem de uma variável ou de um estilo desta página, e todo elemento repetido é uma instância de componente. Trocar o valor na variável muda o sistema inteiro.

## Variáveis (99)

| Coleção | O que tem | Modos |
|---|---|---|
| Primitives | 40 cores brutas: verde, terracota, creme, carvão, cinza e cores de aviso. Não se usam nas telas | Valor |
| Color | 35 cores semânticas: `bg/`, `text/`, `border/`, `feedback/`. É o que as telas usam | **Ulivo** (alta fidelidade) e **Wireframe** (cinzas) |
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

## Efeitos (4)

Sombra sm, md e lg, e Foco anel (contorno terracota usado em campo e botão com foco).

## Componentes (16 famílias, 79 variantes)

| Componente | Variantes e estados | Propriedades editáveis |
|---|---|---|
| Botão | Estilo (Primary, Secondary, Text, Danger) x Estado (Default, Hover, Pressed, Focus, Disabled), 48 px | Rótulo |
| Botão pequeno | Os mesmos 20, 36 px, para tabelas | Rótulo |
| Chip | Selected (On, Off) x Estado (Default, Hover, Disabled) | Rótulo |
| Status | Tom: Neutro, Sucesso, Alerta, Perigo, Info | Rótulo |
| Campo | Estado: Default, Focus, Filled, Error, Disabled | Rótulo, Valor, Ajuda |
| Alerta | Tom: Info, Sucesso, Alerta, Perigo | Título, Mensagem |
| Cartão | Estilo: Contorno, Suave | Sobretítulo, Título, Detalhe |
| Número | um | Rótulo, Valor |
| Mensagem WhatsApp | um | Mensagem |
| Barra superior | Voltar: Sim, Não | Título |
| Menu inferior | Aba (Ativa: Sim, Não) e o menu pronto com 3 abas | Rótulo |
| Item do menu lateral | Estado: Default, Hover, Ativo | Rótulo |
| Célula de tabela | Tipo: Cabeçalho, Corpo | Texto |
| Diálogo | um, com botão de perigo e botão secundário | Título, Mensagem |
| Imagem | um | Rótulo |
| Logo | Fundo: Verde, Creme, Carvão | nenhuma |

## Como usar

- Monte telas só com instâncias. Se faltar uma peça, crie o componente aqui antes de usá-la.
- Terracota só em ação principal, símbolo e link. Uma ação principal por tela.
- Botão de perigo só para desfazer algo (cancelar reserva).
- Campo mostra o texto de ajuda apenas no erro ou quando preenchido.
- Para ver o wireframe com as mesmas peças, troque o modo da moldura para Wireframe.

## Fora desta versão

Ícones (hoje são espaços reservados), caixa de seleção, interruptor, calendário e seletor de horário completo. Entram quando uma tela precisar.

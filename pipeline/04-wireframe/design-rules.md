# Regras de desenho

Valem para o wireframe e a alta fidelidade. A marca está em [padrao-visual.md](../../referencias/padrao-visual.md) e na [decisão 1](../decisions/interface/0001-marca-ulivo-cores-e-fontes.md).

## Tamanhos de tela

| Quem | Aparelho | Tamanho |
|---|---|---|
| Cliente | celular | 390 x 960 |
| Atendente | tablet deitado | 1366 x 1024 |
| Gerente | computador | 1440 x 900 |

## Wireframe

- Só tons de cinza e uma nota amarela para anotações. Sem cor de marca.
- Fonte única: DM Sans. Nada de terceira fonte no arquivo.
- Cantos arredondados de 8 (campos e botões) e 16 (cartões).
- Espaçamento em múltiplos de 4. Margem da tela: 20 no celular, 24 no computador e no tablet.
- Botão principal cheio e escuro; botão secundário só com contorno.
- Estados de erro e vazios ficam em nota amarela dentro de cada tela.

## Alta fidelidade

Cores medidas nas imagens de referência do café ([decisão 12](../decisions/interface/0012-creme-e-verde-medidos-na-referencia-do-cafe.md)).

- **Proporção:** creme cerca de 65% (fundo e cartões), verde floresta cerca de 30% (blocos, botões, menu lateral), terracota cerca de 5% (símbolo, links, etiquetas).
- **Fundo creme** `#F4ECE2`, cartão `#FBF6EF`, bloco suave `#EFE6D8`, verde `#1F3226`, texto `#16251C`.
- **Botão principal é verde** com texto creme. Sobre bloco verde, o botão é creme.
- **Destaque é verde:** item ativo, botão, seleção e ícones ([decisão 13](../decisions/interface/0013-alta-fidelidade-aprovada-destaque-verde.md)). Terracota fica para o símbolo da marca, links, etiquetas e gráfico.
- **Campo tem fundo branco e ícone à esquerda.** Ícone em cartão, tabela e menu fica na Caixa de ícone de 32 x 32.
- **Quadro que contém sombra fica sem recorte.** Só a tela e o quadro arredondado com foto recortam.
- **Fontes:** Cormorant Garamond para títulos e marca, DM Sans para o resto. Número com o algarismo 1 nunca em Cormorant: o 1 dela parece um I.
- **Fotos com luz do dia**, fundo claro e cor quente. A foto do topo funde com o creme.

## Versão 2 oficial

Modo claro e modo escuro, com painéis ricos ([decisão 15](../decisions/interface/0015-versao-2-oficial-com-modo-escuro.md)). Foto em cartão some por transparência real. Brilho sempre discreto. Regras completas em [design-system.md](../../docs/design-system.md).

## Espaçamento (hierarquia, do menor para o maior)

| Nível | Exemplo | Valor |
|---|---|---|
| Dentro de uma linha | ícone e texto, nome e detalhe | 4 |
| Entre itens do cartão | título, descrição, botão | 8 |
| Entre cartões lado a lado | atalhos, ambientes | 8 |
| Título de seção e conteúdo | "Nossos ambientes" e cartões | 12 |
| Preenchimento do cartão | | 16 |
| Margem da tela no celular | | 20 |
| Entre seções | | 32 |

Todo espaçamento e raio é múltiplo de 4 e vem de variável. Altura de botão 48 (36 em tabela), chip 36, etiqueta 20, item de menu lateral 48. No celular, item clicável tem pelo menos 44; chip fica fora dessa regra ([decisão 14](../decisions/processo-de-trabalho/0014-prototipo-sem-cliques-e-alvo-de-toque.md)). Toda tela de celular tem a Barra de status.

## Como conferir antes de entregar

Rodar a [régua](../04b-visual-references/regua.md) por script: espaçamentos fora de múltiplos de 4 (zero), cores e espaços soltos sem variável (zero), linhas de cartões com espaço 0 (zero), contraste calculado, teste de cinza e de desfoque, e a proporção de cor medida contra a referência.

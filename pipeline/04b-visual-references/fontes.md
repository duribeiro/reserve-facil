# Banco de fontes de referência

Lista de onde pesquisar, em ordem de confiança. Abra cada fonte de verdade antes de citar. Se uma fonte pedir login, pagamento ou bloquear, registre "bloqueada" e siga para a próxima. Preços e limites mudam: confira no site no dia.

Origem: pesquisa de 29/10/2026 em guias de terceiros. Os itens marcados "conferir" ainda não foram abertos pelo projeto.

## Nível 1. Apps reais publicados (maior peso)

| Fonte | Para que serve | Observação |
|---|---|---|
| Páginas de loja (App Store e Google Play) de apps do mesmo domínio e de domínios vizinhos | Capturas oficiais gratuitas, feitas pelo próprio produto | Abra pelo navegador |
| Mobbin | Biblioteca de capturas reais de apps, organizadas por padrão e por fluxo | Conferir o que o plano gratuito mostra |
| Refero | Banco de capturas de interfaces web e iOS | Conferir plano e limite |
| Page Flows | Fluxos completos gravados (cadastro, compra, assinatura) | Bom para jornadas, não para uma tela só. Conferir acesso |

## Nível 2. Sistemas de design oficiais (regra, não gosto)

| Fonte | Para que serve |
|---|---|
| Apple Human Interface Guidelines | Hierarquia, harmonia, consistência, alvos de toque, tipografia dinâmica |
| Material Design 3 | Cor, forma, tamanho, movimento, contenção; componentes e estados |
| Sistemas públicos de produto (exemplos: Atlassian, Shopify Polaris, IBM Carbon) | Como grandes equipes nomeiam e organizam variáveis e componentes |
| WCAG 2.2 (W3C) | Contraste, alvo de toque, foco, tamanho de texto |

## Nível 3. Estudos de caso

| Fonte | Para que serve |
|---|---|
| Behance | Projetos completos com processo e telas em uso |

## Nível 4. Conceito e clima (menor peso)

| Fonte | Para que serve |
|---|---|
| Dribbble | Direção visual e microinteração. As telas costumam ter dado falso: não use como prova de que um padrão funciona |
| Pinterest | Busca por qualquer tema, clima, cor e fotografia. Uma fonte entre as outras, sem prioridade sobre elas |

## Landing pages e design systems prontos

| Fonte | Para que serve |
|---|---|
| [ds.asimov.academy](https://ds.asimov.academy/) (Asimov Design Systems) | Galeria de 39 design systems, filtro por tema escuro e claro, busca e ordem. Cada item tem prévia em nova aba e download em .zip. Indicada pelo dono em 29/10/2026 como inspiração para landing pages. Conferido: a página abre e lista os itens. Não conferido: o conteúdo de cada prévia, a licença de uso e se o .zip serve de base. Antes de baixar qualquer arquivo, peça permissão ao dono |

Use para estudar como uma landing page organiza cor, tipografia, seções e componentes num sistema só. Trate cada item como referência de estudo (mesma regra das outras fontes), e confira a licença antes de reaproveitar qualquer arquivo.

## Regras de uso

- Entre as referências que ficam, pelo menos 4 vêm do nível 1 ou 2. Níveis 3 e 4 só completam.
- Referência de domínio vizinho vale: o que importa é o tipo de tela (lista, detalhe, filtro, entrada, vazio).
- Em galerias que agregam imagens (Pinterest, Dribbble e similares), siga o item até a origem (app, site ou estudo de caso) e avalie a origem, não a miniatura. Sem origem identificável, fica como clima.
- Registre em cada referência: link, data e o que foi aberto de fato (tela inteira ou miniatura).
- Imagens baixadas servem só para estudo e ficam fora do produto. Não publique a pasta `refs/`: o que entra no repositório são os links, as notas e a folha de avaliação.
- Atualize esta lista quando achar uma fonte melhor ou quando uma deixar de funcionar.

## Biblioteca de padrões por tipo de tela

Ao buscar, procure por tipo de tela e confira o que cada uma precisa resolver:

| Tipo de tela | O que conferir |
|---|---|
| Entrada e cadastro | Quantos campos, login social, o que acontece depois do primeiro toque |
| Landing page | Primeira dobra com uma promessa e uma ação, prova (número, depoimento, logo), seções curtas, chamada final |
| Início ou "hoje" | O foco único da tela, o que muda por dia, a primeira ação |
| Lista e coleção | Grade ou lista, filtro, ordem, estado vazio |
| Detalhe do item | Imagem, ação principal, informação secundária |
| Criação e câmera | Guia na tela, progresso, como cancelar |
| Filtros e busca | Escolha única ou múltipla, limpar, aplicar, contagem de resultados |
| Espera e processamento | Mostra progresso, mantém o contexto, diz quanto falta |
| Erro, vazio e sucesso | Diz o que houve e o que fazer em seguida |
| Perfil e ajustes | Agrupamento, alternadores, ações perigosas separadas |
| Acessibilidade | Tamanho de texto, alto contraste, movimento reduzido |

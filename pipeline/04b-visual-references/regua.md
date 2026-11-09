# Régua de qualidade visual

Usada nas etapas 4b (avaliar referências), 4c (conferir amostras), 4d e 4e (conferir telas). Serve para qualquer produto.

Por que existe: "bonito" não se mede, e uma tela bonita faz o avaliador perdoar problemas de uso (efeito estético-usabilidade, Kurosu e Kashimura, 1995). Por isso a régua separa o que se **mede**, o que se **julga com âncora** e o que se **compara**. Beleza nunca compensa uma falha de medição.

## Parte A. Portões (passa ou reprova, medido)

Reprovou em um, a referência ou a tela sai. Não existe nota para compensar.

| Portão | Como medir |
|---|---|
| Contraste de texto | Calcule a razão entre as cores de texto e de fundo pela fórmula de luminância relativa da WCAG. Texto normal: 4,5 para 1 ou mais. Texto grande (18 pt ou mais, ou 14 pt em negrito): 3 para 1 ou mais. Na referência, amostre as cores por script em vez de olhar. |
| Alvo de toque | 44 pontos (iOS) ou 48 (Android) em cada lado, ou mais, em itens clicáveis. Neste projeto, chips ficam fora ([decisão 14](../decisions/processo-de-trabalho/0014-prototipo-sem-cliques-e-alvo-de-toque.md)). |
| Cor sozinha não informa | Estado e erro também aparecem por ícone, forma ou texto. |
| Conteúdo real | Foto, dado e texto de verdade. Caixa cinza, texto de enchimento e dado impossível reprovam. |
| Escopo | Nada que o escopo do produto deixou de fora. |
| Produto real | Só para referência: captura de app publicado, ou estudo de caso com tela de uso. Imagem de conceito de galeria só entra como apoio de clima, nunca como prova de que algo funciona. |

## Parte B. Critérios com nota 0, 1 ou 2 (âncoras)

Para cada critério, escreva primeiro uma frase com **o que você vê** (evidência) e só depois a nota. Nota sem evidência vale 0.

| Critério | 0 | 1 | 2 |
|---|---|---|---|
| 1. Um foco por tela | Dois ou mais elementos disputam o primeiro olhar | O foco existe, mas um segundo elemento quase empata | Em 2 segundos dá para dizer qual é o principal |
| 2. Hierarquia sem cor | No teste de cinza e de desfoque, os níveis se misturam | Os níveis principais se mantêm, os secundários se perdem | Título, conteúdo, ação e apoio continuam distintos |
| 3. Conteúdo é protagonista | A decoração ocupa mais espaço que o conteúdo | Conteúdo e decoração dividem o espaço | Foto, produto ou dado ocupam o espaço e a moldura some |
| 4. Paleta contida | Mais de 5 cores sem papel claro | Paleta controlada, com um uso de cor sem função | Um fundo, um texto, um destaque e no máximo dois apoios, cada um com função |
| 5. Tipografia | Mais de 2 famílias, ou títulos quase iguais ao texto | 2 famílias, escala pouco marcada | No máximo 2 famílias e uma escala em que cada nível se distingue de longe |
| 6. Ritmo e respiro | Espaços irregulares, alinhamento quebrado | Espaço bom em parte da tela | Espaçamentos seguem uma escala (4 ou 8) e o alinhamento é consistente |
| 7. Consistência de componentes | Botões, chips e cartões com raios e pesos diferentes | Padrão com uma ou duas exceções | Mesmo raio, peso e espaçamento em tudo que é do mesmo tipo |
| 8. Profundidade com moderação | Sombra ou vidro em excesso, ou nenhuma separação entre camadas | Camadas legíveis, efeito um pouco forte | Efeito suave, só onde ajuda a separar camadas |
| 9. Ideia aproveitável | Nada que resolva um problema das telas-chave | Ideia boa, mas já resolvida no projeto | Resolve um problema real das telas-chave de um jeito novo para o projeto |

Total máximo: 18. Referência ou tela com menos de 11 não fica.

## Testes que o agente executa (não adivinhe, rode)

1. **Dois segundos:** abra a imagem e escreva em uma frase o que o olho vê primeiro. Se não for o que a tela quer destacar, o critério 1 vale 0.
2. **Cinza:** converta para escala de cinza (exemplo: Pillow, `convert("L")`) e confira se a hierarquia continua. Vale para o critério 2.
3. **Desfoque:** aplique desfoque forte (raio de 8 a 12 px) e veja se os blocos principais ainda se separam.
4. **Contraste:** amostre as cores com script e calcule a razão. Registre os dois códigos hexadecimais e o resultado.
5. **Grade:** meça 5 distâncias entre elementos. Se não são múltiplos de 4, o critério 6 vale no máximo 1.

## Parte C. Desempate por comparação

Notas sozinhas variam de uma rodada para outra. Para decidir entre as referências que empataram, compare **duas por vez** e escreva qual vence e por quê, em uma linha. Repita a comparação com a ordem trocada. Se o resultado mudar com a ordem, o empate é real: mantenha as duas.

## Regras para quem avalia

- Quem monta a amostra não dá sozinho a nota da própria amostra. Use a régua e mostre as evidências ao dono.
- Se só viu a miniatura, marque "miniatura" e não dê nota nos critérios 5, 6 e 7.
- Se o dono corrigir uma nota, a correção vale mais que a régua. Registre o que a correção ensina e ajuste os próximos julgamentos.

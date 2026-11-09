Roteiro da etapa 4c. Origem: experiência do projeto iCloset (27/10/2026). Amostras com silhuetas cinzas não convenceram; amostras com imagens reais e estruturas diferentes deixaram a escolha clara. Revisado em 29/10/2026 com matriz de diferença, estados e checagem medida.

---

Você é um designer de interface sênior. A partir da especificação visual
da etapa 4b, você monta três amostras de alta fidelidade com cara de app
pronto, para o dono escolher.

Leia antes: `pipeline/04b-visual-references/references.md`,
`pipeline/04b-visual-references/regua.md`, o wireframe aprovado e
`pipeline/04-wireframe/design-rules.md`.

Se algum arquivo faltar, pare e diga qual. Não invente.

Passo 1. Conteúdo real
Amostra com caixa cinza não é alta fidelidade. Defina as imagens de
conteúdo que as três telas-chave precisam (pessoas, produtos, lugares,
gráficos, o que o domínio pedir) e escolha a fonte, nesta ordem:

1. Gerador de imagem disponível no ambiente: procure entre as ferramentas
   conectadas (conectores de geração de imagem, ferramentas de IA da
   própria ferramenta de desenho) e entre as chaves de API do cofre.
   Antes de gerar, mostre ao dono quantas imagens, para quê e o custo
   estimado, e só gere depois do sim.
2. Banco de imagens gratuito com licença que permita uso comercial e
   modificação. Confira a licença de cada imagem e anote a origem.
3. Sem nenhuma das duas: ilustração vetorial (SVG) desenhada por você,
   com formas limpas e as cores da paleta. Avise o dono de que as
   amostras ficam menos realistas por isso.

Regras para o conteúdo:

- Pessoa gerada por IA nunca é uma pessoa real nem parecida com alguém
  conhecido.
- Quando a mesma pessoa ou o mesmo objeto aparece em mais de uma tela ou
  ângulo, gere a partir de uma imagem de referência para manter a
  consistência.
- Produtos e objetos isolados saem com fundo removido quando a tela pede
  recorte.
- Use textos e dados plausíveis do domínio, com tamanhos variados: pelo
  menos um título que ocupe duas linhas e um nome longo, para a amostra
  não depender de texto curto.
- Guarde as imagens na pasta de recursos visuais do projeto (padrão:
  `design/hifi-assets/`), com nomes descritivos e uma versão leve para a
  ferramenta de desenho.

Passo 2. Três amostras
Antes de desenhar, preencha a matriz abaixo e mostre ao dono. Se duas
amostras repetirem a mesma resposta em mais de duas linhas, refaça a
mais parecida.

| | Amostra A | Amostra B | Amostra C |
|---|---|---|---|
| Nome e frase de clima | | | |
| Referências de origem (números) | | | |
| Imagem: tela cheia, cartão, mosaico ou recorte | | | |
| Estrutura da lista: lista, grade ou mosaico | | | |
| Navegação: barra fixa, flutuante ou outra | | | |
| Cor: fundo e destaque | | | |
| Tipografia: par de fontes | | | |
| Raio e profundidade | | | |

Trocar só a cor não conta como amostra diferente. Cada amostra cobre as
três telas-chave definidas na etapa 4b e, em pelo menos uma delas, um
estado que não é o feliz (vazio, carregando ou erro).

Regras de qualidade, em todas:

- barra de status (sinal, Wi-Fi e bateria desenhados completos), barra de
  navegação e alvos de toque com tamanho real de celular;
- portões da Parte A de `regua.md` aprovados: contraste calculado por
  script nos pares de texto, alvo de toque medido, nada que só use cor
  para informar;
- nada que o escopo deixou de fora;
- confira cada tela por captura e corrija sobreposição, corte de texto e
  imagem mal enquadrada antes de mostrar;
- rode os testes de cinza e de desfoque de `regua.md`. Se a hierarquia
  some, a tela não está pronta.

Passo 3. Escolha do dono
Mostre as três lado a lado, com uma tabela comparando clima, cores,
fontes e a estrutura de cada tela, e diga de qual referência veio cada
ideia. Pergunte qual ele escolhe, ou o que ele quer misturar de cada uma.

Quando ele escolher, pergunte uma coisa a mais, porque muda o sistema:
se o produto deve ter modo de alto contraste agora. Se a visão do
produto cita acessibilidade, assuma que sim e só registre.

Grave a escolha como decisão em `pipeline/decisions/`, com a skill `adr`,
só depois de o dono decidir.

Antes de entregar, confira cada item:

- [ ] matriz preenchida e três amostras com estrutura diferente;
- [ ] cada amostra tem um estado que não é o feliz;
- [ ] contraste calculado por script e alvos medidos;
- [ ] captura conferida sem sobreposição nem corte;
- [ ] testes de cinza e desfoque feitos;
- [ ] decisão registrada depois da escolha do dono.

Critério de aceite: a lista acima inteira marcada.

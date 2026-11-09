Roteiro da etapa 4d. Revisado em 29/10/2026 com variáveis em duas camadas, modos de acessibilidade e páginas separadas, a partir do que o projeto iCloset aprendeu na alta fidelidade.

---

Você é um designer de sistemas. A partir da amostra escolhida pelo dono,
você monta o design system do produto, no formato de um painel de marca
completo.

Leia antes: a decisão da etapa 4c, a amostra escolhida,
`pipeline/04b-visual-references/references.md` e
`pipeline/04b-visual-references/regua.md`.

Se algum arquivo faltar, pare e diga qual. Não invente.

Organização do arquivo de desenho (páginas separadas):

- "Design system": o painel de marca, só o que o sistema define;
- "Protótipo: componentes de interação": os componentes que existem só
  para dar comportamento ao protótipo (alternadores, grupos de escolha,
  abas). Nunca na página das telas;
- "Alta fidelidade: telas": só telas.

Monte a página "Design system" com estas seções, nesta ordem:

1. Cores, em duas camadas. Primeira camada: a paleta bruta (nomes
   neutros, exemplo: verde-500). Segunda camada: as variáveis com nome de
   função (fundo, superfície, texto, texto secundário, linha, destaque,
   estados de sucesso, alerta e erro), que apontam para a paleta. Toda
   tela usa só a segunda camada. Cada variável com código hexadecimal.
2. Modos das cores: a coleção tem o modo Padrão e o modo Alto contraste
   (e Escuro, se a decisão da etapa 4c incluir). Trocar o modo muda a tela
   inteira sem editar tela.
3. Tipografia: famílias e escala (título grande, título, subtítulo,
   texto, legenda), com tamanho, peso e altura de linha. Cada nível como
   estilo de texto.
4. Grade e espaçamento: margens, colunas e a escala de espaçamento
   (múltiplos de 4 ou 8), como variáveis.
5. Raios, bordas e sombras: valores fixos, como variáveis ou estilos de
   efeito.
6. Componentes: botões (primário, secundário, ícone), campos, chips,
   cartões, listas, barra de navegação, cabeçalhos, alternadores, avisos,
   barra de status do aparelho (sinal, Wi-Fi e bateria completos) e
   estados de tela (vazio, carregando, erro, sucesso). Cada um como
   componente, com variantes para os estados (normal, pressionado,
   desativado, selecionado, foco).
7. Iconografia: estilo, espessura do traço e tamanho padrão.
8. Linguagem visual: tratamento de imagem (recorte, fundo, enquadramento)
   e grafismos ou padrões, se a amostra usar.
9. Acessibilidade: tabela com cada par de texto e fundo, a razão de
   contraste calculada por script em cada modo, alvos mínimos, e como cada
   componente se comporta com texto maior.
10. Aplicações: as três telas-chave refeitas só com os componentes e as
    variáveis do sistema, para provar que o sistema basta.

Regras de construção (valem para o sistema e para toda tela feita com ele):

- Todo contêiner usa auto layout, com espaçamento e preenchimento vindos
  das variáveis. Posição absoluta só para sobreposição intencional (selo
  sobre imagem, botão flutuante).
- Todo elemento que se repete é componente. Variações viram variantes
  (estado, tamanho, tipo), e textos, ícones e imagens trocáveis viram
  propriedades do componente.
- Componentes maiores são montados com componentes menores (um cartão de
  peça usa o selo de estado e o botão de ícone do sistema), para que mudar
  a peça pequena atualize todas as grandes.
- Nomes de camadas e componentes descrevem a função, não a aparência.
- Nomes de variáveis seguem o padrão que o código vai usar (minúsculas
  com hífen, exemplo: `texto-secundario`), para virarem tokens sem
  tradução na etapa de construção.
- Se um componente precisa de comportamento no protótipo (tocar, marcar,
  alternar), a interação fica dentro do próprio componente. Navegação
  entre telas nunca fica no componente, porque componente em outra página
  não consegue apontar para tela.

Regras:

- Nada solto: toda cor e todo texto das aplicações usam variável ou
  estilo. Verifique por script: liste os preenchimentos sem variável nas
  aplicações. O resultado precisa ser zero.
- Contraste de texto acima de 4,5 para 1 (3 para 1 em texto grande) e
  alvos de toque de pelo menos 44 pontos. Calcule, não estime.
- Escreva `docs/design-system.md` com uma linha por
  item: nome, valor e quando usar.

Mostre a página ao dono e peça aprovação.

Antes de entregar, confira cada item:

- [ ] três páginas separadas no arquivo de desenho;
- [ ] variáveis em duas camadas e modo Alto contraste funcionando;
- [ ] contraste calculado em todos os pares, em todos os modos;
- [ ] zero preenchimento solto nas aplicações;
- [ ] barra de status completa e estados de tela como componentes;
- [ ] documento `design-system.md` com todos os itens.

Critério de aceite: a lista acima inteira marcada e a página aprovada
pelo dono.

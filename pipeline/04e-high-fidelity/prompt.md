Roteiro da etapa 4e. Revisado em 29/10/2026 com as regras de protótipo realista que o projeto iCloset aprendeu (decisão 15).

---

Você é um designer de interface. Você leva o wireframe aprovado para a
alta fidelidade, uma jornada por vez, usando só o design system.

Leia antes: o wireframe aprovado, `pipeline/04-wireframe/README.md` (lista
de telas e mapa da jornada), `docs/design-system.md`
e `pipeline/04b-visual-references/regua.md`.

Se algum arquivo faltar, pare e diga qual. Não invente.

Para cada jornada, na ordem do mapa:

1. Refaça cada tela com os componentes e as variáveis do design system,
   seguindo as regras de construção da etapa 4d: auto layout em todo
   contêiner, instâncias de componentes com propriedades em vez de
   cópias soltas, e variantes para os estados. Se faltar um componente,
   crie no sistema primeiro e depois use.
2. Use imagens de conteúdo reais, da mesma fonte e com as mesmas regras
   da etapa 4c.
3. Desenhe também os estados que o wireframe não mostra: vazio,
   carregando, erro e sucesso, quando a tela tiver. Se um toque leva a
   uma espera (gerar, enviar, processar), desenhe a tela de espera e faça
   ela seguir sozinha para o resultado.
4. Ligue o protótipo para que ele se comporte como o app:
   - toda seta de voltar usa a ação "Voltar" do protótipo, e nunca uma
     tela fixa;
   - escolha única (um marcado por vez) e escolha múltipla (liga e desliga)
     mudam de verdade, tanto em chips quanto em opções;
   - filtros e abas filtram o conteúdo da tela (use variáveis do protótipo
     quando a ferramenta oferecer);
   - galerias e vistas trocam por toque e por arraste;
   - tela maior que o celular rola, por baixo da barra de navegação;
   - transições: entrar numa tela desliza, trocar de aba esmaece;
   - todo cartão, linha de lista e ícone que parece tocável leva a algum
     lugar. Se não há tela para o destino, crie a tela de apoio ou
     registre a lacuna no relatório;
   - defina os fluxos nomeados para a apresentação (um por jornada).
5. Confira por captura: texto cortado, sobreposição, contraste calculado,
   alvos de toque de pelo menos 44 pontos e consistência com o sistema.
   Troque o modo de Alto contraste e confira de novo uma tela por jornada.
6. Teste a navegação por script e registre os números: total de
   navegações, setas com "Voltar" real, esperas automáticas, destinos
   inexistentes (precisa ser zero), toques para a própria tela (zero) e
   telas inalcançáveis a partir da primeira (zero). Liste os elementos
   tocáveis sem destino.
7. Teste o protótipo em modo de apresentação, tocando de verdade nos
   caminhos principais. O que só foi verificado pelos dados do arquivo
   e não no modo de apresentação precisa constar no relatório como "não
   testado ao vivo".
8. Mostre a jornada ao dono e peça o veredito: aprovada, aprovada com
   ajuste, ou refazer.

Ajuste que muda uma regra visual volta para o design system e vira
decisão em `pipeline/decisions/` depois do veredito. Mudança grande no
comportamento do protótipo também vira decisão.

Antes de entregar cada jornada, confira cada item:

- [ ] zero valor solto fora do design system;
- [ ] estados de vazio, carregando, erro e sucesso desenhados onde existem;
- [ ] números do teste de navegação registrados, com zeros onde exigido;
- [ ] lista de elementos tocáveis sem destino no relatório;
- [ ] testado em modo de apresentação, ou declarado "não testado ao vivo";
- [ ] componentes de interação fora da página das telas.

Critério de aceite: todas as jornadas aprovadas, protótipo navegável de
ponta a ponta e nenhuma tela com valor solto fora do design system.

# Padrão de assets

Fotos e mockups do restaurante fictício Ulivo, na seção **Assets** da página Design System do Figma: [abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=22-2). Os arquivos de imagem ficam no Figma e não sobem para o repositório. Este documento guarda as regras e os prompts para gerar de novo.

## Regras

- **Origem:** geradas no Google Flow com o modelo Nano Banana 2.1 (custo 0 crédito). São imagens de IA para o protótipo. Em produção, troque por fotos reais do restaurante.
- **Prompt em inglês**, sempre com a paleta: verde floresta, carvão, creme, âmbar quente e só um toque de terracota.
- **Sem texto e sem logo dentro da imagem.** Logo e textos entram pelos componentes.
- **Proporções:** 16:9 para banner, 3:4 para retrato e mockup, 1:1 para prato e cartão.
- **Nome da camada:** `foto/assunto` ou `mockup/assunto`, minúsculas e sem acento.
- **Uso nas telas:** a foto entra como preenchimento de um quadro, com degradê carvão por baixo quando há texto por cima.

## Imagens (10)

| Camada | Proporção | Assunto | Usada em |
|---|---|---|---|
| foto/salao | 16:9 | Salão ao anoitecer, paredes verdes e mesas de madeira escura | Entrar, Início, Mesas |
| foto/massa | 1:1 | Massa com cogumelos em prato carvão, vista de cima | Início, Minhas reservas |
| foto/fachada | 3:4 | Fachada com placa redonda verde e emblema de oliveira | Confirmar, Detalhe, Cancelar |
| foto/equipe | 3:4 | Atendente de avental carvão com bandeja | Usuários |
| mockup/cardapio | 3:4 | Cardápio verde com emblema e página creme | Marca aplicada |
| mockup/embalagem | 3:4 | Sacola, copo e caixa de viagem | Marca aplicada |
| foto/sobremesa | 1:1 | Mousse de chocolate com framboesas | Início, Minhas reservas |
| foto/bar | 16:9 | Bar e adega com luz quente | Minhas reservas, Alterar, Horários, Reservas do dia |
| foto/vinho | 3:4 | Taça de vinho branco com vela | Cadastro, Início, Minhas reservas |
| foto/mesa | 16:9 | Mesa posta vista de cima com oliveira | Buscar mesa, Reserva confirmada, Relatórios |

## Como gerar de novo

Use o servidor MCP do Flow, projeto Ulivo, coleção assets, `custo_max` 0 e chave de idempotência nova a cada tentativa. Base do prompt:

```text
<enquadramento>, <sujeito em um restaurante italiano elegante>, <luz>, shallow depth of field.
Palette of forest green, charcoal, cream and a touch of terracotta. No text, no logos.
```

O Flow recusou 2 de 10 pedidos feitos em lote ("atividade incomum"). Pedir de novo, com chave nova, funcionou.

## Ícones

Lucide (licença ISC), versão 0.468.0. Mais regras em [design-system.md](design-system.md).

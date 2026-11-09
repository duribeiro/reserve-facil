# Visão

Etapa 1, aprovada pelo dono em 08/11/2026. Base: levantamento de requisitos da turma ([docs/requisitos-reservefacil.md](../../docs/requisitos-reservefacil.md)) e as respostas do dono. Sinais de sucesso e riscos são inferência do agente, pendentes de confirmação.

## Visão

- **Problema:** restaurantes que recebem reservas por telefone, mensagem ou pessoalmente sofrem com reservas duplicadas, informação perdida e dificuldade para alterar ou cancelar horários.
- **Quem usa:** o cliente do restaurante (reserva, consulta, altera e cancela), o atendente (acompanha o dia, registra chegada e ausência) e o gerente (mesas, horários, regras, usuários, relatórios). O cliente é quem mais usa.
- **Em uma frase:** o ReserveFácil é um sistema que ajuda clientes e equipe de restaurantes a reservar e controlar mesas sem duplicidade nem perda de informação, contratado por cada restaurante e personalizado com a marca dele.
- **Escopo deste protótipo:** uma implementação, para o restaurante fictício **Ulivo**. A estrutura é a mesma que será vendida a outros restaurantes (SaaS); cada um ganha a própria marca. O protótipo não desenha cadastro de restaurantes nem painel de várias marcas.
- **Aviso ao cliente:** confirmação e cancelamento chegam por WhatsApp.
- **Sinais de sucesso (inferência):**
  - Nenhuma reserva duplicada para a mesma mesa e horário.
  - O cliente reserva, altera e cancela sem ligar para o restaurante.
- **Riscos (inferência):**
  - Duas reservas para a mesma mesa.
  - Aviso de confirmação ou cancelamento que não chega.
  - Cliente enxergando reserva de outra pessoa.
- **O que acontece se falhar:** duas famílias chegam para a mesma mesa e uma fica sem lugar; ou a mesa fica vazia porque o cancelamento não foi avisado; ou dados de um cliente vazam para outro.

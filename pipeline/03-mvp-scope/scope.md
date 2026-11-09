# Escopo do MVP

Etapa 3, aprovada pelo dono em 08/11/2026. Base: [features.md](features.md). Regra do corte: entra agora só o que o levantamento da turma exige ([docs/requisitos-reservefacil.md](../../docs/requisitos-reservefacil.md)). Todo o resto será feito depois. Decisão: [5](../decisions/produto/0005-escopo-agora-so-o-que-o-pdf-exige.md).

## Escopo do MVP

### Agora (primeira versão)

- Cadastro e login dos 3 perfis (manter): sem conta não há reserva por cliente.
- Consultar mesas disponíveis (manter): o cliente vê se há lugar antes de reservar.
- Realizar, ver, alterar e cancelar reserva (manter): é o ciclo central.
- Conferência anti-duplicidade e de capacidade (manter): é o problema de origem.
- Confirmação e aviso de cancelamento por WhatsApp (simular): a tela mostra a mensagem, o envio real é manual.
- Reservas do dia, check-in e ausência (manter): o atendente organiza o dia.
- Atendente cadastra reserva para cliente (manter): atende telefone e balcão.
- Gerenciar mesas (manter): cadastrar, editar e remover, com capacidade.
- Horários de funcionamento e regras de reserva, incluindo tempo de tolerância (manter): sem isso o sistema não valida nada.
- Gerenciar usuários (simplificar): lista simples, sem permissões finas.
- Relatórios (simplificar): reservas do dia e ausências, sem gráficos.

### Depois (próximas versões)

Tudo o que o dono aprovou no brainstorm e o PDF não exige:

- Conta: entrar com Google ou Apple, recuperar senha, perfil do cliente, histórico de visitas.
- Reserva: pedido especial, escolher área, escolher mesa no mapa, lista de espera, adicionar ao calendário.
- WhatsApp: lembrete no dia anterior, confirmação de presença, aviso de alteração, pesquisa de satisfação.
- Atendimento: mapa da sala ao vivo, fila de quem chegou sem reserva, anotações do atendente, bloquear mesa.
- Gestão: bloquear datas, relatório de horários de pico, exportar planilha.
- Marca e site: landing page do Ulivo, cardápio digital, galeria e localização, troca de marca por restaurante.
- Pagamento: sinal para grupos grandes, taxa de cancelamento tardio.

### Nunca

Nada por enquanto. O dono quer fazer todas as ideias aprovadas, então a taxa de cancelamento tardio, que o agente tinha proposto para Nunca, ficou em Depois.

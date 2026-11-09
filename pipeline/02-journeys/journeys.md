# Jornadas

Etapa 2, confirmada pelo dono em 08/11/2026. Base: [vision.md](../01-problem-and-vision/vision.md) e [docs/requisitos-reservefacil.md](../../docs/requisitos-reservefacil.md). Frases marcadas com * têm motivo escrito pelo agente, não pelo PDF.

## Jornadas

### Cliente

- Como cliente, quero criar uma conta para poder usar as funções de reserva.
- Como cliente, quero entrar no sistema para acessar minha conta e minhas reservas.
- Como cliente, quero consultar as mesas disponíveis por data, horário e número de pessoas para saber se há lugar antes de decidir.
- Como cliente, quero reservar uma mesa para garantir meu lugar no restaurante.
- Como cliente, quero ver minhas reservas para saber o que tenho marcado, sem ver as de outras pessoas.
- Como cliente, quero alterar data, horário ou número de pessoas de uma reserva para ajustar quando meu plano muda.
- Como cliente, quero cancelar uma reserva para liberar a mesa quando não puder ir.

### Atendente

- Como atendente, quero ver as reservas do dia e o status de cada uma para organizar o atendimento.
- Como atendente, quero cadastrar uma reserva em nome de um cliente para atender quem pede por telefone ou na porta, sem criar duplicidade.*
- Como atendente, quero registrar a chegada do cliente (check-in) para saber que a mesa está ocupada.
- Como atendente, quero registrar a ausência depois do tempo de tolerância para registrar o não comparecimento e liberar a mesa.
- Como atendente, quero entrar no sistema com o meu perfil para ver só o que cabe ao meu trabalho.*

### Gerente

- Como gerente, quero cadastrar, editar e remover mesas, com a capacidade de cada uma, para o sistema refletir a sala real.
- Como gerente, quero definir horários de funcionamento e regras de reserva para que as reservas respeitem o jeito que o restaurante trabalha.
- Como gerente, quero administrar os usuários do sistema para controlar quem acessa e com qual perfil.
- Como gerente, quero consultar relatórios para acompanhar as reservas do restaurante.
- Como gerente, quero entrar no sistema com o meu perfil para acessar as configurações.*

### Sistema

- Como sistema, quero conferir disponibilidade, capacidade da mesa e regras antes de confirmar uma reserva para nunca permitir duas reservas na mesma mesa e horário.
- Como sistema, quero enviar a confirmação por WhatsApp depois de uma reserva para o cliente ter certeza de que está marcada.
- Como sistema, quero enviar o aviso de cancelamento por WhatsApp para o cliente saber que a reserva foi desfeita.
- Como sistema, quero deixar o cliente ver, alterar e cancelar só as próprias reservas para proteger os dados de cada pessoa.
- Como sistema, quero bloquear o check-in fora da data e a ausência antes da tolerância para o status da reserva refletir a realidade.
- Como sistema, quero avisar o motivo quando recuso uma reserva (sem mesa, capacidade, horário) para o cliente saber o que ajustar.*
- Como sistema, quero impedir a remoção de uma mesa que gere conflito com reservas existentes para não deixar reserva sem mesa.

## Fora desta versão

Lembrete no dia anterior, lista de espera, recuperar senha e pagamento. O PDF não pede e a primeira versão para sem isso.

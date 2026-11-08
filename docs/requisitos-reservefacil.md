# ReserveFácil: Sistema de Reserva para Restaurante

Levantamento de requisitos do trabalho da faculdade, transcrito do PDF original. O PDF fica só na máquina local.

## 1. Introdução

O ReserveFácil é um sistema para organizar as reservas de mesas em restaurantes. Quando os pedidos são feitos por telefone, mensagens ou presencialmente, podem ocorrer reservas duplicadas, perda de informações e dificuldades para alterar ou cancelar horários. O sistema centraliza essas atividades e facilita o controle das reservas.

- O **cliente** pode criar uma conta, consultar mesas disponíveis, realizar reserva, visualizar, alterar e cancelar suas reservas.
- O **atendente** pode cadastrar reservas para clientes, acompanhar as reservas do dia, realizar check-in e registrar ausências.
- O **gerente** administra mesas, horários de funcionamento, regras e usuários, além de consultar relatórios.
- Um **serviço externo** envia confirmações e avisos de cancelamento.

## 2. Atores

| Ator | O que faz |
|---|---|
| Cliente | Utiliza as funções relacionadas à própria conta e às próprias reservas. |
| Atendente | Cadastra reservas para clientes, acompanha as reservas do dia, registra chegadas e ausências. |
| Gerente | Configura o funcionamento do sistema, administra mesas e usuários e consulta relatórios. |
| Serviço de Notificações | Sistema externo responsável por enviar confirmações e avisos de cancelamento aos clientes. |

## 3. Diagrama de casos de uso (descrito em texto)

O diagrama original agrupa os casos de uso por ator.

| Ator | Casos de uso |
|---|---|
| Cliente | Cadastrar-se; Fazer login; Consultar mesas disponíveis; Realizar reserva; Consultar minhas reservas; Alterar reserva; Cancelar reserva |
| Atendente | Registrar reserva para cliente; Consultar reservas do dia; Confirmar chegada (check-in); Registrar ausência |
| Gerente | Cadastrar mesas; Editar mesas; Remover mesas; Configurar horários; Definir regras de reserva; Gerenciar usuários; Consultar relatórios |
| Serviço de Notificações | Enviar confirmação; Enviar aviso de cancelamento |

Relações `include`:

- Realizar reserva inclui Consultar mesas disponíveis.
- Alterar reserva inclui Consultar mesas disponíveis.
- Realizar reserva inclui Enviar confirmação.
- Cancelar reserva inclui Enviar aviso de cancelamento.

Fazer login serve ao cliente, ao atendente e ao gerente.

## 4. Descrição textual dos principais casos de uso

As descrições detalham os principais fluxos de interação entre os atores e o sistema. Os fluxos alternativos representam situações previstas pelas regras da documentação.

### 4.1 Cadastrar-se

- **Ator principal:** Cliente
- **Objetivo:** O cliente cria uma conta para utilizar as funcionalidades de reserva.
- **Pré-condição:** O cliente ainda não possui uma conta cadastrada.
- **Fluxo principal:**
  1. O cliente acessa a opção de cadastro.
  2. O sistema apresenta os campos necessários para o cadastro.
  3. O cliente informa seus dados.
  4. O sistema valida as informações e registra a conta.
  5. O sistema informa que o cadastro foi realizado.
- **Fluxos alternativos:** Se houver informação obrigatória ausente ou inválida, o sistema informa o problema e solicita a correção.
- **Pós-condição:** A conta do cliente fica cadastrada no sistema.

### 4.2 Fazer login

- **Ator principal:** Cliente, Atendente ou Gerente
- **Objetivo:** O usuário acessa o sistema de acordo com seu perfil.
- **Pré-condição:** O usuário possui cadastro no sistema.
- **Fluxo principal:**
  1. O usuário acessa a opção de entrar no sistema.
  2. O sistema solicita as credenciais de acesso.
  3. O usuário informa suas credenciais.
  4. O sistema valida os dados.
  5. O sistema permite o acesso conforme o perfil do usuário.
- **Fluxos alternativos:** Se as credenciais forem inválidas, o sistema informa que não foi possível entrar e solicita uma nova tentativa.
- **Pós-condição:** O usuário fica autenticado no sistema.

### 4.3 Consultar mesas disponíveis

- **Ator principal:** Cliente
- **Objetivo:** O cliente verifica a disponibilidade de mesas para uma data, horário e quantidade de pessoas.
- **Pré-condição:** O cliente está conectado ao sistema.
- **Fluxo principal:**
  1. O cliente acessa a consulta de disponibilidade.
  2. O sistema solicita data, horário e quantidade de pessoas.
  3. O cliente informa os dados.
  4. O sistema verifica as mesas disponíveis, considerando a capacidade e os horários de funcionamento.
  5. O sistema apresenta as opções disponíveis.
- **Fluxos alternativos:** Se não houver mesa compatível, o sistema informa que não há disponibilidade para os dados informados.
- **Pós-condição:** O cliente visualiza a disponibilidade correspondente à pesquisa.

### 4.4 Realizar reserva

- **Ator principal:** Cliente
- **Objetivo:** O cliente registra uma reserva de mesa no restaurante.
- **Pré-condição:** O cliente está conectado ao sistema.
- **Fluxo principal:**
  1. O cliente seleciona a opção de realizar reserva.
  2. O sistema solicita data, horário e quantidade de pessoas.
  3. O cliente informa os dados e escolhe uma opção disponível.
  4. O sistema verifica novamente a disponibilidade, a capacidade da mesa e as regras do restaurante.
  5. O sistema registra a reserva.
  6. O sistema solicita o envio da confirmação ao Serviço de Notificações.
- **Fluxos alternativos:**
  - Se não houver mesa disponível, o sistema informa a indisponibilidade e não confirma a reserva.
  - Se a quantidade de pessoas exceder a capacidade da mesa, ou o horário não respeitar o funcionamento, o sistema informa que a reserva não pode ser realizada.
  - Se a mesa já estiver reservada para um período conflitante, o sistema impede a duplicidade.
- **Pós-condição:** A reserva fica registrada e vinculada ao cliente; a confirmação é enviada pelo serviço externo.

### 4.5 Visualizar próprias reservas

- **Ator principal:** Cliente
- **Objetivo:** O cliente consulta as reservas vinculadas à sua conta.
- **Pré-condição:** O cliente está conectado ao sistema.
- **Fluxo principal:**
  1. O cliente acessa a área de suas reservas.
  2. O sistema identifica a conta do cliente.
  3. O sistema apresenta as reservas vinculadas àquela conta.
- **Fluxos alternativos:** Se o cliente ainda não possuir reservas, o sistema informa que não há reservas cadastradas.
- **Pós-condição:** As reservas do cliente são exibidas sem apresentar reservas de outras contas.

### 4.6 Alterar reserva

- **Ator principal:** Cliente
- **Objetivo:** O cliente modifica os dados de uma reserva própria.
- **Pré-condição:** O cliente está conectado e possui uma reserva ativa.
- **Fluxo principal:**
  1. O cliente acessa suas reservas.
  2. O cliente seleciona a reserva que deseja alterar.
  3. O sistema verifica se a reserva pertence ao cliente.
  4. O cliente informa os novos dados de data, horário ou quantidade de pessoas.
  5. O sistema verifica disponibilidade e regras do restaurante.
  6. O sistema atualiza a reserva e informa a alteração ao cliente.
- **Fluxos alternativos:**
  - Se a reserva não pertencer ao cliente, o sistema não permite a alteração.
  - Se o novo horário não estiver disponível ou não atender às regras, o sistema informa o problema e mantém os dados anteriores.
- **Pós-condição:** A reserva é atualizada somente quando as novas condições são válidas.

### 4.7 Cancelar reserva

- **Ator principal:** Cliente
- **Objetivo:** O cliente cancela uma reserva própria.
- **Pré-condição:** O cliente está conectado e possui uma reserva ativa.
- **Fluxo principal:**
  1. O cliente acessa suas reservas.
  2. O cliente seleciona a reserva que deseja cancelar.
  3. O sistema verifica se a reserva pertence ao cliente.
  4. O cliente confirma o cancelamento.
  5. O sistema altera o status da reserva para cancelada.
  6. O sistema solicita ao Serviço de Notificações o envio do aviso de cancelamento.
- **Fluxos alternativos:** Se a reserva não pertencer ao cliente, o sistema impede o cancelamento.
- **Pós-condição:** A reserva fica cancelada e o aviso de cancelamento é enviado pelo serviço externo.

### 4.8 Cadastrar reserva para cliente

- **Ator principal:** Atendente
- **Objetivo:** O atendente registra uma reserva em nome de um cliente.
- **Pré-condição:** O atendente está conectado ao sistema.
- **Fluxo principal:**
  1. O atendente acessa a opção de cadastrar reserva.
  2. O atendente informa os dados do cliente, a data, o horário e a quantidade de pessoas.
  3. O sistema verifica disponibilidade, capacidade da mesa e regras do restaurante.
  4. O sistema registra a reserva.
  5. O sistema apresenta a confirmação do cadastro.
- **Fluxos alternativos:** Se não houver disponibilidade ou os dados não atenderem às regras, o sistema informa o motivo e não registra a reserva.
- **Pós-condição:** A reserva fica registrada no sistema para o cliente informado.

### 4.9 Consultar reservas do dia

- **Ator principal:** Atendente
- **Objetivo:** O atendente acompanha as reservas previstas para o dia.
- **Pré-condição:** O atendente está conectado ao sistema.
- **Fluxo principal:**
  1. O atendente acessa a consulta de reservas do dia.
  2. O sistema recupera as reservas da data correspondente.
  3. O sistema apresenta a lista de reservas e seus respectivos status.
- **Fluxos alternativos:** Se não houver reservas para a data, o sistema informa que a lista está vazia.
- **Pós-condição:** O atendente visualiza as reservas previstas para organizar o atendimento.

### 4.10 Registrar chegada (check-in)

- **Ator principal:** Atendente
- **Objetivo:** O atendente registra a chegada do cliente ao restaurante.
- **Pré-condição:** O atendente está conectado e existe uma reserva para a data do atendimento.
- **Fluxo principal:**
  1. O atendente localiza a reserva do cliente.
  2. O atendente confirma a chegada do cliente.
  3. O sistema verifica se a reserva corresponde à data atual.
  4. O sistema atualiza o status da reserva para chegada confirmada (check-in).
- **Fluxos alternativos:** Se a reserva não corresponder à data atual, o sistema não realiza o check-in.
- **Pós-condição:** O status da reserva passa a indicar que o cliente chegou.

### 4.11 Registrar ausência

- **Ator principal:** Atendente
- **Objetivo:** O atendente registra que o cliente não compareceu à reserva.
- **Pré-condição:** O atendente está conectado e existe uma reserva para aquele dia.
- **Fluxo principal:**
  1. O atendente consulta as reservas do dia.
  2. O atendente identifica a reserva cujo cliente não compareceu.
  3. Após o período de tolerância configurado, o atendente registra a ausência.
  4. O sistema atualiza o status da reserva para ausência.
- **Fluxos alternativos:** Se o período de tolerância ainda não tiver terminado, o sistema não permite registrar a ausência.
- **Pós-condição:** A ausência fica registrada no status da reserva.

### 4.12 Gerenciar mesas

- **Ator principal:** Gerente
- **Objetivo:** O gerente cadastra, edita ou remove mesas utilizadas nas reservas.
- **Pré-condição:** O gerente está conectado ao sistema.
- **Fluxo principal:**
  1. O gerente acessa o gerenciamento de mesas.
  2. O gerente escolhe cadastrar, editar ou remover uma mesa.
  3. O gerente informa ou altera os dados da mesa, incluindo sua capacidade.
  4. O sistema valida os dados e salva a operação.
- **Fluxos alternativos:**
  - Se os dados forem inválidos, o sistema informa o problema e não salva a alteração.
  - A remoção de uma mesa não deve permitir a criação de conflitos com reservas existentes; o sistema deve validar a situação antes de concluir a operação.
- **Pós-condição:** O cadastro de mesas fica atualizado para utilização nas reservas.

### 4.13 Configurar horários e regras de reserva

- **Ator principal:** Gerente
- **Objetivo:** O gerente define os horários de funcionamento e as regras que serão aplicadas às reservas.
- **Pré-condição:** O gerente está conectado ao sistema.
- **Fluxo principal:**
  1. O gerente acessa as configurações do restaurante.
  2. O gerente informa ou altera os horários de funcionamento e as regras de reserva.
  3. O sistema valida as configurações.
  4. O sistema salva as novas configurações.
  5. O sistema considera essas configurações nas próximas reservas.
- **Fluxos alternativos:** Se as configurações forem inválidas ou inconsistentes, o sistema informa o problema e solicita a correção.
- **Pós-condição:** As configurações ficam salvas e passam a orientar as próximas reservas.

### 4.14 Gerenciar usuários

- **Ator principal:** Gerente
- **Objetivo:** O gerente administra os usuários do sistema.
- **Pré-condição:** O gerente está conectado ao sistema.
- **Fluxo principal:**
  1. O gerente acessa a área de gerenciamento de usuários.
  2. O gerente seleciona a operação de gerenciamento disponível.
  3. O gerente informa ou altera os dados necessários.
  4. O sistema valida e salva a operação.
- **Fluxos alternativos:** Se os dados forem inválidos, o sistema informa o problema e não salva a operação.
- **Pós-condição:** Os dados dos usuários ficam atualizados.

### 4.15 Consultar relatórios

- **Ator principal:** Gerente
- **Objetivo:** O gerente consulta relatórios para acompanhar as reservas do restaurante.
- **Pré-condição:** O gerente está conectado ao sistema.
- **Fluxo principal:**
  1. O gerente acessa a opção de relatórios.
  2. O gerente seleciona o relatório ou os critérios disponíveis.
  3. O sistema reúne as informações correspondentes.
  4. O sistema apresenta o relatório.
- **Fluxos alternativos:** Se não houver dados para os critérios selecionados, o sistema informa que não existem resultados.
- **Pós-condição:** O relatório solicitado é exibido ao gerente.

## 5. Regras gerais do sistema

1. Uma reserva só pode ser confirmada quando houver mesa disponível.
2. Não podem existir reservas conflitantes para a mesma mesa e horário.
3. A quantidade de pessoas deve respeitar a capacidade da mesa.
4. O cliente só pode alterar ou cancelar suas próprias reservas.
5. As reservas devem respeitar os horários e as regras definidos pelo gerente.
6. O check-in deve ocorrer na data reservada.
7. A ausência pode ser registrada após o período de tolerância configurado.

## 6. BDD: cenários de comportamento

### Realizar uma reserva com sucesso

- **Dado** que o cliente esteja conectado ao sistema **e** exista uma mesa disponível no horário escolhido
- **Quando** informar a data, o horário e a quantidade de pessoas
- **Então** o sistema deve registrar a reserva **e** enviar uma confirmação ao cliente.

### Tentar reservar sem disponibilidade

- **Dado** que não existam mesas disponíveis no horário escolhido
- **Quando** o cliente tentar realizar a reserva
- **Então** o sistema deve informar que não há disponibilidade **e** não deve confirmar a reserva.

### Impedir uma reserva conflitante

- **Dado** que uma mesa já esteja reservada para determinado horário
- **Quando** outra reserva for solicitada para a mesma mesa e horário
- **Então** o sistema deve impedir o conflito.

### Consultar as próprias reservas

- **Dado** que o cliente esteja conectado
- **Quando** acessar a área de reservas
- **Então** o sistema deve exibir as reservas vinculadas à sua conta.

### Alterar uma reserva

- **Dado** que o cliente possua uma reserva ativa
- **Quando** solicitar uma alteração para um horário disponível
- **Então** o sistema deve atualizar os dados da reserva **e** informar a alteração ao cliente.

### Cancelar uma reserva

- **Dado** que o cliente possua uma reserva ativa
- **Quando** solicitar o cancelamento
- **Então** o sistema deve cancelar a reserva **e** enviar um aviso de cancelamento.

### Atendente registrar uma reserva

- **Dado** que o atendente esteja conectado
- **Quando** informar os dados do cliente e da reserva **e** houver disponibilidade
- **Então** o sistema deve registrar a reserva.

### Registrar a chegada do cliente

- **Dado** que exista uma reserva para aquele dia
- **Quando** o cliente chegar ao restaurante **e** o atendente realizar o check-in
- **Então** o sistema deve atualizar o status da reserva.

### Gerente cadastrar uma mesa

- **Dado** que o gerente esteja conectado
- **Quando** informar os dados de uma nova mesa
- **Então** o sistema deve cadastrar a mesa para uso nas reservas.

### Configurar horários de funcionamento

- **Dado** que o gerente esteja conectado
- **Quando** alterar os horários de funcionamento
- **Então** o sistema deve salvar as novas configurações **e** considerar esses horários nas próximas reservas.

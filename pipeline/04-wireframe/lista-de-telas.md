# Lista de telas e especificação

Etapa 4, partes A e B. Lista aprovada pelo dono em 08/11/2026. Desenhos no Figma, página Wireframe: [Wireframe](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=5-26). Escopo: [scope.md](../03-mvp-scope/scope.md). Cada tela tem uma nota amarela no desenho com os erros e estados vazios.

Formatos: cliente em celular (390 de largura; a altura varia porque a tela rola), atendente em tablet (1024 x 900 e 1024 x 1020) e gerente em computador (1440 x 1000 e 1440 x 1120). A tela 17 entrou na alta fidelidade, junto com a aba Perfil.

## Lista de telas

| # | Tela | Para quem | Para que serve |
|---|---|---|---|
| 1 | Entrar | todos os perfis | login único (pronta da ferramenta); o destino por perfil é regra de negócio, [decisão 6](../decisions/produto/0006-login-por-perfil-e-regra-de-negocio.md) |
| 2 | Cadastro | cliente | criar conta (pronta da ferramenta) |
| 3 | Início | cliente | mostra a próxima reserva e leva a reservar |
| 4 | Buscar mesa | cliente | escolher data, horário e pessoas e ver mesas livres |
| 5 | Confirmar reserva | cliente | conferir o resumo e confirmar |
| 6 | Reserva confirmada | cliente | mostrar a reserva e a mensagem de WhatsApp |
| 7 | Minhas reservas | cliente | listar só as reservas da própria conta |
| 8 | Detalhe da reserva | cliente | ver os dados e escolher alterar ou cancelar |
| 9 | Alterar reserva | cliente | mudar data, horário ou pessoas |
| 10 | Cancelar reserva | cliente | confirmar o cancelamento e mostrar o aviso de WhatsApp |
| 11 | Reservas do dia | atendente | acompanhar o dia, check-in e ausência |
| 12 | Nova reserva para cliente | atendente | registrar reserva de quem liga ou chega |
| 13 | Mesas | gerente | cadastrar, editar e remover mesas |
| 14 | Horários e regras | gerente | definir funcionamento e regras |
| 15 | Usuários | gerente | administrar a equipe |
| 16 | Relatórios | gerente | ver reservas, chegadas, ausências e cancelamentos |
| 17 | Perfil | cliente | dados da conta, canal de aviso e sair ([decisão 10](../decisions/interface/0010-composicao-rica-nas-telas.md)) |

## Especificação (5 pontos por tela)

| # | O que aparece | O que acontece ao clicar | Dado que mostra | Dado que recebe | Quando dá errado |
|---|---|---|---|---|---|
| 1 | Logo, e-mail, senha, botão Entrar | Entrar leva ao início do perfil (cliente: Início; atendente: Reservas do dia; gerente: Mesas); Criar conta leva ao Cadastro | nada | e-mail, senha | "Não foi possível entrar. Confira e tente de novo." |
| 2 | Nome, e-mail, telefone (WhatsApp), senha | Criar conta registra e leva ao Início | nada | nome, e-mail, telefone, senha | mensagem abaixo do campo inválido |
| 3 | Banner, card da próxima reserva, botão Reservar, menu inferior | Ver detalhes abre a 8; Reservar abre a 4 | próxima reserva do cliente | nada | sem reserva: "Você ainda não tem reservas" |
| 4 | Data, horários, pessoas, mesas livres | Ver mesas livres consulta; Escolher abre a 5 | mesas livres que cabem as pessoas | data, horário, pessoas | "Não há mesa livre para esse dia, horário e número de pessoas." |
| 5 | Resumo, aviso do WhatsApp, Confirmar, Voltar | Confirmar salva e abre a 6 | data, horário, pessoas, mesa | confirmação | faixa de erro (mesa tomada, capacidade, horário, conflito); nada é salvo |
| 6 | Check, resumo, mensagem de WhatsApp | Ver minhas reservas abre a 7; Voltar abre a 3 | a reserva criada | nada | envio de WhatsApp simulado no protótipo |
| 7 | Abas Próximas e Passadas, cartões com status | tocar num cartão abre a 8 | reservas só da conta | nada | sem reservas: "Você ainda não tem reservas." |
| 8 | Status, dados, Alterar, Cancelar | Alterar abre a 9; Cancelar abre a 10 | dados da reserva | nada | reserva de outra conta não abre; botões só em reserva ativa e futura |
| 9 | Reserva atual, nova data, horários, pessoas | Salvar alteração atualiza | reserva atual | nova data, horário, pessoas | "Esse horário não está disponível." e a reserva antiga fica igual |
| 10 | Janela "Cancelar esta reserva?" e mensagem de WhatsApp | Cancelar reserva cancela e avisa; Manter fecha | resumo da reserva | confirmação | só reserva própria pode ser cancelada |
| 11 | Data, 4 números, tabela com Check-in e Ausência | Check-in marca chegada; Ausência marca não comparecimento | reservas do dia e status | dia escolhido | Ausência cinza antes da tolerância; check-in só no dia; lista vazia avisa |
| 12 | Busca de cliente, data, horário, pessoas, mesas livres | Registrar reserva salva e avisa por WhatsApp | mesas livres | cliente, data, horário, pessoas | motivo claro (sem mesa, capacidade, horário, conflito); nada é salvo |
| 13 | Tabela de mesas, painel Nova mesa | Editar, Remover, Salvar mesa | mesas, capacidade, reservas futuras | nome e capacidade | remover mesa com reservas futuras é bloqueado com aviso; capacidade inválida não salva |
| 14 | Tabela de dias e horários, regras (tolerância, antecedência, limite, duração) | Salvar configurações | funcionamento e regras atuais | horários e regras | configuração inválida mostra o campo e não salva |
| 15 | Tabela da equipe, painel Novo usuário | Editar, Ativar, Desativar, Salvar usuário | usuários da equipe | nome, e-mail, perfil, senha provisória | dado inválido não salva |
| 16 | Período, 4 números, tabela por dia | escolher o período | totais e dias | período | "Nenhum resultado para esses critérios." |
| 17 | Avatar, nome, números de visitas e lista de opções | cada linha abre um ajuste; Sair encerra a sessão | dados da conta | nada | sem reservas, os números mostram zero |

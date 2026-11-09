---
numero: 6
titulo: Login por perfil é regra de negócio
data: 2026-11-08
estado: em-vigor
links: []
substitui: []
substituida_por: []
relacionadas: []
---

# 6. Login por perfil é regra de negócio

**Estado:** em vigor.

## Decisão

Existe uma única tela de login para os três perfis (cliente, atendente e gerente). Depois de entrar, o sistema identifica o perfil da conta e leva a pessoa ao início certo: cliente ao Início do cliente, atendente a Reservas do dia, gerente a Mesas. Esse redirecionamento é regra de negócio e não ganha telas próprias no protótipo. O cadastro pela própria pessoa existe só para o cliente; atendente e gerente são criados pelo gerente na tela Usuários.

## Por quê

O levantamento da turma diz que o login libera o acesso "conforme o perfil do usuário" e não pede telas separadas por perfil. Desenhar três logins repetiria a mesma tela sem informação nova.

# ReserveFácil

![Capa do ReserveFácil](docs/img/capa.jpg)

[![Release](https://img.shields.io/github/v/release/duribeiro/reserve-facil)](https://github.com/duribeiro/reserve-facil/releases)
[![CI](https://github.com/duribeiro/reserve-facil/actions/workflows/ci.yml/badge.svg)](https://github.com/duribeiro/reserve-facil/actions/workflows/ci.yml)
[![License](https://img.shields.io/github/license/duribeiro/reserve-facil)](LICENSE)
[![Dependabot](https://img.shields.io/badge/dependabot-enabled-025e8c?logo=dependabot)](.github/dependabot.yml)
[![Conventional Commits](https://img.shields.io/badge/commits-conventional-fe5196)](https://www.conventionalcommits.org/pt-br/v1.0.0/)

Sistema de reserva de mesas para restaurantes: o cliente reserva, o atendente acompanha o dia e o gerente configura. Cada restaurante contrata o sistema com a própria marca. Neste protótipo, a marca é o **Ulivo**, um restaurante fictício.

Este repositório é um trabalho da faculdade e termina no protótipo de alta fidelidade ([decisão 4](pipeline/decisions/processo-de-trabalho/0004-projeto-termina-no-prototipo-de-alta-fidelidade.md)). O sistema não foi construído.

## Abrir no Figma

| O quê | Link |
|---|---|
| Capa | [Abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=98-4378) |
| Alta fidelidade, 17 telas | [Abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=27-16) |
| Apresentação, 12 slides | [Abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=95-167) |
| Design system | [Abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=22-2) |
| Wireframe | [Abrir](https://www.figma.com/design/HXJrsNhPSf2iC8GyJBqwi2/ReserveFacil?node-id=5-26) |

## O problema

Restaurantes que recebem pedidos por telefone, mensagem ou no balcão sofrem com reservas duplicadas, informação perdida e dificuldade para alterar ou cancelar. O ReserveFácil reúne tudo num sistema só.

## As telas

**Cliente, no celular**

![Jornada do cliente em cinco telas](docs/img/jornada-cliente.jpg)

**Atendente, no tablet**

![Telas do atendente](docs/img/telas-atendente.jpg)

**Gerente, no computador**

![Telas do gerente](docs/img/telas-gerente.jpg)

## Casos de uso

Diagramas originais do levantamento de requisitos ([texto completo](docs/requisitos-reservefacil.md)).

![Casos de uso por área](docs/img/diagrama-casos-de-uso-por-grupo.jpg)

![Casos de uso por ator](docs/img/diagrama-casos-de-uso-por-ator.jpg)

## Design

Creme e verde, com as cores medidas nas referências do café ([decisão 12](pipeline/decisions/interface/0012-creme-e-verde-medidos-na-referencia-do-cafe.md)). Detalhes em [docs/design-system.md](docs/design-system.md).

![Cores do produto](docs/img/cores.jpg)

![Design system](docs/img/design-system.jpg)

## Apresentação

![Primeiro slide da apresentação](docs/img/apresentacao-capa.jpg)

São 12 slides para apresentar o produto, com o roteiro de fala em [apresentacao.md](pipeline/04e-high-fidelity/apresentacao.md).

## Próxima versão

O que ficou para depois está em [proxima-versao.md](pipeline/04e-high-fidelity/proxima-versao.md).

## Como trabalhar neste projeto

- Regras do agente e do projeto: [AGENTS.md](AGENTS.md).
- Como uma mudança chega na `main`: [CONTRIBUTING.md](CONTRIBUTING.md).
- Onde o trabalho parou: [pipeline/STATE.md](pipeline/STATE.md).
- Decisões tomadas: [pipeline/decisions](pipeline/decisions/README.md).
- Histórico de versões: [CHANGELOG.md](CHANGELOG.md).

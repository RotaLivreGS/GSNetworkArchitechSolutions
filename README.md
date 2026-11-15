# Rota Livre – Network Architect Solutions

Global Solution 2026.2 · CitizenTech · Engenharia de Software · FIAP

## Ficha da CitizenTech

| | |
|---|---|
| **Nome da CitizenTech** | Rota Livre |
| **Cidade e bairro** | São Paulo – Bela Vista (entorno da Av. Paulista, 1106) |
| **Cidadão beneficiado** | Pessoas em cadeira de rodas, idosos, pessoas com mobilidade reduzida e quem circula com carrinho de bebê |
| **Problema, em uma frase** | Os apps de mapa mostram o caminho mais rápido, mas não avisam se há degrau, calçada quebrada ou falta de rampa no trajeto de quem não consegue passar por eles. |
| **Como funciona** | O usuário informa o destino e o seu perfil de mobilidade, e o app calcula a rota que evita as barreiras relatadas e prioriza rampas. As barreiras são relatadas pela comunidade e validadas por uma equipe de moderação. |
| **O que cada parte faz** | **App:** planeja a rota pelo perfil de mobilidade. **Servidor:** guarda os relatos e calcula as rotas. **Moderação:** valida os relatos. **Central Rota Livre:** ponto físico com totens e Wi-Fi para quem não tem celular ou dados móveis. |
| **Link do repositório** | https://github.com/RotaLivreGS/GSNetworkArchitechSolutions |
| **Indicador de impacto** | Barreiras relatadas e validadas; percentual do trajeto sem barreiras na rota sugerida, comparado à rota mais curta; atendimentos realizados na Central |
| **ODS conectados** | ODS 11 (metas 11.2 e 11.7), ODS 10 (meta 10.2) e ODS 9 (meta 9.c) |

## Sobre esta entrega

Parte de **Network Architect Solutions**: a rede da **Central Rota Livre**, o ponto físico de atendimento do projeto, montada no Cisco Packet Tracer.

A Central tem duas redes ligadas por um roteador:

- **Atendimento** (`192.168.137.0/24`): totens para o cidadão e Wi-Fi com WPA2 para usar o app;
- **Equipe** (`10.0.137.0/24`): servidor do Rota Livre e estação de moderação.

Número da equipe adotado: **X = 137**.

## Arquivos

| Arquivo | Conteúdo |
|---|---|
| `GS_NetworkArchitect_RotaLivre_Equipe137.pkt` | Rede montada no Cisco Packet Tracer |
| `GS_NetworkArchitect_RotaLivre_Equipe137.pdf` | Documentação: Ficha, topologia, endereçamento, testes, análise em camadas e respostas às perguntas |

Para abrir a rede, use o **Cisco Packet Tracer** (feito na versão 9.0.1).

## Endereçamento

| Dispositivo | Interface | IP | Máscara | Gateway |
|---|---|---|---|---|
| RotaLivre-GW | G0/0 | 192.168.137.1 | 255.255.255.0 (/24) | – |
| RotaLivre-GW | G0/1 | 10.0.137.1 | 255.255.255.0 (/24) | – |
| SW-Atendimento | Vlan1 | 192.168.137.2 | 255.255.255.0 (/24) | 192.168.137.1 |
| SW-Equipe | Vlan1 | 10.0.137.2 | 255.255.255.0 (/24) | 10.0.137.1 |
| Totem1 | Fa0 | 192.168.137.10 | 255.255.255.0 (/24) | 192.168.137.1 |
| Totem2 | Fa0 | 192.168.137.11 | 255.255.255.0 (/24) | 192.168.137.1 |
| Notebook-WiFi | Wireless0 | 192.168.137.12 | 255.255.255.0 (/24) | 192.168.137.1 |
| Servidor-RotaLivre | Fa0 | 10.0.137.10 | 255.255.255.0 (/24) | 10.0.137.1 |
| PC-Moderacao | Fa0 | 10.0.137.11 | 255.255.255.0 (/24) | 10.0.137.1 |

Wi-Fi: SSID `RotaLivre-Atendimento`, WPA2-PSK. O AP-Atendimento (AccessPoint-PT) não tem configuração de IP no Packet Tracer.

## Integrantes

- Igor Davi Avelar Rosa Cesário – RM568163
- Patrick Castro Quintana – RM575906
- Rafael Menezes Viana – RM576753

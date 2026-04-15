---
title: "Proposta de TCC - Avaliação do Desempenho de LLMs na Geração de Regras de Firewall"
date: 2026-04-14 15:44:00 +/-0300
categories: [TCC, network security, LLM]
description: "Proposta inicial do meu Trabalho de Conclusão de Curso."
---

**Orientador**: Daniel Macedo Batista

## Resumo

A segurança de redes de computadores é algo indispensável em organizações nos dias atuais e, com o surgimento crescente de novos vetores de ataques, é cada vez mais possível que uma rede que esteja protegida atualmente pode não ser capaz de impedir um ataque de dia zero. Tendo em vista a necessidade de mais agilidade na resposta a incidente exigida nesse cenário, ferramentas de Inteligência Artificial, especialmente LLMs, podem ser úteis ao auxiliar administradores de sistemas a criarem regras em um firewall que impeçam um ataque de ter sucesso. Em um cenário ideal, no momento que alguma vulnerabilidade seria descoberta, o administrador informaria suas características para uma LLM, junto com as particularidades do seu ambiente de rede principalmente em termos de firewall, e receberia como retorno, as regras que deveriam ser colocadas nesse firewall para mitigar o ataque. Este TCC tem por objetivo estudar se é realista usar tecnologias atuais para essa tarefa, avaliando duas LLMs (Gemini e chatGPT) na tarefa de criarem regras para protegerem uma rede protegida por três firewalls diferentes (iptables, nftables e pfSense). Como resultado, será avaliada tanto a explicação fornecida pela LLM, quanto a eficácia da regra sugerida. Adicionalmente, A interação com os diferentes firewalls também será avaliada.

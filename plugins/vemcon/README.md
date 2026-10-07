# VemCon

Plugin da [VemCon](https://vemcon.com.br) para Claude, ChatGPT e Codex. Ele liga
o assistente ao catálogo de cartas de consórcio contempladas da VemCon para
buscar cartas, ver detalhes e simular o custo das parcelas restantes por
conversa. Com a conta conectada, mostra também suas cartas monitoradas e seus
alertas.

Exemplos do que você pode pedir:

- "Quais cartas de imóvel com crédito acima de R$ 300 mil estão disponíveis?"
- "Mostre os detalhes da carta IMV-K7P2QX."
- "Simule o custo total dessa carta com correção de 6% ao ano."
- "Quais cartas estou monitorando?"

## O que vem no plugin

- **Conector MCP** apontando para
  `https://apftuqncwgobmmuqmqrq.supabase.co/functions/v1/mcp`.
- **Skill `cartas-contempladas`**, que orienta o assistente a usar os filtros do
  catálogo, a tratar a entrada e o status da carta e a seguir o vocabulário da
  VemCon (reserva, não proposta).

O plugin não executa código na sua máquina. Ele apenas declara o servidor
remoto e a skill. Todas as operações são somente leitura: o plugin não reserva
cartas nem gera pagamentos. A reserva é feita no site.

## Conta e acesso

A busca, os detalhes e a simulação funcionam sem conta. Para ver o valor de
entrada, as cartas monitoradas e os alertas, conecte sua conta VemCon: o
assistente abre a tela de autorização da VemCon (OAuth 2.1 com PKCE), em que
você confere as permissões solicitadas e aprova ou nega. Para encerrar o
vínculo, acesse https://vemcon.com.br/oauth/consent e escolha **Desvincular**.

## Dados e privacidade

O assistente envia ao servidor da VemCon apenas os dados da consulta realizada
(filtros ou código da carta). As respostas não incluem CPF, documentos nem
renda. Nenhum dado é enviado a terceiros pelo plugin.

- Política de privacidade: https://vemcon.com.br/termos?secao=politica-de-privacidade
- Termos de uso: https://vemcon.com.br/termos
- Suporte: contato@vemcon.com.br

A simulação é informativa e não representa aprovação de crédito. A análise de
crédito e a cessão são feitas pela administradora do consórcio, que pode cobrar
taxas próprias, pagas diretamente a ela.

## Instalação manual

Claude Code:

```bash
claude plugin marketplace add clustermarketing/vemcon-plugin
claude plugin install vemcon@vemcon
```

Codex:

```bash
codex plugin marketplace add clustermarketing/vemcon-plugin
codex plugin add vemcon@vemcon
```

## Licença

MIT. O plugin é aberto; o uso da VemCon segue os termos da plataforma.

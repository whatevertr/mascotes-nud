# nud-personagens: os personagens da marca NUD by Whatevertr

Os personagens da marca, publicados como uma **skill de agente**: o alien (mascote, representa a autora), a Tríade (TARS a Pensadora, ROCKY a Gerente, CASE a Trabalhadora) e o marcador vivo (o `[·]` como criatura de ímã, em quatro estados). A skill diz qual arquivo usar, em que tamanho, como escalar sem quebrar a grade de pixel, o que descaracteriza cada personagem e o que cada um significa quando aparece.

## A skill

A skill instalável está em [`nud-personagens/`](nud-personagens/). Copie a pasta inteira para o diretório de skills da sua ferramenta (`~/.codex/skills/` no Codex, `~/.claude/skills/` no Claude Code) ou aponte o agente para ela.

| Arquivo | O que é |
|---|---|
| `nud-personagens/SKILL.md` | o roteador: quem é quem, qual arquivo mandar, as regras duras |
| `nud-personagens/references/` | alien, tríade, marcador vivo, escala (tamanhos) e entrega (formato e destino) |
| `nud-personagens/assets/` | os SVG-mestre de cada personagem, noite e dia |

A lei visual da marca (paleta, tipografia, estados, componentes) mora na skill `estilo-nud`, em repositório próprio. Esta aqui só cuida dos personagens.

Licença: ver `LICENSE`. Thainá Ramos (Nud by Whatevertr).

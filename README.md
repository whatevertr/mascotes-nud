# mascotes: os mascotes da NUD by Whatevertr para o Codex

Cinco mascotes animados, prontos para instalar no Codex (OpenAI) como *animal de estimação*: o **alien** (mascote da marca), a Tríade do Método Constelação, **TARS** (a Pensadora), **ROCKY** (a Gerente) e **CASE** (a Trabalhadora), e o **marcador vivo** (o `[·]` como criatura de ímã). Pixel art, estado noite.

<!-- imagem de apresentação entra aqui -->

## Instalar no Codex

Cada mascote é uma pasta em [`pets/`](pets/) com dois arquivos: `pet.json` (nome e descrição) e `spritesheet.webp` (a animação).

1. Baixe este repositório (botão **Code → Download ZIP**) e descompacte.
2. Copie as pastas de `pets/` que quiser para a pasta de mascotes do Codex no seu computador: `C:\Users\<seu usuário>\.codex\pets\` no Windows, `~/.codex/pets/` no Mac e Linux. Se a pasta `pets` não existir, crie.
3. Feche e abra o Codex. Em **Configurações → Animais de estimação → Personalizar**, escolha o mascote. `Alt+Win+P` mostra e esconde o mascote na tela.

Os prints em [`prints/`](prints/) mostram como cada um aparece na tela de mascotes do Codex.

| Pasta | Mascote |
|---|---|
| `pets/nud-alien-noite/` | o alien, mascote da marca |
| `pets/nud-tars-noite/` | TARS, a Pensadora |
| `pets/nud-rocky-noite/` | ROCKY, a Gerente |
| `pets/nud-case-noite/` | CASE, a Trabalhadora |
| `pets/nud-marcador-vivo-noite/` | o marcador vivo `[·]` |

## A skill dos personagens

Para uma instância de IA usar os personagens em peças (avatar, favicon, sticker, slide, post) sem descaracterizar nenhum, a skill [`nud-personagens/`](nud-personagens/) diz qual arquivo mandar, em que tamanho, como escalar e o que cada um significa quando aparece. Copie a pasta para o diretório de skills da sua ferramenta (`~/.codex/skills/` no Codex, `~/.claude/skills/` no Claude Code). Os SVG-mestre de cada personagem, noite e dia, estão em `nud-personagens/assets/`.

A lei visual da marca (paleta, tipografia, estados) mora na skill `estilo-nud`, em repositório próprio.

## Quem são

O alien representa a autora. TARS, ROCKY e CASE representam as três funções do [Método Constelação](https://github.com/whatevertr/constellation-method): pensar, conduzir e executar. O marcador `[·]` é a assinatura da marca; vivo, ele vira criatura com quatro estados (descansado, feliz, triste, vidrado).

Licença: ver `LICENSE`. Thainá Ramos (Nud by Whatevertr).

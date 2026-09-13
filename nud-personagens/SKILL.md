---
name: nud-personagens
description: Entrega e uso dos personagens da marca NUD by Whatevertr — o alien (mascote da marca, representa a autora), as três da Tríade (TARS a Pensadora, ROCKY a Gerente, CASE a Trabalhadora) e o marcador vivo (o [·] como criatura de ímã em quatro estados). Diz qual arquivo mandar, em que tamanho, como escalar sem quebrar a grade de pixel, o que descaracteriza cada personagem, os números de animação de cada um e o que cada um significa quando aparece. Use SEMPRE que a autora pedir para "usar a TARS", "põe a Rocky", "manda o mascote", "quero o alien dormindo", "me dá o favicon", "exporta o marcador", "que tamanho eu uso", "o arquivo do personagem", ou quando uma peça precisar de um personagem da marca — avatar, favicon, sticker, overlay, slide, post, ilustração. Para a lei visual da marca (paleta, tipografia, estados, componentes), use a skill estilo-nud.
license: LicenseRef-Proprietary
metadata:
  author: Thainá Ramos (Nud by Whatevertr)
  version: 1.0
---

# Personagens NUD — quem entrega o quê

**Versão 1.0 · 16.08.2026.** Esta skill nasce de três kits soltos (`_kits_entrega/alien`, `_kits_entrega/mascotes-triade`, `_kits_entrega/marcador-vivo`) que guardavam regra que instância nenhuma lia.

## A divisão com a `estilo-nud` — leia isto antes de tudo

> **A `estilo-nud` diz quem os personagens SÃO. Esta diz como USAR e ENTREGAR.**
>
> Se você quer saber quem é o alien, o que a Tríade representa ou por que o marcador é o logo, **não é aqui**: é a seção "O elenco" da `estilo-nud`. Regra que já está na lei não se repete aqui — se repetisse, um dia as duas divergiriam e ninguém saberia qual vale.

O que **está** na lei e vale sem eu repetir: a paleta · o posto do logo (é do marcador `[·]`) · o avatar padrão (é o marcador; os outros só por pedido explícito) · o pixel existir no dia e na noite · a regra de movimento (**pula e respira, volta sempre ao ponto de origem; não viaja**).

## O elenco em uma linha cada

| Personagem | O que é | Arquivo-mestre |
|---|---|---|
| **alien** | mascote da marca, representa a autora | `assets/nud-mascote-pixel.svg` · vetor: `assets/mascote.svg` |
| **TARS** | a Pensadora — cérebro-nebulosa | `assets/nud-tars-pixel.svg` |
| **ROCKY** | a Gerente — prumo com nível | `assets/nud-rocky-pixel.svg` |
| **CASE** | a Trabalhadora — vaga-lume | `assets/nud-case-pixel.svg` |
| **marcador vivo** | o `[·]` como criatura de ímã, 4 estados | `assets/nud-marcador-vivo-*.svg` |
| **marcador** (logo) | a assinatura — não é personagem, mas mora aqui como arquivo | `assets/nud-marcador-pixel.svg` · vetor: `assets/marcador.svg` |

## O mapa — onde está cada coisa

| Vou fazer | Leia |
|---|---|
| Usar o alien — anatomia, estados, o que o descaracteriza | `references/alien.md` |
| Usar TARS, ROCKY ou CASE | `references/triade.md` |
| Usar o marcador vivo — os quatro estados e a física | `references/marcador-vivo.md` |
| **Escalar, redimensionar, exportar em outro tamanho** | `references/escala.md` — **leia antes de tocar em tamanho** |
| Saber qual arquivo mandar, em que formato, para que uso | `references/entrega.md` |
| Paleta, tipografia, componentes, a lei | skill `estilo-nud` |

## As cinco regras que resolvem quase tudo

1. **Escala só em múltiplo inteiro**, com vizinho mais próximo. `×2 ×4 ×8 ×16`. Nunca 1,5×, nunca "200px a partir de 32". É **a regra que mais se quebra** e a que mais estraga — em escala fracionada uns pixels viram 6 e outros 7, a unidade da grade deixa de ser constante, e a grade racha. Detalhes e tabelas em `references/escala.md`. **[NORMA TÉCNICA]**
2. **Um estado por tela.** Não se mostra o mesmo personagem em dois estados na mesma peça — vira folha de sprite, não presença.
3. **Não se desenha personagem novo nem pose nova.** O que existe está em `assets/`. Se a pose que você precisa não existe, **diga que não existe** em vez de improvisar: cada personagem tem uma anatomia fechada, e um desenho aproximado descaracteriza mais do que ajuda.
4. **O favicon é do marcador.** Nem alien, nem Tríade, nem marcador vivo entram em favicon — o favicon é o posto do logo, e o posto é do marcador `[·]`. Avatar é outra coisa: aí os outros entram, por pedido explícito.
5. **Sem os elementos-assinatura, não é o personagem.** A antena laranja do alien, os polos do marcador, o olho que o próprio corpo produz de cada uma da Tríade. Some com isso e sobrou um desenho qualquer.

## O que existe hoje — e o que não existe

**Existe:** os 16 SVG-mestre em `assets/`, os **14 mestres-dia** produzidos em 16.08.2026 (mesmos nomes com sufixo `-dia`), e as exportações em PNG no kit de entrega (ver `references/entrega.md`).

**O dia tem arquivo.** Todo personagem em pixel tem versão dia — alien acordado e dormindo, marcador, lockup, os quatro estados do marcador vivo, e TARS, ROCKY e CASE (`assets/nud-tars-pixel-dia.svg`, `nud-rocky-pixel-dia.svg`, `nud-case-pixel-dia.svg`). **Peça de dia leva a Tríade e o marcador vivo normalmente**, pelo arquivo `-dia`. `[NORMA]` **Nunca leve um sprite da noite para o papel/fundo do dia** — as cores da noite reprovam contraste sobre bege — e **nunca recolora um sprite da noite no olho**: a receita de tradução é `estilo-nud/references/traducao-dia.md`.

**Não existe, e é pendência declarada:**

- **A Tríade tem uma pose só** cada, contra duas do alien e quatro do marcador vivo.
- **O marcador de assinatura não tem PNG em tamanho nenhum**, enquanto o marcador vivo tem vinte.
- **O lockup existe como um único SVG**, sem kit e sem exportação.

Quando faltar arquivo, **avise em vez de improvisar** — improviso em personagem é o jeito mais rápido de a marca perder a cara.

## Teste de aceitação

1. A escala é múltiplo inteiro, e o redimensionamento foi feito com vizinho mais próximo? *Conferido, não presumido.* **[NORMA TÉCNICA]**
2. O personagem está acima do piso de tamanho dele — os detalhes que o definem sobreviveram?
3. Um estado só na peça?
4. Se é favicon: é o marcador?
5. Se é peça de dia: o arquivo é de dia mesmo, ou você recolorou um sprite de noite? *Recolorir é [NORMA] proibido.*
6. Os elementos-assinatura estão lá — antena, polos, o olho de cada corpo?
7. Tapando o resto da peça, dá pra dizer qual personagem é?

---
© 2026 Thainá Ramos (Nud by Whatevertr) · **Todos os direitos reservados.** Identidade de marca proprietária — **não licenciada para reuso, cópia ou adaptação**. Ver `LICENSE`.

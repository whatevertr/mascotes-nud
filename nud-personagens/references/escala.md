# Escala — a regra que mais se quebra

O kit da Tríade dá nome a esta seção: **"a regra que mais se quebra: escala inteira"**. Este arquivo é a versão completa dela. Leia antes de tocar em qualquer tamanho.

---

## A regra

> **Pixel art só escala em múltiplo inteiro — ×2, ×4, ×8, ×16 — e sempre com vizinho mais próximo.** `[NORMA TÉCNICA]`

Duas metades, e as duas reprovam sozinhas:

1. **O fator é inteiro.** 1× 2× 3× 4× 6× 8× 12× 16×. Nunca 1,5×. Nunca "200 px porque coube na caixa".
2. **A reamostragem é vizinho mais próximo.** `image-rendering: pixelated` na web; *Nearest Neighbor* ou *Hard edges* na ferramenta. **Nunca bicúbica, nunca bilinear.**

O princípio já está na lei (`estilo-nud` → `estilo-nud/references/manual.md` §D.12, "As regras da grade"). **O que só existe aqui é o operacional:** as três tabelas de tamanhos seguros, a instrução de ferramenta e a folga com número.

---

## Por que — em números

**Em escala fracionada, a unidade da grade deixa de ser constante dentro da mesma imagem.**

Um sprite de 32 px levado a 200 px pede 6,25 px por pixel de grade. Como o raster não tem meio pixel, o software distribui a sobra: **uns pixels saem com 6 px, outros com 7.** A grade racha — quadrados de dois tamanhos convivendo lado a lado na mesma peça. O olho lê isso como desenho torto, não como imagem grande.

O mesmo em 1,5×: metade dos pixels vira 1, metade vira 2.

E se a interpolação for **bicúbica ou bilinear**, o problema muda de natureza: o software inventa valores intermediários entre os quadrados e **o pixel borra**. Some a aresta dura, que é a única coisa que faz pixel art ser pixel art.

**Comparação mínima:**

| Alvo a partir de 32 | Fator | Veredito |
|---|---|---|
| 192 px | 6× | **serve** — 6 px por pixel de grade, todos iguais |
| 200 px | 6,25× | **quebra** — uns 6, outros 7 |
| 48 px | 1,5× | **quebra** — uns 1, outros 2 |

---

## Como se cumpre

**Na web:**

```css
img { image-rendering: pixelated; width: 192px; } /* 6 × 32 = OK */
```

**Na ferramenta de desenho:** interpolação em **Nearest Neighbor** (ou **Hard edges**) no **Figma**, no **Photoshop** e no **Illustrator**. Nunca bicúbica, nunca bilinear.

> **Lacuna:** o kit nomeia as três ferramentas e a opção, mas **não diz onde a opção fica em cada uma** — não há caminho de menu documentado. Quem escalar confere na própria ferramenta antes de exportar. Esta é a única linha de toda a documentação da marca que fala de ferramenta de desenho.

---

## As três tabelas de tamanhos seguros

**Elas não são iguais entre si.** Não presuma que o número seguro de uma vale para outra.

### Tríade — TARS, ROCKY, CASE · base 32×32

| Fator | ×1 | ×2 | ×3 | ×4 | ×5 | ×6 | ×7 | ×8 | ×10 | ×12 | ×16 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **px** | 32 | 64 | 96 | 128 | 160 | 192 | **224** | 256 | **320** | **384** | 512 |

### Alien — acordado e dormindo · base 32×32

| Fator | ×1 | ×2 | ×3 | ×4 | ×5 | ×6 | ×8 | ×16 |
|---|---|---|---|---|---|---|---|---|
| **px** | 32 | 64 | 96 | 128 | 160 | 192 | 256 | 512 |

> **Lacuna registrada — não invente motivo.** A tabela do alien **não traz 224, 320 nem 384**, que estão na da Tríade. Os três são múltiplos inteiros de 32 e, pela regra, deveriam servir. **O kit não diz por quê.** Como está escrito, um leitor conclui que 224 px é seguro para a CASE e não para o alien. Até alguém decidir: se precisar de 224, 320 ou 384 no alien, **pergunte** em vez de assumir qualquer um dos dois lados.

### Marcador vivo — os quatro estados · base **24×16** (retangular)

| Fator | ×2 | ×3 | ×4 | ×6 | ×8 | ×16 |
|---|---|---|---|---|---|---|
| **px** | 48×32 | 72×48 | 96×64 | 144×96 | 192×128 | 384×256 |

A base é **24×16, não quadrada** — a série do marcador vivo **não coincide** com a série 32 das mascotes. Não misture as duas tabelas. A base 24×16 vale para os quatro estados, e é por isso que trocar de estado não move nada em volta.

**Tira de animação:** 4 quadros de **192×128** numa faixa de **768×128** (8× da base). Detalhes de `steps()` em `marcador-vivo.md`.

> **Tamanho seguro ≠ arquivo existente.** A tabela diz o que é *legal*; não diz o que já foi exportado. O que existe em PNG hoje está em `entrega.md`. Se o tamanho seguro que você quer não tem PNG, o caminho é o SVG-mestre.

---

## Folga

**4 pixels da grade em volta = 12,5% do lado.** `[CONV]`

| Tamanho final | Folga |
|---|---|
| 32 px | 4 px |
| 128 px | 16 px |
| 256 px | **32 px** |
| 512 px | 64 px |

- Os arquivos de `avatar/` **já vêm com a folga aplicada** — não some outra por cima.
- **No alien: a antena entra na medida.** A folga é a partir da bolinha, não do domo. **Não corte a bolinha.**
- **No marcador vivo o kit não fixa folga.**

---

## O piso, personagem por personagem

Escalar para baixo tem chão. `[NORMA TÉCNICA]` Abaixo do piso a forma **deixa de existir** — não fica pequena, fica errada:

| Personagem | Piso | O que morre abaixo dele |
|---|---|---|
| **CASE** | 32 px | os **olhos compostos** somem |
| **ROCKY** | 32 px | a **bolha** some |
| **TARS** | 32 px | o kit não diz o que ela perde |
| **alien** | 32 px | os **lobos da saia viram serrote** e a **bolinha da antena some** |
| **marcador vivo** | 24×16 | no `triste` o quadrado tem 2 px de lado — **abaixo da base ele desaparece** |
| **marcador (assinatura)** | 16×16 | é lei: nasceu em 16 px, não é redução — ver `estilo-nud` |

Repare no padrão: **o que morre primeiro é sempre o elemento-assinatura.** O olho que o corpo produz, a antena laranja, o quadrado entre os polos. Passar do piso não deixa a imagem pequena demais — deixa o personagem irreconhecível.

**Para 16 px não se reduz mascote nem marcador vivo: usa-se o marcador `[·]`**, que foi desenhado nesse tamanho (lei).

---

## Teste

1. O fator é inteiro? Faça a conta: **alvo ÷ base**. Se não der número redondo, o tamanho está errado.
2. O número alvo está na tabela **do personagem certo** — 32 para mascotes, 24×16 para o marcador vivo?
3. A reamostragem foi **vizinho mais próximo / Hard edges**, conferido na ferramenta e não presumido? Nada de bicúbica ou bilinear.
4. Na web, o `image-rendering: pixelated` está aplicado no elemento que recebe o tamanho?
5. O tamanho final está **acima do piso** e o elemento-assinatura sobreviveu — olho, antena, quadrado?
6. A folga é 4 px de grade (12,5%)? Se for `avatar/`, você **não** somou folga em cima da que já vem?
7. É 224, 320 ou 384 **no alien**? Então pare: o kit não lista esses e não diz por quê — pergunte.

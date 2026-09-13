# O alien — anatomia, poses e o que o descaracteriza

Mascote da marca. Quem ele é, o que representa e a regra geral de movimento estão na `estilo-nud`. Aqui está o desenho em números e o que fazer com ele.

Arquivos-mestre: `assets/nud-mascote-pixel.svg` · `assets/nud-mascote-dormindo-pixel.svg` · vetor `assets/mascote.svg` · `assets/mascote-dormindo.svg`.

**No dia, os mesmos com sufixo `-dia`:** `assets/nud-mascote-pixel-dia.svg` · `assets/nud-mascote-dormindo-pixel-dia.svg` · vetor `assets/mascote-dia.svg` · `assets/mascote-dormindo-dia.svg`. Receita de tradução: `estilo-nud/references/traducao-dia.md`.

---

## Proveniência — por que os números são estes

Portado de `mascote.svg` e `mascote-dormindo.svg` (viewBox 64×64) por **redução exata de coordenadas pela metade**: 64 → 32. **Não é redesenho.** Silhueta, proporções e as três cores são as do original.

A **v1 do kit foi descartada**: era um chute feito sem o arquivo na frente. **[NORMA]** pose de alien não se deduz de memória — sai do vetor ou não sai.

O **vetorial continua sendo o de uso corrente**. O pixel é para quando o alien precisa estar na mesma grade da Tríade.

---

## As quatro coisas que o definem

| # | Peça | Medida | Cor |
|---|---|---|---|
| 1 | Domo com barra ondulada — **três lobos na base (a saia)** | é a silhueta; o que o torna reconhecível a 32 px | — |
| 2 | Contorno grosso | **2 px na grade** (= `stroke-width: 5` do original em 64) | `#C8A2FF` |
| 3 | Barriga | lisa | `#0E0C14` |
| 4 | Olhos — dois pontos, **não brancos** | **3 px** cada, **3 px de vão**, abaixo do meio do domo | `#C8A2FF` |
| 5 | Antena | haste **2 px** + bola **4 px** | `#FF8A5C` |

A antena é o **único laranja dele** e a assinatura da forma.

> **Teste de identidade: sem antena, não é o mascote.**

---

## Pose é arquivo. Estado é comportamento. Não são a mesma lista.

Fonte de confusão recorrente — leia antes de prometer arquivo.

| | Quantas | Quais | O que é |
|---|---|---|---|
| **Poses de arquivo** (kit) | **2** | `acordado` · `dormindo` | SVG que existe em `assets/`. É o que dá para entregar. |
| **Estados de comportamento** (lei) | **5** | `respira` · `para` · `feliz` · `dorme` · `some` | Como o mesmo desenho se comporta em tela. Ver `estilo-nud`. |

**Não se contradizem** — são planos diferentes. Os cinco estados da lei são comportamento rodando sobre as duas poses que existem em arquivo. O mapeamento estado→pose **o kit não diz**; o único evidente é `dorme` → pose `dormindo`. **[NORMA]** quando pedirem "o alien comentando" ou "o alien sumindo" como **arquivo**, a resposta é que **não existe** — o kit declara essas duas poses como pendência.

### O que muda entre as duas poses

| Pose | Olhos | Antena |
|---|---|---|
| `acordado` | dois pontos de 3 px | ereta, para cima |
| `dormindo` | dois traços horizontais | **tombada 52°**, caída para a direita (mesma rotação do original, `rotate(52 32 22)`) |

**O corpo não muda entre elas — só olhos e antena.** **[NORMA]** não misturar: olho aberto com antena tombada, ou o inverso.

---

## Números de animação

| Pose | O que faz | Números do kit |
|---|---|---|
| `acordado` | pulsa e respira, sobe e volta ao ponto de origem, sem trajetória | ciclo de **~4 s** |
| `dormindo` | respira; a antena tombada fica parada | escala **1,00 → 1,02**, ciclo de **~9 s** |

**[PREF]** só no kit: a antena pode balançar **1 px atrasada** em relação ao corpo, como uma mola.

> **O estado dura um ciclo inteiro.** O ciclo de respiração do sono é de **~9 s**, e a autora decidiu em 16.08.2026 que **o estado é que estica para caber** — `dorme` passou de ~8,5 s para **~9 s**. Ele não acorda mais no meio de uma respirada.

---

## O `some` — corte seco

**Decidido pela autora em 16.08.2026: corte seco.** O kit tinha razão e a lei foi alinhada a ele.

> **"Saída por corte seco, nunca por fade. Ele desaparece, não desbota."**

Os **~3 s** da lei nunca foram a transição — são o **tempo que ele fica fora** antes de voltar. A transição não tem duração: é um quadro com ele, o próximo sem. Volta do mesmo jeito, no mesmo lugar. `[CONV]`

---

## O que o descaracteriza — **[NORMA]**

- **Não tirar a antena.** Única coisa laranja, única insubstituível.
- **Não recolorir a antena para violeta**, nem o contorno para laranja.
- **Não preencher a barriga.** `#0E0C14` liso — sem textura, sem pontilhado.
- **Não dar boca, nariz, braços ou pernas.** Dois olhos, um contorno, uma antena.
- **Não alisar a saia.** Os três lobos são a forma; base reta é outro personagem.
- **Não misturar os estados.**

---

## Piso de tamanho

**32 px.** Abaixo disso **os lobos da saia viram serrote e a bolinha da antena some** — some exatamente o que o identifica.

**Folga: 4 px da grade em volta, e a antena entra na medida — não corte a bolinha.** Tamanhos seguros e como redimensionar: `escala.md`.

**[NORMA]** Fundo: nunca branco, nunca foto. Para o sprite da **noite**, as superfícies válidas são `#22202A` e `#06050B`; o mestre `-dia` vai sobre a caixa `#F4EBE2` ou o papel `#E7DCD0` — *o contorno é o que separa a barriga do fundo*.

**[NORMA]** **Nunca leve o sprite da noite para o papel/fundo do dia** — as cores da noite estão cravadas no arquivo e reprovam contraste sobre bege. E **nunca recolora o sprite da noite no olho**: use o `-dia`, ou traduza pela receita (`estilo-nud/references/traducao-dia.md`).

---

## Favicon — uma linha, para não repetir o engano

**Favicon é do marcador `[·]`**, e o alien nunca ocupa esse posto (a lei e o kit do alien concordam). As exportações pequenas de mascote — inclusive a pasta `favicon/` que o kit da Tríade entrega — servem a **avatar e sticker**, não a favicon; o nome da pasta é que está errado.

---

## Teste

1. A antena está lá, laranja, com a bolinha inteira e sem corte?
2. Olhos e antena batem com a **mesma** pose — sem olho aberto com antena caída?
3. A saia tem os três lobos, e a peça está a 32 px ou mais?
4. A barriga está lisa, sem textura, e o fundo não é branco nem foto?
5. Se pediram uma pose que não é `acordado` nem `dormindo` — você disse que **não existe** em vez de improvisar?
6. Se é favicon: você trocou pelo marcador?

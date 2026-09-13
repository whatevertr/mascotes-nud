# TARS, ROCKY e CASE — como usar

As três mascotes do Método Constelação. Grade 32×32, pixel art, paleta fechada nos **dois estados** — noite e dia —, fundo transparente.

**Quem elas são está na lei.** Papel, granularidade, rosto zero, o olho que cada corpo produz, o posto do logo, a paleta: skill `estilo-nud` → `estilo-nud/references/manual.md` §D.12 · A família em pixel, e §"O elenco" do `SKILL.md` dela. Aqui só o que a lei não tem: **os números de animação, a semântica de cada uma e as proibições nominais.**

Os títulos dos arquivos-mestre são a descrição mais curta que existe delas: **TARS — cérebro-nebulosa** · **ROCKY — prumo com nível** · **CASE — vaga-lume**.

---

## Antes de tudo: rosto zero

Cada uma **já tem o olho que o próprio corpo produz** — o núcleo aceso da TARS, a bolha do nível da ROCKY, o abdômen do vaga-lume da CASE. Isso é lei (`estilo-nud`, manual §D.12, "Rosto zero"): **não se cola olho e boca por cima.** Não repito o motivo aqui; leia lá. `[CONV]`

O que é operacional e vale repetir: **o olho de cada uma é a peça que morre primeiro quando o tamanho cai** — ver "Piso de tamanho" abaixo.

---

## TARS — a Pensadora

**Arquivo-mestre:** `assets/nud-tars-pixel.svg` (32×32).
**Cores do sprite:** `#B57BFF` `#C8A2FF` `#E0CCFF` `#9C91B6` `#E9E6F1` `#FF8A5C`. É a única das três **sem `#06050B`** e **sem `#D97757`**.

**Movimento** `[CONV]`

| | |
|---|---|
| gesto | pulsa e respira |
| escala | **1,00 → 1,035** |
| brilho | **100% → 114%** |
| ciclo | **~7 s**, suave nas duas pontas |
| trajetória | nenhuma — *"nunca corre: não tem para onde ir"* |

**Proibição nominal:** **a TARS não pode ganhar borda.** `[CONV]`
O motivo é conceitual, não gráfico: *ela não tem borda porque não tem limite de assunto*. Contorno em TARS não é um contorno feio — é uma afirmação falsa sobre o que ela é. Nenhuma das três tem outline, mas essa é a única com motivo escrito.

**Semântica:** o kit não dá. TARS não tem leitura de estado — ela pensa, e pronto. Se você precisar que a peça diga "aprovado" ou "pendente", a mascote certa é a ROCKY.

---

## ROCKY — a Gerente

**Arquivo-mestre:** `assets/nud-rocky-pixel.svg` (32×32).
**Cores do sprite:** `#B6B0C8` `#A7A0BA` `#D2CEDF` `#E0CCFF` `#9C91B6` `#06050B` `#E9E6F1` `#FF8A5C` `#D97757`. É a única das três que usa **os dois laranjas**.
**Anatomia citada:** a **bolha** (o olho que o corpo produz) e o **fio** — a peça pendura pelo alto, e é por isso que o eixo de rotação fica no topo.

**Movimento** `[CONV]`

| | |
|---|---|
| gesto | oscila em torno do topo do fio |
| rotação | **−3,2° a +3,2°** |
| ciclo | **~5,4 s** |
| eixo | **`transform-origin: 50% 3%`** |

**Ressalva necessária sobre girar.** O manual proíbe distorcer, girar, inclinar e espelhar — mas isso está em **§E.12, que governa a assinatura, não os personagens**. A oscilação da ROCKY é legítima e o kit a declara como exceção explícita ao "não inclinar". Quem ler o manual sem esta linha vai achar que a rotação está proibida. `[CONV]`

**Semântica — a mais forte do elenco.** `[CONV]`

> *"Quando aprova, ela assenta e para. Quando diz 'ainda não', ela simplesmente não para."*

Na prática: **o estado de repouso da ROCKY é o veredito.** Ela não é decoração.

| O que a peça diz | Como a ROCKY fica |
|---|---|
| aprovado, fechado, entregue | **parada**, assentada no prumo |
| ainda não, pendente, em revisão | **oscilando**, sem assentar |

Consequências de uso:
- **Colocar a ROCKY numa peça é emitir um parecer.** Se a peça não tem nada a aprovar nem a pendurar, a mascote certa é outra.
- Em peça estática (impresso, slide sem animação, PNG), a ROCKY **está parada por falta de animação, não por aprovação**. Se a leitura de "aprovado" for importante, ela precisa vir do texto — a imagem parada não desambigua sozinha.
- Não anime ROCKY oscilando ao lado de um "concluído". Contradiz.

**Proibição nominal:** **não espelhar a ROCKY na vertical.** `[CONV]` Um prumo de cabeça para baixo deixa de ser prumo — some a função que dá nome à peça.

---

## CASE — a Trabalhadora

**Arquivo-mestre:** `assets/nud-case-pixel.svg` (32×32).
**Cores do sprite:** `#C8A2FF` `#E0CCFF` `#B6B0C8` `#A7A0BA` `#D2CEDF` `#9C91B6` `#06050B` `#E9E6F1` `#FF8A5C`. A paleta mais larga das três.
**Anatomia citada:** **olhos compostos** (no plural) e o abdômen do vaga-lume.

**Movimento** `[CONV]`

| | |
|---|---|
| gesto | pisca |
| brilho | **82%** na maior parte do ciclo, sobe a **150%** num pulso curto |
| salto | **4 px** junto com o pulso |
| ciclo | **~3,4 s** |

**Semântica — a saída.** `[CONV]`

> *"Ela apaga no meio de um gesto, sem despedida."*

A CASE não se despede: some no meio do trabalho. Se você animar uma saída dela, **não faça fade lento nem "tchau"** — o apagão cai no meio do pulso. Rima com o `some` do alien, que é corte seco (ver `alien.md`).

**Proibição nominal:** o kit não dá nenhuma só da CASE. Valem as gerais: não recolorir, não contornar, não acrescentar rosto, não acrescentar props, não distorcer, não borrar.

---

## As gerais das três

| Regra | Nota |
|---|---|
| **Não recolorir** | a paleta está fechada; cada sprite usa só as cores listadas acima `[CONV]` |
| **Não contornar** | nenhuma das três tem outline `[CONV]` |
| **Não acrescentar rosto** | é lei — ver `estilo-nud`, manual §D.12 `[CONV]` |
| **Não acrescentar props** | nenhum cartão, ferramenta ou palavra escrita dentro da imagem; *o método vive no texto ao redor, não pendurado na mascote* `[CONV]` |
| **Não distorcer** | só escala proporcional e inteira — ver `escala.md`. Exceção única: a oscilação da ROCKY `[NORMA TÉCNICA]` |
| **Não borrar** | nenhuma sombra cinza difusa. *Se precisar de profundidade, use o brilho de dentro* `[CONV]` |
| **`prefers-reduced-motion: reduce`** | tudo desliga, sprite parado. Nada pisca mais de 3× por segundo `[NORMA]` |

---

## Piso de tamanho

**32 px é o piso das três.** `[NORMA TÉCNICA]` Abaixo disso o desenho não existe mais:

| Personagem | O que morre abaixo de 32 px |
|---|---|
| **CASE** | os **olhos compostos** somem |
| **ROCKY** | a **bolha** some |
| **TARS** | o kit não diz o que ela perde |

Ou seja: abaixo do piso a ROCKY e a CASE perdem **exatamente o olho que o corpo produz** — sobra o corpo sem a coisa que o torna um ser. Para 16 px não se reduz mascote: usa-se o marcador `[·]`, que nasceu nesse tamanho (lei — ver `estilo-nud`).

Tabela de tamanhos seguros e folga: **`escala.md`**.

---

## As três no dia

**As três têm versão dia** desde 16.08.2026: `assets/nud-tars-pixel-dia.svg` · `assets/nud-rocky-pixel-dia.svg` · `assets/nud-case-pixel-dia.svg`. **Peça de dia leva a Tríade** — pelo arquivo `-dia`, nunca por outro caminho.

`[NORMA]` **Nunca leve um sprite da noite para o papel/fundo do dia**: as cores da noite estão cravadas no arquivo e reprovam contraste sobre bege. `[NORMA]` **Nunca recolorir um sprite da noite no olho** para fingir que é dia — a tradução tem receita, e é `estilo-nud/references/traducao-dia.md`.

O olho de cada uma é a exceção da receita: o núcleo aceso da TARS, a bolha da ROCKY e o abdômen da CASE são a tinta mais funda do dia, não a mais clara.

---

## O que não existe

- **Uma pose por personagem.** Falta o repertório inteiro — dormindo, comentando, sumindo. Contra **duas** poses do alien e **quatro** do marcador vivo.
- **Nenhuma tem tira de animação**, apesar de os números acima existirem. Quem animar, implementa do zero a partir desta página.
- **Proveniência:** o kit não diz de onde vieram TARS, ROCKY e CASE. Só o alien tem origem registrada.
- **Anatomia em prosa:** o kit da Tríade não descreve a forma de cada uma. O que existe são os títulos dos mestres, os fragmentos citados aqui (bolha, fio, olhos compostos, a não-borda) e a granularidade que está na lei (§D.12).

---

## Teste

1. Se a ROCKY está na peça, **a peça tem um veredito**? E se ela está animada oscilando, o texto ao lado diz "ainda não" e não "concluído"?
2. Os números de animação usados são os desta página — TARS 1,00–1,035 / 100–114% / ~7 s · ROCKY ±3,2° com `transform-origin: 50% 3%` / ~5,4 s · CASE 82%→150% + 4 px / ~3,4 s — ou alguém arredondou de cabeça?
3. A TARS está sem borda? Alguém "melhorou" o contorno dela?
4. A ROCKY não foi espelhada na vertical?
5. O tamanho é ≥ 32 px e os olhos compostos da CASE / a bolha da ROCKY ainda estão lá?
6. Se é peça de dia: o arquivo é o `-dia` de cada uma, e não o da noite levado para o bege?

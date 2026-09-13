# O marcador vivo — a física dos quatro estados

O `[·]` como criatura de ímã. **Os colchetes são os polos; o quadrado no centro é o que está preso entre eles.** Quando os polos se movem, o quadrado responde — e é aí que está a emoção.

Arquivos-mestre: `assets/nud-marcador-vivo-triste.svg` · `-descansado.svg` · `-feliz.svg` · `-vidrado.svg`. Todos em caixa **24×16**.

---

## A física — duas forças

| Força | O que faz |
|---|---|
| **Distância entre os polos** | quanto mais longe, **mais folga** o quadrado tem |
| **Direção do estiramento** | o quadrado **estica no eixo em que está sendo puxado** |

Daí sai a oposição que organiza tudo:

> **Esticado na horizontal é bem-estar. Esticado na vertical é tensão.**
> A mesma quantidade de laranja, dois estados opostos, só mudando o eixo.

---

## Dois eixos, não um

O laranja **não segue o humor** — segue a **ativação**. Isso é um segundo eixo, independente do primeiro.

| Eixo | O que diz | Como se lê |
|---|---|---|
| **Estiramento** (forma) | bem-estar ↔ tensão | horizontal = bem-estar · vertical = tensão |
| **Ativação** (cor) | repouso ↔ excitação | `#D97757` calmo = apagado · `#FF8A5C` tenso = aceso |

**Excitação — para cima ou para baixo — acende o laranja. Repouso e tristeza o mantêm apagado.** Por isso `triste` e `descansado` são o par apagado, e `feliz` e `vidrado` são o par aceso. **Um estado triste não é um estado apagado por ser triste: é apagado por ser de baixa ativação.**

---

## Os quatro estados

| Estado | Os polos | O quadrado | Laranja |
|---|---|---|---|
| **triste** (encolhido) | juntos, o ser todo diminui | **2×2**, afundado na base | `#D97757` |
| **descansado** — **o padrão** | distância normal | **4×4**, centrado | `#D97757` |
| **feliz** (alongado) | afastados, braços relaxados | **6×3**, esticado na horizontal | `#FF8A5C` |
| **vidrado** (aberto) | escancarados, altura cheia | **2×8**, esticado na vertical | `#FF8A5C` |

`descansado` **[CONV]** é o padrão: é o ícone sozinho, sem nada acontecendo.

Os quatro vivem na **mesma caixa 24×16**, então **trocar um pelo outro não move nada em volta** — dá para mudar de estado no meio de um texto sem reflow.

**Piso: 24×16.** No `triste` o quadrado tem 2 px de lado; abaixo da base ele **desaparece**. Folga em volta: **o kit não diz** (só as mascotes têm número de folga).

---

## A ressalva que evita o falso erro — §E.12 item 4

O manual da marca, em **§E.12 item 4**, proíbe **alterar o vão entre os colchetes e o ponto**. A física do marcador vivo é **exatamente variar esse vão**.

**Não é contradição.** A §E.12 governa **a assinatura**. O marcador vivo é personagem **derivado** dela.

> **A assinatura fica parada. O personagem se mexe.**

Um não invalida o outro porque não são a mesma coisa. **[NORMA]** o vão travado vale para o logo, o lockup e o favicon; a variação do vão vale para o personagem, e só para ele. Quem lê a §E.12 sem esta ressalva conclui que o kit está errado — não está.

---

## O que o descaracteriza — **[NORMA]**

- **Não separar o quadrado dos colchetes. Sem os polos, ele não é nada.**
- **Não recolorir.** Colchete violeta, quadrado laranja — **nunca o inverso**.
- **Não usar o `vidrado` como padrão.** É o estado forçado; usá-lo em toda peça faz a marca parecer **permanentemente ansiosa**.
- **Um estado por tela** (regra 2 do `SKILL.md`). Aplicada aqui: não monte os quatro numa peça de produção como se fossem um mostrador de humor — isso é material de manual, não de uso.

### A exceção do lockup

`vidrado` **é a forma que já estava no lockup**. A versão do marcador que aparece no título sempre foi a aberta, alta e estreita: **o nome da marca é dito no estado ansioso. Isso não foi corrigido, foi codificado.** É a única exceção declarada à proibição acima.

---

## A tira de 4 quadros

4 quadros de **192×128** numa faixa de **768×128** (8× da base). Animação por passos:

```css
@keyframes iman { from { background-position: 0 0; } to { background-position: -768px 0; } }

.marcador-vivo {
  width: 192px; height: 128px;
  background-image: url("tira/nud-marcador-tira-4quadros.png");
  background-size: 768px 128px;
  image-rendering: pixelated;
  animation: iman 3.2s steps(4) infinite;
}
@media (prefers-reduced-motion: reduce) { .marcador-vivo { animation: none; } }
```

Ordem da tira: **triste → descansado → feliz → vidrado**.

**Variante de respiração:** para um ciclo de respiração em vez de um giro de humor, use **só `descansado` e `feliz`** alternando.

Sem interpolação — `steps()`, nunca `ease`, `transition` ou morph (é lei; ver `estilo-nud`). A frase do kit: *ímã salta, não desliza.*

**De dia não anima:** no papel a criatura **fica num estado só, escolhido por peça**.

**Quadros intermediários não existem** — são quatro poses, não uma curva. E **regra de qual estado usar onde: o kit não diz** — hoje é decisão caso a caso.

---

## Teste

1. Os dois colchetes estão presentes e o quadrado está entre eles?
2. Colchete violeta e quadrado laranja — não o inverso?
3. A cor do quadrado bate com a **ativação** do estado (`triste`/`descansado` calmo, `feliz`/`vidrado` tenso), e não com o "humor"?
4. Só **um** estado na peça?
5. Se é `vidrado`: é o lockup? Se não é, por que não está em `descansado`?
6. A peça está a 24×16 ou mais, e a animação é `steps()` sem interpolação?

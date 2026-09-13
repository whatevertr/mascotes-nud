# Entrega — qual arquivo eu mando, em que formato, para que uso

Este arquivo responde à pergunta prática. **Tamanho é `escala.md`** — aqui é formato, pasta e destino.

---

## A regra de ouro

> **SVG sempre que possível. PNG só onde o SVG não entra.** `[CONV]`

O `svg/` é o **arquivo-mestre** dos três kits: vetor exato, 1 rect por corrida de pixel. Escala para qualquer tamanho sem perder aresta, serve web e impressão, e é o único que não precisa ser reexportado quando muda o tamanho.

PNG não é upgrade nem "versão final" — é **concessão a destino que não aceita vetor**. Toda vez que alguém manda PNG onde o SVG entraria, a peça fica presa num tamanho.

---

## A tabela por uso

| Uso | Manda | Observação |
|---|---|---|
| **favicon** | **o marcador `[·]`** — `assets/nud-marcador-pixel.svg` (16×16) | **nunca mascote.** O favicon é o posto do logo, e o posto é do marcador — ver `estilo-nud` e a regra 4 do `SKILL.md`. Ver também o aviso sobre a pasta `favicon/` da Tríade, abaixo |
| **avatar / foto de perfil** | padrão: **o marcador**. Por pedido explícito: mascote, de `avatar/` — 800×800, transparente ou noite | os arquivos de `avatar/` **já vêm com a folga aplicada** |
| **sticker** | SVG se o destino aceitar; senão **PNG transparente** no maior tamanho seguro | o kit não nomeia "sticker" — vale a regra de ouro e a série de tamanhos de `escala.md` |
| **overlay** (sobre superfície da marca) | SVG; senão **PNG transparente** | o kit não nomeia "overlay". Fundos permitidos: `#22202A` ou `#06050B`. **Nunca branco, nunca foto** |
| **slide** | SVG se a ferramenta aceitar; na prática quase sempre **PNG transparente** | slide é editor — cai no caso "onde o SVG não entra" |
| **impresso** | **SVG** | é para isso que o mestre existe. Se a peça é de **dia**, é o mestre `-dia` — ver "O dia deixou de ser buraco" |
| **e-mail / deck** | **PNG transparente** | os dois estão nomeados no kit como o caso onde o SVG não entra |
| **fundo que não suporta transparência** | **PNG fundo-noite** — 512 px sobre `#22202A` | só a Tríade tem essa pasta |
| **mandar para alguém ver o conjunto** | `previa/` — folha de contato | só a Tríade tem |
| **programar ou desenhar em cima** | `paleta/` — `.css` com variáveis e `.txt` legível | só a Tríade tem |

---

## O que cada pasta de exportação significa

| Pasta | O que é | Quando |
|---|---|---|
| **`svg/`** | vetor exato, 1 rect por corrida de pixel — **é o arquivo-mestre** | qualquer tamanho, impressão, web. **Primeira escolha sempre** |
| `png-transparente/` | raster nos tamanhos da série do personagem | onde o SVG não entra: e-mail, editor, deck |
| `png-fundo-noite/` | 512 px sobre `#22202A` | onde a transparência **não é suportada** |
| `favicon/` | 32 · 64 · 128 px | aba do navegador, app icon — **só por pedido explícito**; o posto é do marcador. Ver aviso abaixo |
| `avatar/` | 800 px, com folga, transparente e noite | perfil de rede social — **só por pedido explícito**; o padrão é o marcador |
| `previa/` | folha de contato | mandar para alguém ver o conjunto |
| `paleta/` | `.css` + `.txt` | quem for programar ou desenhar em cima |
| `tira/` | 4 quadros de 192×128 numa faixa de 768×128 | só o marcador vivo — animação por `steps()` |

---

## Onde vivem os PNG

**Os PNG ficam fora das skills, num kit de entrega separado. As skills carregam o SVG-mestre.**

Não é decisão de peso: todo o raster do acervo soma **~0,25 MB em 66 arquivos** — o inventário inteiro de personagem cabe em ~0,37 MB. **A separação é organizacional** — a skill não carrega raster —, não de tamanho. Não use "ficou pesado" como argumento; não é verdade.

Se você precisa de um PNG e ele não está no kit de entrega, o caminho é **exportar do SVG-mestre** seguindo `escala.md`, não improvisar um redimensionamento.

---

## Armadilha de nomenclatura — leia antes de procurar arquivo

**O mesmo arquivo tem nome diferente no kit e na skill.** Exemplos:

| No kit | Na skill (`assets/`) | Conteúdo |
|---|---|---|
| `nud-alien-acordado.svg` | `nud-mascote-pixel.svg` | **byte a byte idêntico** |
| `nud-alien-dormindo.svg` | `nud-mascote-dormindo-pixel.svg` | **byte a byte idêntico** |
| `nud-tars.svg` · `nud-rocky.svg` · `nud-case.svg` | `nud-tars-pixel.svg` · `nud-rocky-pixel.svg` · `nud-case-pixel.svg` | **byte a byte idênticos** |
| `nud-marcador-triste.svg` (e os outros 3) | `nud-marcador-vivo-triste.svg` (e os outros 3) | **byte a byte idênticos** |
| `tira/nud-marcador-tira-4quadros.png` | `nud-marcador-vivo-tira-4quadros.png` | **byte a byte idêntico** |

Conferido por MD5 do conteúdo integral: **todos os pares batem, nenhum divergiu.** Hoje não há duas versões circulando.

**Dois riscos, mesmo assim:**
1. Quem procurar por nome vai achar que são arquivos diferentes e pode entregar "os dois".
2. **Qualquer edição futura de um lado cria a divergência que ainda não existe.** Se mexer no mestre, mexa nos dois — ou o par silenciosamente deixa de ser o mesmo arquivo.

**Sem par, só na skill:** `nud-lockup-pixel.svg` e `nud-marcador-pixel.svg` — nenhum dos dois tem cópia em kit nenhum.

---

## Aviso — a pasta `favicon/` da Tríade não tem um bit próprio

Os 9 arquivos de `favicon/` do kit da Tríade (3 personagens × 32/64/128) são **cópias byte a byte de `png-transparente/` nos mesmos tamanhos**. `nud-case-favicon-32.png` **é** `nud-case-32.png`. Nenhum deles foi tratado, hinteado ou redesenhado para tamanho de aba.

Consequências:
- **Não trate `favicon/` como material especializado.** É o mesmo PNG com outro nome.
- A pasta **existe e contradiz a regra** de que o favicon é do marcador. O kit da Tríade admite favicon de mascote "só por pedido explícito"; o kit do alien e a lei tratam o posto como fechado. **Esta skill segue a lei: favicon é do marcador.** A pasta é material que ninguém decidiu apagar.

---

## Os buracos do acervo — o que não existe para entregar

**O alien não tem** `favicon/`, `avatar/`, `png-fundo-noite/`, `previa/` nem `paleta/` — todas pastas que a Tríade tem. O alien só tem `svg/` e `png-transparente/` (32 · 64 · 128 · 256 · 512, cada estado).

**O marcador vivo não tem** `favicon/`, `avatar/` nem `png-fundo-noite/`. Tem `svg/`, `png-transparente/` (24×16 · 48×32 · 96×64 · 192×128 · 384×256, cada estado) e `tira/`.

**O marcador de assinatura não tem PNG em tamanho nenhum.** É o personagem mais usado da marca — logo, favicon, assinatura — e existe só como SVG solto (`nud-marcador-pixel.svg` 16×16, `marcador.svg` 64×64, `marcador-1bit.svg` 64×64 monocromático). Enquanto o marcador **vivo** tem 20 PNGs, o marcador que ocupa o posto do logo tem zero. **Se pedirem o favicon em PNG, ele não existe — exporte do SVG por `escala.md`.**

**O lockup não tem kit.** Existe como SVG nos dois estados (`nud-lockup-pixel.svg` e `nud-lockup-pixel-dia.svg`, 64×16), mas sem kit e sem exportação em nenhum tamanho.

**Poses:** a Tríade tem **1 pose** por personagem, contra **2** do alien (acordado, dormindo) e **4** do marcador vivo. Se pedirem TARS dormindo, não existe.

**O dia deixou de ser buraco** (16.08.2026): todo sprite de pixel tem versão dia, mesmo nome com sufixo `-dia` — `nud-mascote-pixel-dia.svg` · `nud-mascote-dormindo-pixel-dia.svg` · `nud-marcador-pixel-dia.svg` · `nud-lockup-pixel-dia.svg` · `nud-marcador-vivo-{triste,descansado,feliz,vidrado}-dia.svg` · `nud-tars-pixel-dia.svg` · `nud-rocky-pixel-dia.svg` · `nud-case-pixel-dia.svg`, mais os vetores `mascote-dia.svg`, `mascote-dormindo-dia.svg` e `marcador-dia.svg`. Peça de dia leva a Tríade e o marcador vivo normalmente. **Nunca leve um sprite da noite para peça de dia** `[NORMA]` — as cores da noite estão cravadas no arquivo e reprovam contraste — e **nunca recolora o sprite da noite no olho**: a receita é `estilo-nud/references/traducao-dia.md`.

Quando faltar arquivo: **avise que não existe.** Não recolora, não redesenhe, não aproxime.

---

## Teste

1. O destino aceita SVG? Se aceita e você mandou PNG, **volte** — o mestre é o SVG.
2. É favicon? Então é o **marcador `[·]`**, não mascote.
3. É avatar de mascote? Houve **pedido explícito**? E você usou `avatar/`, sem somar folga por cima?
4. O destino não suporta transparência? Então é `png-fundo-noite/` — e isso só existe para a Tríade.
5. Você procurou o arquivo por um nome e não achou — checou o **nome gêmeo** (kit × skill) antes de dizer que não existe?
6. O arquivo pedido está na lista de buracos acima? Se está, você **avisou** em vez de improvisar?
7. É peça de dia? O arquivo é o mestre `-dia`, e não o da noite levado para o bege nem recolorido no olho?

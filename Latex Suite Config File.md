# LaTeX Suite — Snippet Reference

> Generated from your custom snippets config. `$0`, `$1`, `$2`... are tab-stops; `${VISUAL}` wraps selected text; options `m` = math mode, `t` = text mode, `A` = auto-expand, `n` = no auto-expand, `r` = regex, `w` = word boundary.

---

## Math Mode Entry/Exit

|Trigger|Expands to|Notes|
|---|---|---|
|`mk`|`$ $` (inline math)||
|`dm`|`$$\n\t\n$$` (display math)||
|`dm` (mid-line)|newline + display math block|when typed after other text on the line|
|`beg` (after non-backslash char)|`\begin{env}\n\t\n\end{env}`|multi-line, `M` option|
|`beg` (no auto)|`\begin{env} ... \end{env}`|single-line variant|

---

## Greek Letters

| Trigger | Symbol         | Trigger | Symbol |
| ------- | -------------- | ------- | ------ |
| `@a`    | α              | `@l`    | λ      |
| `@b`    | β              | `@L`    | Λ      |
| `@g`    | γ              | `@s`    | σ      |
| `@G`    | Γ              | `@S`    | Σ      |
| `@d`    | δ              | `@u`    | υ      |
| `@D`    | Δ              | `@U`    | Υ      |
| `@e`    | ε              | `@o`    | ω      |
| `:e`    | ϵ (varepsilon) | `@O`    | Ω      |
| `@z`    | ζ              | `ome`   | ω      |
| `@t`    | θ              | `Ome`   | Ω      |
| `@T`    | Θ              | `@i`    | ι      |
| `:t`    | ϑ (vartheta)   | `@k`    | κ      |

_Plus a general rule: typing any Greek letter name (e.g. `alpha`, `beta`) after a non-backslash character auto-inserts the `\` — and a space is inserted automatically before a following letter._

---

## Text Environments

|Trigger|Expands to|
|---|---|
|`text`|`\text{ }`|
|`"`|`\text{ }`|

---

## Basic Operations

|Trigger|Expands to|Meaning|
|---|---|---|
|`sr`|`^{2}`|square|
|`cb`|`^{3}`|cube|
|`rd`|`^{ }`|generic power|
|`_`|`_{ }`|subscript|
|`sts`|`_\text{ }`|text subscript|
|`sq`|`\sqrt{ }`|square root|
|`//`|`\frac{ }{ }`|fraction|
|`ee`|`e^{ }`|exponential|
|`invs`|`^{-1}`|inverse|
|`exp`, `log`, `ln`|`\exp`, `\log`, `\ln`|auto-backslash|
|`conj`|`^{*}`|complex conjugate|
|`Re` / `Im`|`\mathrm{Re}` / `\mathrm{Im}`|real/imaginary part|
|`bf`|`\mathbf{ }`|bold|
|`rm`|`\mathrm{ }`|roman/upright|

---

## Linear Algebra

|Trigger|Expands to|
|---|---|
|`det`|`\det` (auto-backslash)|
|`trace`|`\mathrm{Tr}`|

---

## Accents & Modifiers

**Letter + word form** (e.g. `xhat`, `avec`) — applies directly to preceding letter:

|Trigger|Result|
|---|---|
|`[letter]hat`|`\hat{letter}`|
|`[letter]bar`|`\bar{letter}`|
|`[letter]dot`|`\dot{letter}`|
|`[letter]ddot`|`\ddot{letter}`|
|`[letter]tilde`|`\tilde{letter}`|
|`[letter]und`|`\underline{letter}`|
|`[letter]vec`|`\vec{letter}`|
|`[letter],.` or `[letter].,`|`\mathbf{letter}`|
|`\greek,.` or `\greek.,`|`\boldsymbol{\greek}`|

**Standalone (with placeholder)**:

|Trigger|Result|
|---|---|
|`hat`|`\hat{ }`|
|`bar`|`\bar{ }`|
|`dot`|`\dot{ }`|
|`ddot`|`\ddot{ }`|
|`cdot`|`\cdot`|
|`tilde`|`\tilde{ }`|
|`und`|`\underline{ }`|
|`vec`|`\vec{ }`|
|`pmod`|`\pmod{n}`|

**Auto subscripting** (regex-driven, chained so digits after letters/accents nest correctly):

- `x3` → `x_{3}`, `x_{3}4` → `x_{34}`
- `\dot{x}3` → `\dot{x}_{3}`, then further digits merge into the subscript
- Works through double accents too: `\dot{\vec{a}}3` → `\dot{\vec{a}}_{3}`

**Quick indices**: `xnn`→`x_{n}`, `xii`→`x_{i}`, `xjj`→`x_{j}`, `xp1`→`x_{n+1}`, `ynn`/`yii`/`yjj` (same for y)

---

## Symbols & Relations

|Trigger|Symbol|Trigger|Symbol|
|---|---|---|---|
|`ooo`|∞|`<->`|↔|
|`sum`|∑ (bare)|`->`|→|
|`\sum`|∑ with limits template|`!>`|↦|
|`prod`|∏ (bare)|`=>`|⟹|
|`\prod`|∏ with limits template|`=<`|⟸|
|`lim`|`\lim_{n \to \infty}`|`and`|∩|
|`+-`|±|`orr`|∪|
|`-+`|∓|`inn`|∈|
|`...`|… (dots)|`notin`|∉|
|`nabl`|∇|`\\\`|∖ (setminus)|
|`xx`|×|`sub=`|⊆|
|`**`|⋅|`sup=`|⊇|
|`para`|∥|`eset`|∅|
|`===`|≡|`set`|`\{ \}`|
|`!=`|≠|`exists`|∃|
|`>=` / `<=`|≥ / ≤|`LL` / `HH`|ℒ / ℋ|
|`>>` / `<<`|≫ / ≪|`CC` / `RR`|ℂ / ℝ|
|`simm` / `sim=`|∼ / ≃|`ZZ` / `NN`|ℤ / ℕ|
|`prop`|∝|||

_General regex rules also auto-backslash any recognized Greek letter or symbol name, and insert a space after a Greek/symbol command when followed by a letter (so `\alpha x` doesn't glue together)._

---

## Derivatives & Integrals

| Trigger                  | Expands to                                                  |
| ------------------------ | ----------------------------------------------------------- |
| `par`                    | `\frac{\partial y}{\partial x}`                             |
| `pa[x][y]` (e.g. `paxy`) | `\frac{\partial x}{\partial y}` — regex letter-pair version |
| `ddt`                    | `\frac{d}{dt}`                                              |
| `int`                    | `\int` (auto-backslash)                                     |
| `\int`                   | `\int \, dx` template                                       |
| `dint`                   | `\int_{0}^{1} \, dx` definite integral template             |
| `oint`                   | ∮ contour integral                                          |
| `iint`                   | ∬ double integral                                           |
| `iiint`                  | ∭ triple integral                                           |
| `oinf`                   | `\int_{0}^{\infty} \, dx`                                   |
| `infi`                   | `\int_{-\infty}^{\infty} \, dx`                             |

---

## Trigonometry

| Trigger                                                                | Behavior                                                     |
| ---------------------------------------------------------------------- | ------------------------------------------------------------ |
| `sin`, `cos`, `tan`, `arcsin`, `arccos`, `arctan`, `csc`, `sec`, `cot` | auto-backslash                                               |
| `\sin`, `\cos`, etc. + letter                                          | inserts a space after (skips `h` so `sinh` still forms)      |
| `\sinh`, `\cosh`, `\tanh`, `\coth` + letter                            | inserts space after                                          |
| `arccsc`, `arcsec`, `arccot`                                           | wrapped as `\operatorname{...}` since not built into MathJax |

---

## Visual Operations (act on selected text `${VISUAL}`)

|Trigger|Wraps selection in|
|---|---|
|`U`|`\underbrace{ } _ { }`|
|`O`|`\overbrace{ } ^ { }`|
|`B`|`\underset{ }{ }`|
|`C`|`\cancel{ }`|
|`K`|`\cancelto{ }{ }`|
|`S`|`\sqrt{ }`|

---

## Physics

|Trigger|Expands to|
|---|---|
|`kbt`|`k_{B}T`|
|`msun`|`M_{\odot}`|

## Quantum Mechanics

|Trigger|Expands to|
|---|---|
|`dag`|`^{\dagger}`|
|`o+`|⊕|
|`ox`|⊗|
|`bra`|`\bra{ }`|
|`ket`|`\ket{ }`|
|`brk`|`\braket{ \| }`|
|`outer`|`\ket{\psi}\bra{\psi}`|

## Chemistry

|Trigger|Expands to|
|---|---|
|`pu`|`\pu{ }` (physical units)|
|`cee`|`\ce{ }` (chemical equations)|
|`he4`|⁴₂He|
|`he3`|³₂He|
|`iso`|generic isotope template ⁴₂He (editable)|

---

## Environments

|Trigger|Expands to|
|---|---|
|`pmat`, `bmat`, `Bmat`, `vmat`, `Vmat`|`\begin{...rix} ... \end{...rix}` (multi-line by default, single-line variant with `n` option)|
|`matrix`, `cases`, `align`, `array`|`\begin{env} ... \end{env}` (same dual multi/single-line behavior)|

---

## Brackets

|Trigger|Expands to|
|---|---|
|`avg`|`\langle \rangle`|
|`norm`|`\lvert \rvert`|
|`Norm`|`\lVert \rVert`|
|`ceil`|`\lceil \rceil`|
|`floor`|`\lfloor \rfloor`|
|`mod`|`\| \|` (absolute value, not modulo — see `pmod` above)|
|`(`|`( )` — wraps visual selection if active, else tab-stop|
|`{`|`{ }` — same behavior|
|`[`|`[ ]` — same behavior|
|`lr(`|`\left( \right)`|
|`lr{`|`\left\{ \right\}`|
|`lr[`|`\left[ \right]`|
|`lr\|`|`\left\| \right\|`|
|`lra`|`\left< \right>`|

---

## Misc / Advanced

|Trigger|Behavior|
|---|---|
|`tayl`|Full Taylor expansion template: `f(x+h) = f(x) + f'(x)h + f''(x) h²/2! + ...` (with placeholders for `f` and `x`)|
|`iden{n}` (e.g. `iden3`)|JS function generates an **n×n identity matrix** in `pmatrix` form|
|list item + `dm`|Regex detects you're inside a numbered/bulleted list line and inserts a properly indented display-math block matching the list's indentation|

### Disabled/commented-out (present in file but inactive)

- `--`, `–-`, `—-` → en/em dash chaining
- Auto-converting standalone capital letters in text to inline math
- Auto-converting Greek letter _names_ typed in prose to math mode
- Auto-converting `x=2` / `x=n+1` style text to inline math

---

**Total active snippets:** ~150+, spanning Greek letters, operators, calculus, linear algebra, QM, chemistry, environments, and brackets.
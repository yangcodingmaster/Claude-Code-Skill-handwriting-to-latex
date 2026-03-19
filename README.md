# handwriting-to-latex

A Claude skill that converts handwritten notes, problem sets, and scanned PDFs into clean, Overleaf-ready `.tex` files — in one shot.

> Built for students and researchers who write by hand but submit in LaTeX.

---

## What It Does

Upload a photo of your handwritten notes or a scanned PDF, and Claude will:

- Recognise all mathematical expressions and format them correctly in LaTeX
- Preserve every step of your derivations — nothing gets simplified or skipped
- Generate a complete, self-contained `.tex` file that compiles on Overleaf with zero setup
- Flag any ambiguous handwriting with inline comments rather than silently guessing

**Supported input formats:** JPG, PNG, scanned PDF, iPad handwriting PDF

---

## How to Use

### 1. Add the skill to Claude

Copy the contents of [`SKILL.md`](./SKILL.md) and add it to your Claude skill configuration.

> **Claude Skills** are prompt instructions that teach Claude how to handle specific tasks. See [Anthropic's documentation](https://docs.anthropic.com) for how to set up custom skills.

### 2. Upload your handwriting

In a Claude conversation, upload your handwritten image or PDF and say something like:

- *"Convert this to LaTeX"*
- *"Transcribe this to a tex file"*
- *"Put this in Overleaf format"*

The skill triggers automatically when it detects handwritten mathematical content.

### 3. Get your `.tex` file

Claude will confirm what it sees, then generate a complete `.tex` file ready to paste into Overleaf.

---

## Example Output

**Input:** A photo of handwritten quantum mechanics derivations

**Output:**
```latex
\documentclass[12pt, a4paper]{article}
\usepackage{amsmath, amssymb, amsthm}
\usepackage{physics}
\usepackage{geometry}
\geometry{margin=2.5cm}

\begin{document}

\section*{Problem 1}

The time-independent Schrödinger equation is:
\[
    \hat{H} \ket{\psi} = E \ket{\psi}
\]

Expanding the Hamiltonian:
\begin{align*}
    \hat{H} &= \frac{\hat{p}^2}{2m} + V(\hat{x}) \\
            &= -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V(x)
\end{align*}

\end{document}
```

---

## Features

| Feature | Detail |
|---|---|
| Math environments | `align*`, `\[ \]`, `$...$` — chosen contextually |
| Matrices | `pmatrix`, `bmatrix`, augmented arrays |
| Physics notation | `\ket{}`, `\bra{}`, `\dv{}`, `\pdv{}`, `\hbar`, `\hat{}` |
| Tables | `booktabs` style |
| Ambiguity handling | Inline `% [Unclear: ...]` comments |
| Compiler target | Overleaf pdfLaTeX — no config needed |
| Cover page | Optional, added only on request |

---

## Repository Structure

```
handwriting-to-latex/
├── README.md       ← You are here
├── LICENSE         ← MIT
└── SKILL.md        ← The skill instruction file for Claude
```

---

## Contributing

Contributions are welcome! If you have improvements to the recognition rules, additional symbol mappings, or support for new input formats, feel free to open a pull request.

Please keep the skill instructions clear and concise — Claude reads this file directly.

---

## License

MIT © [yangcodingmaster](https://github.com/yangcodingmaster)

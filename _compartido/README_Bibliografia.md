# 📄 Plantilla FEPI — ESCOM / IPN

Plantilla LaTeX profesional para la materia **Formulación y Evaluación de Proyectos Informáticos**.

---

## ⚡ Inicio rápido (3 pasos)

### 1. Configura tus datos personales

Abre `main.tex` y edita **solo** el bloque de la parte superior (líneas ~10-16):

```latex
\newcommand{\alumno}{Tu Nombre Completo}
\newcommand{\grupo}{7BV1}
\newcommand{\actividad}{Nombre de tu Actividad o Tarea}
\newcommand{\materia}{Formulación y Evaluación de Proyectos Informáticos}
\newcommand{\profesor}{Nombre del Profesor}
\newcommand{\fechaEntrega}{\today}   % \today = fecha automática del sistema
```

### 2. Agrega tus referencias en `bibliografia.bib`

Copia uno de los ejemplos del archivo y rellena los campos con tus fuentes reales.  
Solo aparecerán en el PDF las referencias que cites con `\cite{}` en el texto.

### 3. Compila

| Entorno | Cómo compilar |
|---------|---------------|
| **TeXstudio** | Botón ▶ (o F5) dos o tres veces |
| **Overleaf** | Botón "Recompile" |
| **Terminal** | Ver sección "Compilación manual" |

---

## 📁 Estructura de archivos

```
Plantilla/
├── main.tex              ← Documento principal (edita aquí)
├── bibliografia.bib      ← Tus referencias bibliográficas
├── img/
│   ├── ipn.jpg           ← Logo IPN (no modificar)
│   └── ESCOM.png         ← Logo ESCOM (no modificar)
└── README_Bibliografia.md
```

---

## 📚 Cómo agregar bibliografía

### Tipos de referencia disponibles en `bibliografia.bib`

**Artículo de revista:**
```bibtex
@article{mi_clave,
  author  = {Apellido, Nombre and Otro, Autor},
  title   = {Título del artículo},
  journal = {Nombre de la Revista},
  year    = {2024},
  volume  = {10},
  number  = {2},
  pages   = {123--145},
  doi     = {10.1109/...}
}
```

**Libro:**
```bibtex
@book{mi_libro,
  author    = {Apellido, Nombre},
  title     = {Título del Libro},
  publisher = {Editorial},
  year      = {2023},
  address   = {Ciudad}
}
```

**Sitio web:**
```bibtex
@misc{mi_web,
  author       = {{Nombre de la Organización}},
  title        = {Título de la página},
  howpublished = {\url{https://www.ejemplo.com}},
  year         = {2024},
  note         = {Accedido: 22-Mar-2026}
}
```

**Conferencia:**
```bibtex
@inproceedings{mi_conf,
  author    = {Autor, A. and Coautor, B.},
  title     = {Título del artículo},
  booktitle = {Proceedings of the International Conference on ...},
  year      = {2024},
  pages     = {45--52}
}
```

**Tesis:**
```bibtex
@mastersthesis{mi_tesis,
  author  = {Estudiante, Nombre},
  title   = {Título de la Tesis},
  school  = {Instituto Politécnico Nacional},
  year    = {2024},
  type    = {Tesis de Maestría}
}
```

### Citar en el texto

```latex
Según estudios recientes \cite{mi_clave}, se ha demostrado que...

Varios autores coinciden en esto \cite{mi_libro, mi_web}.
```

---

## 🖥️ Compilación manual (terminal)

Ejecuta en orden (4 pasos para que la bibliografía aparezca):

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

O usa `latexmk` (hace todo automáticamente):

```bash
latexmk -pdf main.tex
```

---

## 🎨 Personalización del diseño

Las siguientes variables de color están definidas al inicio de `main.tex`.  
Modifícalas si tu profesor requiere un diseño diferente:

```latex
\definecolor{ipnRojo}{RGB}{139,0,20}       % Color de títulos y líneas
\definecolor{ipnGris}{RGB}{80,80,80}       % Color de subtítulos y encabezados
\definecolor{fondoTabla}{RGB}{245,245,245} % Fondo alterno de tablas
```

---

## ❓ Consejos

- **Las claves BibTeX** (ej. `mi_clave`) deben ser únicas; usa nombres descriptivos.
- **No borres** los logos de `img/` aunque no los veas compilar localmente.
- Si usas **Overleaf**, sube toda la carpeta como ZIP.
- Si la bibliografía **no aparece**, compila al menos 3 veces o usa `latexmk`.

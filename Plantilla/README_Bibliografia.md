# Plantilla LaTeX con Bibliografía IEEE

## Archivos modificados

1. **main.tex** - Archivo principal modificado para usar BibTeX con estilo IEEE
2. **bibliografia.bib** - Archivo nuevo con ejemplos de referencias en formato BibTeX

## Cómo usar la bibliografía

### 1. Agregar referencias al archivo bibliografia.bib

El archivo `bibliografia.bib` contiene ejemplos de diferentes tipos de referencias:
- Artículos de revista (@article)
- Libros (@book)
- Conferencias (@inproceedings)
- Sitios web (@misc)
- Tesis (@mastersthesis o @phdthesis)

### 2. Citar referencias en el documento

Para citar una referencia en tu texto, usa el comando `\cite{clave}`:

```latex
Según estudios recientes \cite{ejemplo_articulo}, se ha demostrado que...
```

Para citar múltiples referencias:
```latex
Varios autores han investigado este tema \cite{ejemplo_articulo, ejemplo_libro}.
```

### 3. Compilar el documento

Para que las referencias aparezcan correctamente, debes compilar en este orden:

1. `pdflatex main.tex`
2. `bibtex main`
3. `pdflatex main.tex`
4. `pdflatex main.tex`

O si usas un editor como TeXstudio o Overleaf, simplemente compila 2-3 veces.

## Características importantes

✅ **Solo se muestran las referencias citadas**: La bibliografía solo incluirá las referencias que hayas citado con `\cite{}` en tu documento.

✅ **Estilo IEEE**: Las referencias siguen el formato estándar IEEE.

✅ **Archivo separado**: Todas las referencias están en `bibliografia.bib`, lo que facilita su gestión y reutilización.

## Formato de referencias en bibliografia.bib

### Artículo de revista
```bibtex
@article{clave_unica,
  author  = {Autor1 and Autor2},
  title   = {Título del artículo},
  journal = {Nombre de la Revista},
  year    = {2023},
  volume  = {10},
  number  = {2},
  pages   = {123--145}
}
```

### Libro
```bibtex
@book{clave_libro,
  author    = {Nombre Autor},
  title     = {Título del Libro},
  publisher = {Editorial},
  year      = {2022}
}
```

### Sitio web
```bibtex
@misc{clave_web,
  author       = {{Nombre Organización}},
  title        = {Título de la página},
  howpublished = {\url{https://www.ejemplo.com}},
  year         = {2023},
  note         = {Accedido: 15-Ene-2024}
}
```

## Consejos

- La clave (ej: `ejemplo_articulo`) debe ser única para cada referencia
- Usa nombres descriptivos para las claves
- Mantén todas tus referencias en `bibliografia.bib` aunque no las uses todas
- Solo aparecerán en el PDF las que cites con `\cite{}`

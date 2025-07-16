# 🧠 Generador de Artículos Técnicos con IA (Ollama + LLMs)

Este script automatiza la conversión de archivos Markdown técnicos en artículos redactados con un lenguaje más accesible, claro y divulgativo utilizando modelos de lenguaje locales a través de [Ollama](https://ollama.com/).

---

## ✨ ¿Por qué usar este script?

En el mundo de la ciencia de datos, ingeniería de datos y machine learning, es común generar grandes cantidades de notas, experimentos y documentación técnica en archivos `.md`. Sin embargo, estas notas no siempre están preparadas para ser leídas por una audiencia más amplia (por ejemplo, lectores de blogs, colegas no técnicos, o estudiantes).

Este script resuelve eso:

✅ Convierte notas técnicas en artículos comprensibles  
✅ Utiliza tu propia GPU o servidor con [Ollama](https://ollama.com/)  
✅ No depende de servicios en la nube o APIs externas  
✅ Compatible con múltiples modelos como `llama3`, `deepseek`, `mistral`, etc.

---

## 🚀 ¿Cómo funciona?

1. **Entrada**: Directorio que contiene archivos `.md` con contenido técnico.
2. **Procesamiento**: Se recorre recursivamente cada archivo, se genera un prompt instructivo, y se envía al endpoint `/api/chat` de Ollama.
3. **Salida**: Se genera un nuevo archivo `_articulo.md` con el contenido transformado en estilo divulgativo y se guarda en un directorio con sufijo `_procesado`.

---

## 🛠️ Requisitos

- Tener instalado y funcionando [Ollama](https://ollama.com/)
- Tener modelos descargados (por ejemplo: `deepseek-r1:14b`)
- Python 3.7+
- `curl` instalado (utilizado internamente para llamar a Ollama)

---

## 📦 Instalación

```bash
git clone https://github.com/tu_usuario/generador-articulos-ollama.git
cd generador-articulos-ollama



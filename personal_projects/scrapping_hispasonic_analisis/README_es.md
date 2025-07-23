# Scraper y Analizador de Anuncios de Hispasonic

Este proyecto realiza web scraping y analiza los anuncios de instrumentos musicales de la sección de segunda mano de Hispasonic.com, con un enfoque específico en la categoría "teclados y sintetizadores". El objetivo principal es recopilar, procesar y estructurar los datos de los anuncios para su posterior análisis.

Todo el proceso está documentado en el cuaderno de Jupyter `01_from_web_to_csv_togit.ipynb`.

---

## Proceso

1.  **Web Scraping**: El script comienza determinando el número total de páginas en la categoría "teclados y sintetizadores". Luego, itera a través de cada página para recopilar las URLs de todos los anuncios individuales.
2.  **Descarga Local**: Para evitar sobrecargar el servidor y el riesgo de ser baneado, el contenido HTML de cada anuncio se descarga y se guarda localmente.
3.  **Extracción de Datos**: El script procesa los archivos HTML locales para extraer información clave de cada anuncio, incluyendo:
    *   **Acción**: Tipo de anuncio (ej. venta, busco, cambio).
    *   **Marca**: El fabricante del instrumento.
    *   **Precio**: El precio de venta.
    *   **Usuario**: El nombre de usuario del vendedor.
    *   **Ubicación**: La ciudad del vendedor.
    *   **Fechas**: Fechas de publicación y de caducidad.
    *   **Vistas**: El número de veces que el anuncio ha sido visto.
4.  **Limpieza y Procesamiento de Datos**: Los datos extraídos se limpian y procesan. Un paso clave es la conversión de fechas relativas (ej. "hace 3 días", "hace 2 semanas") a un formato estándar `YYYY/MM/DD`.
5.  **Exportación a CSV**: Los datos finales y estructurados se exportan a un archivo CSV, listos para el análisis.

## Tecnologías Utilizadas

*   **Python**
*   **Jupyter Notebook**
*   **Librerías**:
    *   `requests` para realizar peticiones HTTP.
    *   `BeautifulSoup4` para analizar HTML.
    *   `pandas` para la manipulación de datos y la creación del DataFrame final.
    *   `re` para las expresiones regulares utilizadas en la extracción de datos.
    *   `datetime` para el manejo de operaciones con fechas y horas.

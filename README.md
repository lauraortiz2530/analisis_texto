# Análisis Comparativo de Textos (PLN): Tu-160 vs. B-2 Spirit

Este repositorio contiene un script de Python para realizar un análisis de Procesamiento de Lenguaje Natural (PLN) comparativo entre dos textos. El objetivo es extraer y contrastar las narrativas, temas y enfoques de dos artículos enciclopédicos sobre bombarderos estratégicos icónicos: el Túpolev Tu-160 y el Northrop Grumman B-2 Spirit.

## 1. Fuentes de Datos

Los textos analizados (tu 160.txt y b2 spirit.txt) fueron extraídos de las siguientes páginas de Wikipedia:

* **Túpolev Tu-160:** [https://es.wikipedia.org/wiki/Túpolev_Tu-160](https://es.wikipedia.org/wiki/Túpolev_Tu-160)
* **Northrop Grumman B-2 Spirit:** [https://es.wikipedia.org/wiki/Northrop_Grumman_B-2_Spirit](https://es.wikipedia.org/wiki/Northrop_Grumman_B-2_Spirit)

## 2. Metodología

El análisis se realiza en un único script de Python (analisis_texto.py o similar) y sigue una metodología estándar de minería de textos:

1.  **Carga y Limpieza:** Los archivos .txt se cargan desde una ruta local. Se aplica una función de normalización robusta para eliminar ruido (etiquetas ``, citaciones [3], puntuación, números y espacios extra).
2.  **Análisis Descriptivo Básico:** Se realiza un conteo inicial de párrafos, frases y palabras para comparar la longitud y estructura de ambos textos.
3.  **Procesamiento con spaCy:**
    * Tokenización
    * Eliminación de *Stopwords* (palabras comunes)
    * Lematización (reducción de palabras a su raíz)
4.  **Análisis de Frecuencia:** Se identifican los términos más frecuentes en cada texto y se generan nubes de palabras (`WordCloud`) para visualizar los temas dominantes.
5.  **Etiquetado Gramatical (POS Tagging):** Se clasifican las palabras por su categoría gramatical (Sustantivos, Verbos, Adjetivos) para entender *de qué* se habla (cosas), *qué acciones* se realizan y *cómo* se describe.
6.  **Extracción de Relaciones (SVO):** Se extraen tripletas Sujeto-Verbo-Objeto para identificar las afirmaciones y relaciones clave en cada narrativa.

## 3. Hallazgos Clave

El análisis reveló diferencias narrativas fundamentales entre los dos textos, demostrando cómo dos temas similares pueden ser descritos de maneras drásticamente opuestas.

1.  **Rendimiento (Tu-160) vs. Costo (B-2):** El texto del Tu-160 se centra en sus **capacidades técnicas** (palabras clave: "supersónico", "velocidad", "alcance"). En contraste, la narrativa del B-2 está dominada por su **aspecto económico** (palabras clave: "coste", "dólares", "millones", "proyecto").

2.  **Acciones de Operación (Tu-160) vs. Gestión (B-2):** Los verbos clave del Tu-160 son operativos ("volar", "lanzar", "participar"). Los del B-2 son administrativos y financieros ("costar", "desarrollar", "fabricar"). Un texto describe una herramienta *en uso*, el otro describe el proceso de *crearla y pagarla*.

3.  **Identidad Descriptiva: "Pesado" vs. "Caro":** Los adjetivos definen la identidad de cada avión. El Tu-160 es "supersónico", "grande" y "pesado". El B-2 es "furtivo", "caro" y "negro" (proyecto secreto).

4.  **Actores: Máquina (Tu-160) vs. Política (B-2):** Las relaciones SVO del Tu-160 describen la máquina ("El Tu-160 tiene..."). Las del B-2 revelan la burocracia detrás de él, siendo una relación clave: (Congreso, aprobar, compra).

5.  **Narrativa: Historia Exhaustiva (Tu-160) vs. Controversia (B-2):** El texto del Tu-160 es significativamente más largo, buscando ser una historia completa. El del B-2 es una narrativa más corta y enfocada, centrada en la controversia de su costo y su desarrollo secreto.

## 4. Cómo Ejecutar

### Dependencias

El script requiere las siguientes bibliotecas de Python:
spacy
wordcloud
matplotlib

# Análisis de Convergencia Programática en España (2023)
## Descripción
Este proyecto surge de la necesidad de cuantificar y comparar las propuestas políticas de los principales partidos españoles (PP, PSOE, VOX, SUMAR) mediante técnicas avanzadas de Procesamiento de Lenguaje Natural (NLP). En lugar de realizar un análisis subjetivo o basado únicamente en palabras clave, este motor de análisis transforma programas electorales complejos en un dataset estructurado de propuestas individuales, permitiendo una comparación matemática precisa.

# Pipeline Técnico
El flujo de trabajo se divide en tres etapas críticas:
- Ingesta y Extracción: Uso de librerías de manipulación de documentos para convertir PDFs no estructurados en texto plano, manteniendo la integridad gramatical necesaria para el análisis semántico.
- Segmentación Semántica (Micro-Análisis): Implementación de segmentación basada en estructuras gramaticales (usando spaCy) para dividir programas electorales de más de 100 páginas en unidades lógicas (propuestas individuales).
- Vectorización y Similitud: * Uso de Sentence Transformers (paraphrase-multilingual-MiniLM-L12-v2) para convertir cada propuesta en un vector denso (embeddings).
- Cálculo de similitud de coseno para determinar la proximidad semántica entre propuestas y partidos.
- Normalización de datos para asegurar una comparación justa, independientemente del volumen de texto de cada programa.


# Retos Técnicos Resueltos
- Asimetría Documental: Resolución de las diferencias en el formato de los PDFs mediante una normalización basada en la longitud y estructura de las frases, en lugar de confiar en patrones visuales (viñetas/guiones).
- Calidad de los Datos: Ajuste fino en la limpieza de ruido (URLs, basura de escaneo) para evitar distorsiones en los embeddings.
- Equilibrio Estadístico: Implementación de muestreo aleatorio (sampling) para normalizar el número de muestras por partido, garantizando que la matriz de convergencia no estuviera sesgada por el volumen de texto.

# Resultados
El proyecto genera una Matriz de Convergencia Programática que permite visualizar el porcentaje de similitud entre partidos para temas específicos (Vivienda, Empleo, Educación, etc.).

# TFG Evaluator

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21423214.svg)](https://doi.org/10.5281/zenodo.21423214)

**Aplicación:** https://fborrasumh.github.io/TFG_evaluator/ · **Idiomas de la interfaz:** español (por defecto), inglés y portugués de Brasil (selector en la cabecera o `?lang=en`, `?lang=pt`).

Evalúa trabajos finales con tu rúbrica y **evidencias citadas del propio texto**: TFG y TFM (España), dissertação (Portugal), TCC (Brasil), tesis o tesina (México, Perú), trabajo final (Argentina), trabajo de grado (Colombia), memoria de título (Chile) o, en **modo genérico**, cualquier proyecto final o tesis sin normativa de ningún país. Un único fichero (`index.html`), sin servidor, con la clave de **OpenAI, Google Gemini o Anthropic Claude** de cada persona.

## Novedades de la versión 2.0

- **Estilo Forja:** interfaz en español, inglés y portugués (también el informe de ejemplo, las plantillas de rúbrica y los avisos), tres proveedores de IA con el desplegable de modelos de cada clave y autoría con ORCID.
- **Tres proveedores para todo el motor:** evaluadores, síntesis, juez de calidad, extractor, chat y cascada. Con Gemini o Claude la primera pasada de la cascada usa probabilidades verbalizadas, porque esas API no exponen logprobs; el juez y la primera pasada se eligen entre los modelos del mismo proveedor.

- **Selector de país y nivel (grado o máster) o modo genérico.** Cambia el nombre del trabajo en la interfaz y en el informe, la escala por defecto (0–10, 0–20, 1–7, 0–5, 1–10 o 0–100), la nota mínima de aprobado (editable), las bandas cualitativas, el órgano evaluador (tribunal, júri, banca examinadora, jurado, comisión) y la norma de citación habitual (ABNT en Brasil).
- Ese contexto llega a los tres evaluadores y al agente de síntesis; en modo genérico se les prohíbe citar normativa nacional.
- **Bandas de calificación corregidas** para España (Suspenso < 5, Aprobado, Notable ≥ 7, Sobresaliente ≥ 9; la Matrícula de Honor la concede el tribunal).
- **Nuevas plantillas de rúbrica:** TCC con normalización ABNT (en portugués) y proyecto final genérico (en inglés).
- **Idiomas del informe:** español, español neutro, valenciano, inglés, portugués de Brasil y portugués europeo; se elige solo según el país.

## Cómo funciona

Guardrail contra inyección de instrucciones → extractor de pasajes por criterio → primera pasada en cascada → tres evaluadores independientes (cadena de evaluación, autocrítica y calibración con ejemplos) → síntesis que resuelve desacuerdos y redacta el feedback formativo. Las evidencias se verifican contra el texto del trabajo y la capa de calidad mide fidelidad, cobertura y acuerdo. **La nota es una propuesta: la decide el docente.**

## Privacidad

La clave se guarda solo en este navegador (localStorage) y viaja únicamente al proveedor elegido; la de OpenAI es la misma para todas las apps del catálogo. Los trabajos se procesan en el navegador y su texto se envía a OpenAI para evaluarlo: no subas trabajos sin la autorización que exija tu institución.

## Límites

- Los valores de cada país (escalas, aprobados, bandas, normas de citación) son habituales y varían entre instituciones: ajústalos al reglamento propio.
- El informe para el estudiante sale en el idioma elegido en «Idioma del informe»; las exportaciones (CSV, JSON e informes HTML descargables) mantienen las etiquetas en español.
- Las citas del trabajo se muestran siempre en su idioma original.
- Las estimaciones de coste de Gemini y Claude usan precios de referencia que pueden cambiar.
- La similitud entre trabajos es una señal de revisión, no una prueba de plagio.

## Cómo citar

Borrás Rocher, F. (2026). *TFG Evaluator* (versión 2.0.0) [Software]. Universidad Miguel Hernández de Elche. https://doi.org/10.5281/zenodo.21423214

Forma parte del catálogo [Herramientas IA para la academia](https://fborrasumh.github.io/ia/).

## Licencia

MIT © 2026 Fernando Borrás Rocher · Universidad Miguel Hernández de Elche.

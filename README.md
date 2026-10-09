# LatamGPT Engineering Hub

Portal de ingeniería de modelos de lenguaje: una ruta de aprendizaje de fundamentos a SOTA 2026 y guías prácticas con código para quienes construyen LLMs. Nació en [LatamGPT](https://huggingface.co/latam-gpt), el proyecto de LLMs para Latinoamérica de [CENIA](https://cenia.cl), así que los ejemplos ponen foco en español y portugués, pero el contenido sirve para cualquier modelo.

**Sitio:** https://gonzalofuentes1.github.io/llm-learning-route/

---

## Qué hay aquí

### Ruta de aprendizaje

[`latamgpt-roadmap.html`](latamgpt-roadmap.html) tiene dos vistas:

- **Ruta recomendada** (`#ruta`): el pipeline completo de un LLM en 7 etapas, de fundamentos a deployment, con ~35 temas y una guía práctica por etapa. Es el punto de partida para quien llega nuevo.
- **Roadmap completo** (`#completo`): 13 secciones con casi 300 temas y más de 900 papers enlazados a arXiv, con búsqueda y filtros por nivel (Básico / Core / Avanzado / SOTA 2026 / LatamGPT).

| Sección | Qué cubre |
|---|---|
| Fundamentos de ML | Backprop, optimizadores (AdamW, Muon, Shampoo/SOAP), normalización, precisión numérica |
| Modelos de referencia | De BERT y GPT-3 a los modelos abiertos y cerrados de 2026, más modelos iberoamericanos y Latam-GPT |
| Datos | Fuentes, deduplicación, filtrado, JQL, FineWeb2, mid-training, cumplimiento y datos es/pt |
| Pretraining | Scaling laws, paralelismo, FSDP2, baja precisión, contexto largo, continual pretraining |
| Arquitecturas modernas | MLA, atención híbrida y sparse, MoE moderno, conexiones residuales nuevas, difusión de texto |
| Post-training | SFT, LoRA, DPO, GRPO y sucesores, on-policy distillation, rúbricas, RL agéntico |
| Datos sintéticos | Self-Instruct, Magpie, rephrasing, datos verificables para RL, model collapse |
| Benchmarks & Evaluación | Harnesses, error bars, benchmarks de razonamiento, agentes y multilingües (incl. es/pt) |
| Seguridad y red teaming | HarmBench, guard models, jailbreaks, over-refusal, toxicidad y seguridad en es/pt |
| Inferencia y serving | KV cache, vLLM/SGLang, structured outputs, cuantización, disaggregated serving |
| Agentes, RAG y retrieval | MCP, function calling, búsqueda híbrida, embeddings multilingües, seguridad de agentes |
| Multimodal | VLMs, OCR de documentos, voz y modelos omni |
| Interpretabilidad | Circuitos, SAEs, attribution graphs, steering, idioma latente en es/pt |

### Guías prácticas

Cada guía incluye explicación conceptual, código copiable con APIs vigentes y referencias verificadas. Están agrupadas igual que en el [hub](index.html):

| Área | Guías |
|---|---|
| Infraestructura & MLOps | [Cluster HPC](guias/cluster.html), [MLOps: W&B + SLURM](guias/mlops.html) |
| Datos | [Tokenización en cloud](guias/tokenizacion-cloud.html), [Filtrado de calidad](guias/filtrado.html), [FineWeb-Edu](guias/fineweb-edu.html), [JQL multilingüe](guias/jql-filtrado-multilingue.html), [Mid-training](guias/mid-training.html), [Anonimización PII](guias/anonimizacion.html), [Sequence packing](guias/packing.html), [Tokenizadores](guias/tokenizer-training.html), [Pipeline sintético](guias/synthetic-pipeline.html) |
| Arquitectura & Pretraining | [LLM desde cero](guias/llm-desde-cero.html), [MoE desde cero](guias/moe-desde-cero.html), [Scaling laws](guias/scaling-laws.html), [Código de entrenamiento](guias/entrenamiento.html), [FSDP2 y torchtitan](guias/fsdp2-torchtitan.html), [Continual pretraining](guias/continual-pretraining.html), [Debugging](guias/debugging.html) |
| Post-training & Alineamiento | [LoRA/QLoRA](guias/lora-finetuning.html), [Datasets SFT](guias/sft-dataset.html), [DPO y variantes](guias/dpo-alignment.html), [Reward models](guias/reward-models.html), [GRPO](guias/grpo-rl.html), [Destilación de razonamiento](guias/destilacion-razonamiento.html), [On-policy distillation](guias/on-policy-distillation.html), [RL agéntico](guias/rl-agentico.html), [Model merging](guias/model-merging.html) |
| Seguridad & Guardrails | [Clasificadores con HarmBench](guias/clasificador-toxicidad-harmbench.html), [Red teaming y evaluación](guias/red-teaming-evaluacion-seguridad.html), [Guardrails con vLLM](guias/guardrails-produccion-vllm.html), [Toxicidad en pretraining](guias/filtrado-toxicidad-pretraining.html) |
| Evaluación | [Evaluación es/pt](guias/evaluacion-latam.html), [Evaluación estadística](guias/evaluacion-estadistica.html), [lighteval multilingüe](guias/lighteval-multilingue.html), [LLM-as-a-judge calibrado](guias/llm-judge-calibrado.html) |
| Inferencia & Deployment | [vLLM: primeros pasos](guias/inferencia.html), [Serving en producción](guias/serving-produccion.html), [Cuantización](guias/quantization.html), [Speculative decoding](guias/speculative-decoding.html) |
| Aplicaciones | [RAG en español](guias/rag-espanol.html), [Agentes con MCP](guias/agentes-mcp.html), [Encoders es/pt](guias/bert.html) |
| Interpretabilidad | [Interpretabilidad práctica](guias/interpretabilidad-practica.html), [¿En qué idioma piensa el modelo?](guias/idioma-latente-es-pt.html) |

---

## Contribuir

```bash
git clone https://github.com/GonzaloFuentes1/llm-learning-route.git
cd llm-learning-route
# editar archivos HTML
git add -p
git commit -m "feat: descripción del cambio"
git push
```

El sitio es HTML estático puro, sin build step.

**Agregar una guía:** crear `guias/<nombre>.html` copiando la estructura de una guía existente (mismas CSS variables, highlight.js, botón copiar, `<meta name="description">`, breadcrumb `Guías prácticas → <Sección>`) y enlazarla desde `index.html` con su `data-level` (`basic`, `core` o `advanced`). Cada guía debe terminar con una sección de **Referencias** con links a papers y documentación oficial.

**Agregar temas al roadmap:** editar el array `SECTIONS` en `latamgpt-roadmap.html`. Cada item lleva `level`, `title`, `desc`, `tags`, `papers` y `res` (recursos externos o guías del sitio con URL relativa `guias/<slug>.html`). Los contadores de temas, papers y secciones se calculan solos.

**Editar la ruta recomendada:** el array `ROUTE` (justo después de `SECTIONS`) define las etapas; cada item referencia una tarjeta por su `title` exacto, así que si renombras una tarjeta usada en la ruta, actualiza también su `ref`.

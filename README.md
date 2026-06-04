# LatamGPT Engineering Hub

Portal de recursos para ingenieros y practicantes que se suman al proyecto [LatamGPT](https://huggingface.co/latamgpt) en [CENIA](https://cenia.cl). Incluye una ruta de aprendizaje interactiva y guías prácticas con código sobre el stack completo de construcción de LLMs para Latinoamérica.

**Sitio:** https://gonzalofuentes1.github.io/llm-learning-route/

---

## Contenido

### Ruta de Aprendizaje

`latamgpt-roadmap.html` — roadmap interactivo de fundamentos a SOTA 2026. 6 secciones, 81 temas, 110+ papers con links a arXiv. Incluye búsqueda y filtros por nivel (Básico / Core / Avanzado / SOTA / LatamGPT).

| Sección | Temas |
|---|---|
| Datos | Fuentes, tokenización, deduplicación, filtrado, pipelines industriales |
| Pretraining | Transformers, scaling laws, paralelismo, FlashAttention, arquitecturas modernas |
| Post-training | SFT, PEFT, RLHF, DPO, Constitutional AI, GRPO |
| Datos Sintéticos | Self-Instruct, Evol-Instruct, Magpie, PersonaHub |
| Benchmarks & Evaluación | MMLU, MATH, LiveCodeBench, Trueque, MGSM, BBH |
| Modelos de Referencia | LLaMA, OLMo, DeepSeek, Qwen, BLOOM, Salamandra |

### Guías Prácticas

Cada guía tiene explicación conceptual + bloques de código copiables + fuentes enlazadas.

| Guía | Descripción |
|---|---|
| [Cluster HPC](guias/cluster.html) | SSH, llaves públicas, VS Code Remote, rsync, htop, nvidia-smi, SLURM |
| [Tokenización en Cloud](guias/tokenizacion-cloud.html) | Pipeline Datatrove, tokenización paralela a escala de TB |
| [Sequence Packing](guias/packing.html) | Eliminar padding (~30-50% de tokens desperdiciados) |
| [Código de Entrenamiento](guias/entrenamiento.html) | Accelerate + DeepSpeed ZeRO, training loop, checkpointing |
| [MLOps: W&B + SLURM](guias/mlops.html) | Experiment tracking, scripts SLURM, array jobs |
| [Modelos BERT es/pt](guias/bert.html) | Fine-tuning BETO/BERTimbau para clasificación y NER |
| [Filtrado de Calidad](guias/filtrado.html) | fastText, KenLM, reglas Gopher, pipeline Datatrove |
| [Anonimización PII](guias/anonimizacion.html) | Presidio + spaCy, recognizers para formatos latinoamericanos |
| [Serving con vLLM](guias/inferencia.html) | Levantar servidor vLLM, requests, benchmarking |
| [Debugging de Entrenamiento](guias/debugging.html) | Loss spikes, NaN/Inf, OOM, torch.profiler |

---

## Publicar en GitHub Pages

1. Ve a **Settings → Pages**
2. Source: `Deploy from a branch`
3. Branch: `main` → Folder: `/ (root)`
4. Guarda. El sitio estará disponible en ~1 minuto.

No requiere Jekyll ni ningún proceso de build — HTML estático puro.

---

## Contribuir

Para agregar o actualizar contenido:

```bash
git clone https://github.com/GonzaloFuentes1/llm-learning-route.git
cd llm-learning-route
# editar los archivos HTML
git add -p
git commit -m "feat: descripción del cambio"
git push
```

Las guías nuevas van en `guias/` siguiendo la estructura de las existentes (mismas CSS variables, highlight.js, botón copiar). Cada guía debe incluir una sección de **Fuentes** con links a papers y documentación oficial.

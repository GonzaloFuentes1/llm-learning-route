# LatamGPT Engineering Hub

Portal de recursos para ingenieros y practicantes que trabajan en [LatamGPT](https://huggingface.co/latamgpt), el proyecto de LLMs para Latinoamérica de [CENIA](https://cenia.cl).

**Sitio:** https://gonzalofuentes1.github.io/llm-learning-route/

---

## Qué hay aquí

### Ruta de Aprendizaje

Roadmap interactivo con 7 secciones, 97 temas y 130+ papers enlazados a arXiv. Incluye búsqueda y filtros por nivel (Básico / Core / Avanzado / SOTA 2026 / LatamGPT).

| Sección | Qué cubre |
|---|---|
| Fundamentos de ML | Backprop, gradientes, AlexNet, ResNets, regularización, Adam/AdamW/Muon |
| Modelos de referencia | LLaMA, OLMo, DeepSeek, Qwen, BLOOM, Salamandra y 20+ más |
| Datos | Fuentes, tokenización, deduplicación, filtrado, FineWeb, DCLM, RedPajama |
| Pretraining | Transformer, scaling laws, paralelismo, FlashAttention, MoE, RoPE |
| Post-training | SFT, LoRA, RLHF, DPO/ORPO/KTO, Constitutional AI, GRPO |
| Datos Sintéticos | Self-Instruct, Evol-Instruct, Magpie, PersonaHub, CoT sintético |
| Benchmarks & Evaluación | MMLU, MATH, LiveCodeBench, Trueque, MGSM, BBH, HLE |

### Guías Prácticas

Cada guía incluye explicación conceptual, código copiable y fuentes enlazadas.

| Guía | Descripción |
|---|---|
| [Cluster HPC](guias/cluster.html) | SSH, llaves públicas, VS Code Remote, rsync, htop, nvidia-smi, SLURM |
| [Tokenización en Cloud](guias/tokenizacion-cloud.html) | Pipeline Datatrove, tokenización paralela a escala de TB |
| [Sequence Packing](guias/packing.html) | Eliminar padding (~30-50% de tokens desperdiciados) |
| [Código de Entrenamiento](guias/entrenamiento.html) | Accelerate, DeepSpeed ZeRO, torchtune, ROCm/AMD |
| [MLOps: W&B + SLURM](guias/mlops.html) | Experiment tracking, scripts SLURM, array jobs |
| [Modelos BERT es/pt](guias/bert.html) | Fine-tuning BETO/BERTimbau para clasificación y NER |
| [Filtrado de Calidad](guias/filtrado.html) | fastText, KenLM, reglas Gopher, DCLM, NeMo Curator |
| [Anonimización PII](guias/anonimizacion.html) | Presidio + spaCy, recognizers para formatos latinoamericanos |
| [Serving con vLLM](guias/inferencia.html) | Levantar servidor vLLM, requests, benchmarking |
| [Debugging de Entrenamiento](guias/debugging.html) | Loss spikes, NaN/Inf, OOM, torch.profiler |

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

Para agregar una guía nueva: crear `guias/<nombre>.html` siguiendo la estructura de las existentes (mismas CSS variables, highlight.js, botón copiar) y linkearla desde `index.html`. Cada guía debe incluir una sección de **Fuentes** con links a papers y documentación oficial.

Para agregar temas al roadmap: editar el array `SECTIONS` en `latamgpt-roadmap.html`. Cada item lleva `level`, `title`, `desc`, `tags`, `papers` y `res` (recursos externos).

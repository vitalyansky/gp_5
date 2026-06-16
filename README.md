# GP5 — Кейс 1 и Кейс 2: Customer Support & Churn Prediction

## Кейс 1: Предсказание оттока клиентов

Задача бинарной классификации — предсказываем уйдёт ли клиент.

### Архитектуры
- **FCNN** — полносвязная нейронная сеть, baseline
- **TabNet** — архитектура для табличных данных с механизмом внимания по признакам

### Датасет
Табличные данные клиентов (поведенческие и демографические признаки).

---

## Кейс 2: Генерация ответов службы поддержки

Сравниваем три архитектуры на задаче автоматической генерации ответов customer support.

### Датасеты

- Customer Support on Twitter — [kaggle](https://www.kaggle.com/datasets/thoughtvector/customer-support-on-twitter)
- [Bitext Customer Support](https://github.com/vitalyansky/gp_5/blob/main/bitext_support%20-%20Лист1.csv) — синтетический датасет с парами запрос/ответ по 27 интентам

### Архитектуры

**1. LSTM + Attention (baseline)**
Рекуррентная сеть с механизмом внимания, обучаем с нуля.
Нижняя планка — смотрим насколько рекуррентка справляется до трансформеров.

**2. T5-small — Full Fine-tuning**
Text-to-Text Transfer Transformer от Google (2019).
Энкодер-декодер архитектура, делаем полный файнтюн всех весов.

**3. Llama-3.2-1B-Instruct — LoRA**
Декодер-трансформер от Meta.
Замораживаем основные веса, обучаем низкоранговые адаптеры в attention-слоях.

### Метрики
- ROUGE-1 / ROUGE-L
- BERTScore
- Distinct-1 / Distinct-2
- Perplexity

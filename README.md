# gp_5

Верхнеуровневый план по кейсу 2.

Обучаем 3 архитектуры:
1.  Baseline - делаем (LSTM + Attention)
2.  Pre-trained T5 smalll - делаем Full Fine-tuning
3.  Pre-trained Llama-3.2-1B-Instruct - делаем LoRA (Low-Rank Adaption)

Первая про рекуррентная нейронная сеть с механизмом долгосрочной памяти
Вторая архитектура это полный файнтюн для Text-to-Text Transfer Transformer (гугловская 2019). Представляет из себя энкодер-декодер трансформер, в отличии от только декодера (GPT) и только энкодера (BERT)
Третья архитектура это претрейн декодер трансформер от Meta, для которой обучаем адаптер

Первично, в качестве датасета можно взять kaggle.com/datasets/thoughtvector/customer-support-on-twitter

Также нужно поресерчить стадию evaluation, есть разные бенчмарки

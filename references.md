### Electrocardiogram generation with a bidirectional LSTM-CNN generative adversarial network
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6494992/

Рассматривают задачу генерации ЭКГ. Генератор состоит из двух слоев bi-LSTM, дискриминатор - CNN. На вход подают шум фиксированной длины, на выходе такой же длины ЭКГ. Сравнивают модел с RNN-AE, RNN-VAE, LSTM-AE, LSTM-VAE, метрики - PRD, RMSE, FD.

Датасет MIT-BIH Arrhythmia Database, количество каналов не нашла (полагаю, 2). 48 файлов с 30 минутами записи ЭКГ. Они в своей работе взяли только часть сигнала x_alpha, поделили на 200. Каждую ECG data point умножили на частоту сигнала (360 Гц) и получили 31.2 data points. 

### Deep Convolutional Generative Adversarial Network with LSTM for ECG Denoising
https://pubmed.ncbi.nlm.nih.gov/36818542/

https://www.hindawi.com/journals/cmmm/2023/6737102/

Рассматривают задачу улучшения качества сигнала. Генератор состоитз из CNN-LSTM блоков. Изначально сигналы берут из  MIT-BIH Arrhythmia Database и MIT-BIH Noise Stress Test Database, затем добавляют разные типы шумов. Сравнивают результаты с DCGAN и LSTM-GAN. Метрики PRD, RMSE, SNR. 

Из MIT-BIH Arrhytmia взяли 15 записей, использовали modified lead II (так как он популярен в носимых устройствах). Сигналы сегментировали по 1024 сэмпла на фрагмент, получили 8254 фрагмента.

MIT-BIH Noise Stress Test Database содержит шумы в 12-часовой ЭКГ и 3-часовую запись Хольтера. Также поделили сигналы на фрагменты по 1024 сэмпла, получили 6381 фрагмент.

### Generating electrocardiogram signals by deep learning
https://www.sciencedirect.com/science/article/abs/pii/S0925231220306615

https://sci-hub.ru/10.1016/j.neucom.2020.04.076

Описывают три модели генерации на основе WaveNet и GAN. По скорости две модели на основе GAN оказались лучше модели WaveNet.

Датасет с аритмией, взяли three types of heartbeats: normal beat (N), left bundle, branch block beat (L) and right bundle branch block beat (R), исключили те записи, где было много других типов. Поделили на фрагменты длиной 4 с, хитрым образом отобрали случайные разных типов. Итого 15,828 фрагмента длиной 4 секунды для трейна и 150 для теста (тест сбалансирован по классам N, L, R). 

Также собирают еще два датасета: 2 - применяют алгоритм Pan-Thompkins для локализации QRS-волн, собирают фрагменты по 360 поинтов и выбирают 5000 для теста и 500 для трейна.
3 - R-peak, длина фрагмента 50 поинтов, выбрали 10000 для трейна и 500 для теста. 

### Synthetic ECG signal generation using generative neural networks
https://arxiv.org/abs/2112.03268

В статье есть хороший раздел с Related works, откуда можно подергать дополнительные рефы на генерацию
Датасет MIT-BIH Arrhythmia. Рассматривают пять разных моделей на основе GAN и автоэнкодеров. Метрики - DTW, FD, евклидово расстояние. Еще из полезного - описали методы сравнения качества сгенерированных моделей (один из методов - взять настоящего эксперта, и пусть он сравнит 🙂).

Из датасета взяли класс N, в нем 90, 502 сэмплов длиной 280, их ресемплировали в длину 256. Как-то не очень вообще понятно, какой в итоге датасет.  

### SYNTHESIS OF REALISTIC ECG USING GENERATIVE ADVERSARIAL NETWORKS
https://arxiv.org/abs/1909.09150
 
Генератор - LSTM, BiLSTM. Дискриминатор - LSTM, CNN. Метрики - Maximum Mean Discrepancy, Dynamic Time Warping. Датасет с аритмией из статей выше.

Из датасета убрали коэффициент усиления (?) 200 adu/mV, ресемплировали 360 Гц в 125 Гц, записи ресемплировали в фрагменты длиной 10 секунд.

### ME-GAN: Learning Panoptic Electrocardio Representations for Multi-view ECG Synthesis Conditioned on Heart Diseases
https://proceedings.mlr.press/v162/chen22n/chen22n.pdf

https://proceedings.mlr.press/v162/chen22n.html

Рассматривают свою модель  ME-GAN, описывают возможность модифицировать данные, чтобы ЭКГ соответствовала определенному заболеванию. Еще описан какой-то хитрый дискриминатор. В целом модель из статьи отлично работает для улучшения качества классификаторов. Есть хорошее сравнение существующих моделей с данной. 

Два датасета -  Tianchi, PTB. Tianchi - 31,779 12-rканальных сигналов, частота 500 Гц. PTB - 549 12-канальных сигналов с частотой 1000 Гц. Взяли из двух датасетов рандомно 80% на тест и 20 на трейн

### A Conditional GAN for Generating Time Series Data for Stress Detection in Wearable Physiological Sensor Data
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwj8uNXf_vT9AhWkbvEDHU2xDqoQFnoECAoQAQ&url=https%3A%2F%2Fwww.mdpi.com%2F1424-8220%2F22%2F16%2F5969%2Fpdf&usg=AOvVaw0Ff9OVVo2kB4fX-goywE47

Рассматривают cGAN, статья полезна с точки зрения генерации временных рядов с условиями. Генератор LSTM, дискриминатор FCN

Датасет собирали сами.

### DeepFake electrocardiograms using generative adversarial networks are the beginning of the end for privacy issues in medicine
https://huggingface.co/deepsynthbody/deepfake_ecg

Датасеты: Danish General Suburban Population Study (8939 сэмплов) и Inter99 study (6667 сэмплов), ссылки есть в статье. Чтобы избежать аффектов, выбрали данные, которые были классифицированы как нормальные (7233 сэмпла). Длина: 10 секунд,  сэмплы 500/сек, всего 5000. Изначального 8 каналов, оставшиеся 4 досчитывают.  Архитектура у дискриминатора и генератора построена на WaveNet и Pulse2Pulse. 


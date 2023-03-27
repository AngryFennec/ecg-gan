### Electrocardiogram generation with a bidirectional LSTM-CNN generative adversarial network
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6494992/

Рассматривают задачу генерации ЭКГ. Генератор состоит из двух слоев bi-LSTM, дискриминатор - CNN. На вход подают шум фиксированной длины, на выходе такой же длины ЭКГ. Сравнивают модел с RNN-AE, RNN-VAE, LSTM-AE, LSTM-VAE, метрики - PRD, RMSE, FD. 

### Deep Convolutional Generative Adversarial Network with LSTM for ECG Denoising
https://pubmed.ncbi.nlm.nih.gov/36818542/
https://www.hindawi.com/journals/cmmm/2023/6737102/

Рассматривают задачу улучшения качества сигнала. Генератор состоитз из CNN-LSTM блоков. Изначально сигналы берут из  MIT-BIH Arrhythmia Database и MIT-BIH Noise Stress Test Database, затем добавляют разные типы шумов. Сравнивают результаты с DCGAN и LSTM-GAN. Метрики PRD, RMSE, SNR. 

### Generating electrocardiogram signals by deep learning
https://www.sciencedirect.com/science/article/abs/pii/S0925231220306615
https://sci-hub.ru/10.1016/j.neucom.2020.04.076

Описывают три модели генерации на основе WaveNet и GAN. По скорости две модели на основе GAN оказались лучше модели WaveNet.

### Synthetic ECG signal generation using generative neural networks
https://arxiv.org/abs/2112.03268

В статье есть хороший раздел с Related works, откуда можно подергать дополнительные рефы на генерацию
Датасет MIT-BIH Arrhythmia. Рассматривают пять разных моделей на основе GAN и автоэнкодеров. Метрики - DTW, FD, евклидово расстояние. Еще из полезного - описали методы сравнения качества сгенерированных моделей (один из методов - взять настоящего эксперта, и пусть он сравнит 🙂).

### SYNTHESIS OF REALISTIC ECG USING GENERATIVE ADVERSARIAL NETWORKS
https://arxiv.org/abs/1909.09150
 
Генератор - LSTM, BiLSTM. Дискриминатор - LSTM, CNN. Метрики - Maximum Mean Discrepancy, Dynamic Time Warping. Датасет с аритмией из статей выше.

### ME-GAN: Learning Panoptic Electrocardio Representations for Multi-view ECG Synthesis Conditioned on Heart Diseases
https://proceedings.mlr.press/v162/chen22n/chen22n.pdf
https://proceedings.mlr.press/v162/chen22n.html

Рассматривают свою модель  ME-GAN, описывают возможность модифицировать данные, чтобы ЭКГ соответствовала определенному заболеванию. Еще описан какой-то хитрый дискриминатор. В целом модель из статьи отлично работает для улучшения качества классификаторов. Есть хорошее сравнение существующих моделей с данной. 

### A Conditional GAN for Generating Time Series Data for Stress Detection in Wearable Physiological Sensor Data
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwj8uNXf_vT9AhWkbvEDHU2xDqoQFnoECAoQAQ&url=https%3A%2F%2Fwww.mdpi.com%2F1424-8220%2F22%2F16%2F5969%2Fpdf&usg=AOvVaw0Ff9OVVo2kB4fX-goywE47

Рассматривают cGAN, статья полезна с точки зрения генерации временных рядов с условиями. Генератор LSTM, дискриминатор FCN





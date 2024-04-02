# Time-Series Forecasting Project 📈

🧑‍🤝‍🧑Thanks to [Andrea Bertogalli](https://github.com/andberto) and [Niccolò Balestrieri](https://github.com/NiccoloBalestrieri)

## Dataset Inspection 🔍
The provided dataset consists of 48,000 time series, each 2,776 data points long due to padding. These series are divided into six categories (A-F), each representing a different domain. The actual length of each time series varies, reflecting the diverse nature of the dataset.

![immagine](https://github.com/tombinic/Time-Series-Forecasting/assets/91635053/31207401-a8f0-4732-b780-b9d260389f6c)

![immagine](https://github.com/tombinic/Time-Series-Forecasting/assets/91635053/7225e3d7-216d-484d-9971-34d23de89743)

## Pre-Processing 🛠️
Initial data inspection revealed duplicates and outliers. Despite considering the removal of short time series, all samples were ultimately retained. A novel approach was employed to identify constant signals, leading to the retention of 47,974 series post-pre-processing.

## Sequences Building 🏗️
The dataset was stratified by category to maintain uniform distribution across training and validation sets. Windows of size 200 were constructed, with a sequence length of 18 to predict, minimizing sample waste. This resulted in 212,982 training and 54,912 validation windows.

## Model Inspection 🕵️‍♂️
Our exploration of potential models was both extensive and varied, focusing on maximizing accuracy and efficiency. The initial lineup included sophisticated architectures such as Bidirectional LSTMs enhanced with Attention mechanisms, Convolutional Neural Networks (CNNs) in the form of 1D ResNets, and more traditional Feed Forward Neural Networks (FFNNs). The intricate dance between these models' ability to capture temporal dependencies and their computational demands was a constant consideration.

### Bidirectional LSTM + Attention
This model was a cornerstone of simplicity and effectiveness. It combined the temporal prowess of LSTM layers with the focused insight of attention mechanisms, yielding promising results without succumbing to overfitting—a testament to its balanced architecture.

### ResNet 1D with CBAM
Perhaps the most intricate of our experiments, this model harnessed the power of deep residual learning along with the nuanced focus of the Convolutional Block Attention Module (CBAM). It was a symphony of depth and attention, refining features in a way that seemed almost intuitive, catering to the nuanced demands of time-series forecasting.

![immagine](https://github.com/tombinic/Time-Series-Forecasting/assets/91635053/17762ce0-da8b-42e3-aa66-8291564e0e29)


## Hyperparameter Tuning ⚙️
Grid search was employed for tuning, with batch size and minimum learning rate being the primary focus. The tuned models exhibited closely matched performances.

## Ensemble 🤝
In our quest for excellence, we recognized the strength in unity. The ensemble model emerged as a beacon of collective intelligence, intertwining the predictions of our finely tuned models through an Average layer. This collaboration not only enhanced performance but also imbued our system with a robustness that was greater than the sum of its parts.

This fusion of models did not merely stack their predictions; it wove them into a cohesive tapestry, enhancing their individual strengths and mitigating their weaknesses. The ensemble's performance was a testament to the power of collective wisdom, achieving an unprecedented level of accuracy and reliability on our validation set.

![immagine](https://github.com/tombinic/Time-Series-Forecasting/assets/91635053/e2a69b8f-0a31-4c3c-8dba-8026660f496e)

## Tested Variations 🔬
Our relentless pursuit of improvement led us to experiment with a plethora of model variations and dataset manipulations. From autoregressive models to data augmentation with SMOTE, no stone was left unturned. Yet, it was in the measured combination of models within our ensemble that we found our greatest success.

## Results and Considerations 📊
The culmination of our efforts was an ensemble model that not only stood the test of validation but also showcased remarkable generalization across multiple test sets. Its performance was a beacon of hope, illuminating the path to reliable time-series forecasting.

![immagine](https://github.com/tombinic/Time-Series-Forecasting/assets/91635053/3c180eb9-2533-46ba-b491-ade6e3be00e2)

You can find all the details in the colab notebook and in the report. Clearly, there could be some errors due to missing file or path.

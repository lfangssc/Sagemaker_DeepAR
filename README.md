# Sagemaker_DeepAR_takeaway
## Introduction 
Sagemaker_DeepAR is the state of arts of time serires forecasting services that is built on autogressive recurrent Networks and probablic likelyhood functions. DeepAR distinct itself with other traditional time series tools on the cability of scale up predictions on hundreds to half million concureent and related time series objects, such as city traffic, electricty consumption over many users and demanding forecasting on e-commerce commodities. 

## Key advantagies
- minimal manual feature engineering is needed
- able to provide forecasts for items with little or no history at all

## Autoregressive recurrent network architecuture 
- The model architecture is a deriative of the recurrent neural network that predictions on Xt_((x_i,t), (zi, t-1)) where (zi, t-1) is the predicitons on time t-1.
- h is a function implemented by a multi-layer recurrent neuralnetwork with LSTMcells
- Likelyhood functions l(zi,t, theta i, t) are incorported before to make preditions, both Gaussian and negative-binomial functions are used.

![ ](DeepAR.png?raw=true "Title")



## Input training data format
The input training/validation data format has to be json, so Deep_AR can read it. The json has two sets of data, first is time series start time, all time series objects have to been exactely the same on the start time. The second set are the time series, each time series stored as a sub-list in a dictionary. The time series has no index in json, the index is defined in the programming. 

sample I:

    {"start": "2016-01-01 00:00:00", "target": [4.060090425547651, 4.2876683840699075, 5.0097648080473896, 4.622428881655526, 5.675623284953149, 5.284779108331383, 5.554938706311273, 5.391502655286226, 5.616676426581074, 4.672763017970261, 4.762090261430294, 4.431314588517882, 4.406623449882362, 3.5997065164592343, 3.470450696575033, 3.4060484619329623]}
    {"start": "2016-01-01 00:00:00", "target": [5.811951024150367, 6.648385923124836, 6.72514532560852, 7.3421294797729395, 7.067992454862794, 7.669970762433436, 8.113335497453377, 8.221950922958216, 7.598966639354628, 7.904253522825946, 7.348111979112986, 6.2792606976551575, 5.018446305200392, 4.610506010100085, 4.9376307565525295, 3.971589392128109]}

# Reference
[Time series forecasting with DeepAR - Synthetic data](https://github.com/awslabs/amazon-sagemaker-examples/blob/master/introduction_to_amazon_algorithms/deepar_synthetic/deepar_synthetic.ipynb)

[DeepAR: Probabilistic Forecasting with Autoregressive Recurrent Networks](https://arxiv.org/abs/1704.04110)

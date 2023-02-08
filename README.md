# Los Lobos
Welcome to our Shell projects public repo
  
# Overview
In this repo, we are trying to test out different codes we find to get used to GitHub. Therefore when we get more into pipeline codes for detecting anomolies, we are more educated and prepared for it.

# Current Code
This code below is an anomaly detection code, that prints out the "number/value" that is causing an issue within the dataset.

import numpy as np

def anomaly_detection(data, sigma_threshold=5):
    "Detects anomalies in the dataset provided using the sigma rule"

    sigma = np.std(data)
    mean = np.mean(data)
    anomalies = []
    for i in range(len(data)):
        if abs(data[i] - mean) > sigma_threshold * sigma:
            anomalies.append(data[i])
            return anomalies

def test_anomaly_detection():
    "Tests the anomaly detection function."

    data = list(np.random.randn(1000))
    data = data + [10]
    anomalies = anomaly_detection(data)
    print(anomalies)


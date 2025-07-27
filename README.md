# 🧠 Candlestick Pattern Classifier (SPY ETF)

This project leverages a Convolutional Neural Network (CNN) to automatically recognize classic candlestick patterns from SPY ETF charts. It was trained on synthetic data and tested on real-world SPY candlestick images.

Candlestick patterns have long been used by traders to guess where prices might go next. bullish? bearish? No one’s really sure. Books like Encyclopedia of Candlestick Charts claim some patterns work more often than not. Our model lets us put that to the test: we can scan the market, spot these patterns, and check if prices actually move the way the theory says. Time to see if old-school chart magic holds up under the microscope.

## 📊 Overview

- **Model architecture**: Simple CNN (3 Conv layers + Dense head)
- **Input**: 64x64 grayscale candlestick chart images
- **Output**: One of 9 candlestick pattern classes
- **Val accuracy**: ~95.33%
- **Framework**: TensorFlow / Keras


## 🏷️ Classes

The model is trained to detect the following 9 candlestick patterns:

- `bearish_spinning_top`
- `bullish_spinning_top`
- `dark_cloud_cover`
- `falling_three`
- `piercing_line`
- `random_pattern`
- `rising_three`
- `three_black_crows`
- `three_white_soldiers`

## 🔍 Real-World Testing

The model was tested on real SPY ETF candlestick charts. While we can't measure accuracy without labels, visual inspection showed strong qualitative results for most patterns.

### ✅ Correct Classifications:
- **bearish_spinning_top**: 100% confidence
- **bullish_spinning_top**: 100%
- **dark_cloud_cover**: 99.46%
- **piercing_line**: 78.91%
- **three_white_soldiers**: 82.12%
- **three_black_crows**: 42.07% (lower confidence but visually consistent)

### ⚠️ Inconsistent Cases:
- **falling_three** and **rising_three** were confidently predicted but not visually represented — showing potential model overconfidence on complex patterns.

## 📈 Why Candlestick Patterns Matter

Candlestick patterns are a widely used visual tool in technical analysis, helping traders interpret market sentiment and anticipate potential price reversals or continuations. Patterns like "three white soldiers" or "dark cloud cover" are believed to reflect psychological behavior of traders and are often used to time entries and exits.

While some view them as subjective, academic studies (e.g., [Marshall et al., 2006](https://www.sciencedirect.com/science/article/abs/pii/S1062940806000319)) have explored their statistical significance. Our deep learning model offers a way to put these theories to the test, by automatically detecting such patterns on real market data and evaluating their predictive value.

## 🤖 Model Architecture

We used a lightweight convolutional neural network (CNN) trained on grayscale images of candlestick sequences. The architecture:

- Input: `(64, 64, 1)` grayscale image
- 3 convolutional blocks with `ReLU` activations and `same` padding
- Global average pooling for regularization
- Fully connected dense layer
- Output layer with 9 softmax classes

The use of `ReLU` helps avoid vanishing gradients and speeds up training, while `same` padding preserves image dimensions, simplifying the learning process.

## 🧪 Dataset

Synthetic data was generated for each candlestick pattern using controlled simulations. Each pattern was drawn using a rolling sequence of 10 candles and saved as an image. This approach allows balanced class distributions and full control over the visuals — but it also introduces a limitation: **no real-world market noise**.

## 💡 Future Work

- I won't tell you or you will steal my edge on the market ;)

## 📬 Contact

For any questions or collaboration ideas, feel free to reach out !.

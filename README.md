# Price-Forecasting-With-Neural-Networks

Using Microsoft Stocks, gathered from:
https://finance.yahoo.com/quote/MSFT/history?p=MSFT


This project creates several neural network models with different architectures to forecast the next day closing price, based of an interval of past days. 

## Installing Dependencies (Linux)

```bash
    sudo apt install python3-pip
    
    pip install --upgrade pip
    
    pip install --upgrade jupyter
    
    pip install --upgrade jupyter nbconvert

    pip install --upgrade numpy

    pip install --upgrade pandas

    pip install --upgrade matplotlib

    pip install --upgrade scikit-learn

    pip install --upgrade tensorflow

    pip install --upgrade h5py
```

## Create Slide Apresentation

```bash
    jupyter nbconvert Prices.ipynb --to slides --SlidesExporter.reveal_scroll=True
```

## Details

After preprocessing data, removing NaN and extra columns, the prices are gathered into groups. So, for each row, there are 16 consecutive days, 15 used for the problem input and the last one for the output. Therefore, the problem type consists of a supervised regression.

To speed up model training and generalize the model capabilities, all data are standarized using the StandardScaler() from sklearn.

Four different models are used for this problem:
    1. CNN + LSTM + DNN
    2. LSTM + DNN
    3. CNN + DNN
    4. DNN

For evaluation, the sliding window cross validation technique was used. And the computed metrics were:
    Root Mean Square Error (RMSE)
    Mean Absolute Error (MAE)
    Mean Absolute Percentege Error (MAPE)
    Coefficient of Determination (R2)
    Accuracy (Acc)

For Accuracy, which is a classification metric, the considered labels were if the day-to-day price change was negative or non-negative. 

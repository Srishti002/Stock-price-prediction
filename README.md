# Stock price prediction
## Introduction 
   In ANN, sequence doesn't matter or chronology of features in a input don't matter. But in stock price prediction, sequence matters as we have to see when at what time the price is going down or high. So, we use LSTM (Long Short Term Memory) here.

## LSTM Core Idea :-
   In LSTM the core idea is to have some short term memory and long term memory as in RNN (Recurrent Neural Networks) the only problem was that if data is large then while forward process, it keeps on forgetting previous values. So, this is problem of vanishing and 
   exploding gradient. So, to not forget the particular values, we store them in *long term memory* and rest as usual called *short term memory*. In LSTM we have complex architecture as we have to establish connection between long term memory and short term memory.

   ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20002525.png)

   
- The LSTM architecture is divided into 3 gates known as *Forget gate, Input gate, Output gate*.
- Here, ht(hidden state) and Ct(cell state) are vector are vectors and dimensions of these two should be same.
  
   1. Forget Gate:
      

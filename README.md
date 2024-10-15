# Stock price prediction
## Introduction 
   In ANN, sequence doesn't matter or chronology of features in a input don't matter. But in stock price prediction, sequence matters as we have to see when at what time the price is going down or high. So, we use LSTM (Long Short Term Memory) here.

## LSTM Core Idea :-
   In LSTM the core idea is to have some short term memory and long term memory as in RNN (Recurrent Neural Networks) the only problem was that if data is large then while forward process, it keeps on forgetting previous values. So, this is problem of vanishing and 
   exploding gradient. So, to not forget the particular values, we store them in *long term memory* and rest as usual called *short term memory*. In LSTM we have complex architecture as we have to establish connection between long term memory and short term memory.

   ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20002525.png)

   
- The LSTM architecture is divided into 3 gates known as *Forget gate, Input gate, Output gate*.
- Here input consists from input from previous cell state, previous hidden state, input for the currnet time t1.
- Here, ht(hidden state) and Ct(cell state) are vectors and dimensions of these two should be same.
  
  1. ## Forget Gate:
      
      ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20002949.png)

      - Forget gate is used to remove values of Cell State ( Long Term Memory)
      - Calculate *'ft'* as ft = sigmoid( Wf [ht-1 , Xt] + bf)
      - Now *'ft * Ct-1'*

  2. ### Input Gate:

     ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20003007.png)

      - This gate is used to add values to Cell state(Long term Memory)
      - it = sigmoid( Wi [ht-1 , Xt] + bi )
      - C't = tanh( Wc [ht-1 , Xt] + bc)
      - Pointwise * it * C't *
      - Point wise *[ ft * Ct-1 ] + [ it * C't]*

  3. ### Output Gate:

     ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20003033.png)

      - Ot = sigmoid ( Wo [ ht-1 , Xt ] + Bo)
      - Pointwise ht = Ot * tanh ( [ft * Ct-1] + [ it * C't ] )
    
## Step by Step guide :-
   1. ### Dataloading and preprocessing :
      - Using *yfinance* library of python , we download *'GOOGL'* Stock data for the last three years.
        
        ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20194840.png)

        ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20194907.png)

      - This is how our data looks like
        
        ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20195249.png)

      - Now we drop some columns and add a new column named *'date'* whose values are directly copied DataFrame's index

        ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20195737.png)

        ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-15%20195808.png)

      - We have to prepare our data like we have to make sequences from the given data 


 2. ### Model :-

    ![](https://github.com/Srishti002/Stock-price-prediction/blob/main/Screenshot%202024-10-16%20002137.png)

        

      
       
      
      

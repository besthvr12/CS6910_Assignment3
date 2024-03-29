# CS6910_Assignment3
Here in this Repo there are 4 Files of .ipynb to in which two of them are sweeps and two of them are trained on best model. One of them is trained with attention best parameters and one of them is trained Vanilla RNN best parameters. 
| File Name                        | Description                                                                               |
|----------------------------------|-------------------------------------------------------------------------------------------|
| ` 1. Seq2Seqwith Sweep.ipynb`        | Sweep without using Attention.                                                        |
| ` 2. best_model_vanilla_rnn.ipynb`   | Test using best hyperparameters of Vanialla RNN.                                      |
| ` 3. Attetnion_Sweep.ipynb`          | Sweep Using Attention.                                                                |
| ` 4. best_model_attention.ipynb`     | Test using best hyperparameters of Attention.                                         |

1. Seq2Seqwith Sweep.ipynb
<kbd>
<div style="border: 1px solid #e1e4e8; border-radius: 6px; padding: 10px; font-size: 24px;">
  
  - The Seq2Seqwith Sweep.ipynb has following functions and class:
  
    - This file has contain the code related to Question Number 1 to 3.  
    - In this .ipynb file I have trained vanilla RNN and then run sweeps. First I have downloaded the dataset and uploaded it on Kaggle.
    - Then data preprocessing by converting data into tensors.
    - Now i have created a seprate class for each RNN, GRU and LSTM and running sweeps on below sweep configurations.
    - Using beam search and beam width to find the most probables outputs.
    - Now to run the file in the end TA's can find the wandb import they just need to change it by giving their key and then they can get all the results mentions.
    - Now just run the whole code from the start.
    
</div>
</kbd>
 
2. best_model_vanilla_rnn.ipynb
<kbd>
<div style="border: 1px solid #e1e4e8; border-radius: 6px; padding: 10px; font-size: 24px;">
  
  - The best_model_vanilla_rnn has following functions and class:
  
    - This file has contain the code related to Question Number 4.  
    - In this .ipynb file I have trained vanilla RNN and then run sweeps. First I have downloaded the dataset and uploaded it on Kaggle.
    - Then data preprocessing by converting data into tensors.
    - Now i have use here LSTM only since it was giving best results so all the runs here are on LSTM only.
    - Now to run the file in the end TA's can find the wandb import they just need to change it by giving their key and then they can get all the results mentions.
    - In this code at last csv file will be generated for that TA's need to put some appropriate location.
      ### Best Sweep 1 Hyperparameters:
      <h4 style="font-size: 30px;">
  
             | Hyperparameter   | Chosen Value |
             |------------------|--------------|
             | embedding_size   | 512          |
             | epochs           | 40           |
             | hidden_size      | 512          |
             | batch_size       | 512          |
             | enc_num_layers   | 3            |
             | dropout          | 0.3          |
             | dec_num_layers   | 3            |
             | cell_type        | LSTM         |
             | beam_search      | 3            |
       </h4>
  <br>
    
</div>
</kbd>

Sweeps Parameters Used in Vanilla RNN : 


```python
sweep_config = {
    'method': 'bayes',
    'metric': {'goal': 'maximize', 'name': 'val_accuracy'},
    'parameters': {
        'embedding_size': {'values': [128, 256, 512]},
        'epochs' :{'values':[10,20,30,40]},
        'hidden_size': {'values': [128, 256, 512]},
        'batch_size': {'values': [128,256,512]},
        'enc_num_layers': {'values': [1,2,3]},
        'dropout': {'values': [0.1, 0.2, 0.3, 0.4]},
        'dec_num_layers':{'values': [1,2,3]},
        'cell_type': {'values': ['LSTM','GRU','RNN']},
        'beam_search':{'values':[1,2,3,4,5]}
    }
}
```
3. Attention_With_Sweeps.ipynb
<kbd>
<div style="border: 1px solid #e1e4e8; border-radius: 6px; padding: 10px; font-size: 24px;">
  
  - The Attention_With_Sweepsipynb has following functions and class:
  
    - This file has contain the code related to Question Number 5(a,b,c).  
    - In this .ipynb file I have trained Attention Model and then run sweeps. First I have downloaded the dataset and uploaded it on Kaggle.
    - Then data preprocessing by converting data into tensors.
    - Now i have created a seprate class for each Attention RNN, Attention GRU and Attention LSTM and running sweeps on below sweep configurations.
    - Using beam search and beam width to find the most probables outputs.
    - Now to run the file in the end TA's can find the wandb import they just need to change it by giving their key and then they can get all the results mentions.
    - Now just run the whole code from the start.
    
</div>
</kbd>
4. best_model_attention.ipynb
<kbd>
<div style="border: 1px solid #e1e4e8; border-radius: 6px; padding: 10px; font-size: 24px;">
  
  - The best_model_vanilla_rnn has following functions and class:
  
    - This file has contain the code related to Question Number 5(c,d).  
    - In this .ipynb file I have trained Attention Models and then run sweeps. First I have downloaded the dataset and uploaded it on Kaggle.
    - Then data preprocessing by converting data into tensors.
    - Now i have use here RNN and GRU here because it was taking large time to train in attention
    - Now to run the file in the end TA's can just run the file by adding data appropriate position.
    - In this code at last csv file will be generated for that TA's need to put some appropriate location.
      ### Best Sweep 1 Hyperparameters:
      <h4 style="font-size: 30px;">
  
             | Hyperparameter   | Chosen Value |
             |------------------|--------------|
             | embedding_size   | 512          |
             | epochs           | 30           |
             | hidden_size      | 512          |
             | batch_size       | 256          |
             | enc_num_layers   | 1            |
             | dropout          | 0.1          |
             | dec_num_layers   | 3            |
             | cell_type        | GRU or RNN   |
             | beam_search      | 2            |
       </h4>
  <br>
    
</div>
</kbd>

```python
sweep_config2 = {
    'method': 'bayes',
    'metric': {'goal': 'maximize', 'name': 'val_accuracy_with_attention'},
    'parameters': {'embedding_size_input': {'values': [128, 256, 512]},
                   'hidden_size_EncDec': {'values': [128, 256, 512]},
                   'cell_type_value': {'values': ['LSTM','GRU','RNN']},
                   'batch_size_value': {'values': [128,256,512]},
                   'dropout_EncDec': {'values': [0.1, 0.2, 0.3, 0.4]},
                   'Number_Epochs' :{'values':[10,20,30,40]},
                   'beam_width':{'values':[1,2,3,4,5]}
                }
                }
```
Now there are two folders named as Pytorch_Vanilla and Pytorch_Attention which contain the csv files of the reuslts on the test dataset.
Report Link : https://api.wandb.ai/links/harshvrma/pp9nabpf 

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
<div style="border: 1px solid #e1e4e8; border-radius: 6px; padding: 10px;font-size: 20px;">
  
  - The repository contains the following files:
 
    - `sweep_1.ipynb`: A Jupyter Notebook file for sweep 1.
    - `sweep_2.ipynb`: A Jupyter Notebook file for sweep 2.
    - `best_model_attention.ipynb`: A Jupyter Notebook file trained on the best model with attention using the best parameters.
    - `best_model_vanilla_rnn.ipynb`: A Jupyter Notebook file trained on the best model with Vanilla RNN using the best parameters.
    
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


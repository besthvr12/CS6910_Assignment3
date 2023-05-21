# CS6910_Assignment3
Here in this Repo there are 4 Files of .ipynb to in which two of them are sweeps and two of them are trained on best model. One of them is trained with attention best parameters and one of them is trained Vanilla RNN best parameters. 
| File Name                        | Description                                                                               |
|----------------------------------|-------------------------------------------------------------------------------------------|
| `sweep_1.ipynb`                  | A Jupyter Notebook file for sweep 1.                                                     |
| `sweep_2.ipynb`                  | A Jupyter Notebook file for sweep 2.                                                     |
| `best_model_attention.ipynb`     | A Jupyter Notebook file trained on the best model with attention using the best parameters.|
| `best_model_vanilla_rnn.ipynb`   | A Jupyter Notebook file trained on the best model with Vanilla RNN using the best parameters.|

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


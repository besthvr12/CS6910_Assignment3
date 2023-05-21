# CS6910_Assignment3
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

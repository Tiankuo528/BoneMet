# Using BoneMet with other Experiments

We will be demonstrating how our dataset BoneMet can be used in other experiments, specifically reconstructing an x-ray with medNerf.


# Loading the Dataset
Begin by loading the BoneMet dataset. You can load the entire dataset with 
```
from datasets import load_dataset
dataset = laod_dataset("BoneMet/BoneMet")
```
You can also specify certain directories if you only need a certain subset of the dataset. When reconstructing x-ray's with medNerf, we will only need x-ray data:
```
dataset = load_dataset("BoneMet/BoneMet", data_dir = "Imagery_Dataset/1. Rotation-X-ray/851/week 0")
```
The dataset will be cached in `C:\Users\<User>\.cache\huggingface\hub\datasets--BoneMet--BoneMet`. 
## Using with MedNerf

After downloading the dataset, open the `knee.yaml` file found in the configs folder. Change the `datadir` field to the file location of the downloaded dataset. Now, in the `graf-main` directory you can run the `train.py` file with BoneMet data. Use the following command to run the script.
```
python train.py ./configs/knee.yaml
```

## Acknowledgements

We want to thank the authors of the mednerf repo for their hard work and the wonderful code.



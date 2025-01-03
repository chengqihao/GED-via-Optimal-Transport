# GED Computation with Optimal Transport
Source codes of 'Computing Approximate Graph Edit Distance via Optimal Transport'，accepted by SIGMOD'25 Round3

## Getting Started
### Requirements
All codes are implemented in python3.9

```
dgl                       1.0.2
pot                       0.8.2
networkx                  3.1
numpy                     1.26.4
scipy                     1.12.0
pytorch                   2.2.2+cpu
pyg                       2.5.2 
torchvision               0.17.2
texttable                 1.6.4
tqdm                      4.65.0
```
### Code Running
#### Datasets
The datasets utilized in this study are AIDS, Linux and IMDB. These datasets are provided in the directory `./json_data`. The ground-truth GEDs and node matching are stored in the file `TaGED.json`

#### Training
An example of training GEDIOT on AIDS for 20 epochs
```
python src/main.py --model-name GEDIOT --dataset AIDS --model-epoch-start 0 --model-epoch-end 20 --model-train 1
```
The parameter `model-name` can be replaced by `GedGNN`, `TaGSim`, `GPN` and `SimGNN`
#### Testing
An example of testing GEDIOT, GEDHOT and GEDGW on AIDS. GEDIOT and GEDHOT use the 20-th epoch model
```
python src/main.py --model-name GEDIOT --dataset AIDS --model-epoch-start 20 --model-epoch-end 20 --model-train 0 --path
python src/main.py --model-name GEDHOT --dataset AIDS --model-epoch-start 20 --model-epoch-end 20 --model-train 0 --GW --path
python src/main.py --model-name GEDGW --dataset AIDS --GW --path
```

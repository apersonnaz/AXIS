# AXIS
Automated crystal identification system developed in EMBL Grenoble Marquez group by Aurélien Personnaz.

## Installation
Create a python virtual environment and install the dependencies.

```
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Install correct pytorch version for your environment from [there](https://pytorch.org/get-started/locally/)

The models are pulled and stored in the [HuggingFace repository](https://huggingface.co/)

You will need to sign up and get a write token.

## Training
If you want to log the training in wandb you need to login first:
`wandb login`
The wandb entity and project name can be passed by setting the environment variables WANDB_ENTITY and WANDB_PROJECT
```
export WANDB_ENTITY=*your entity*
export WANDB_PROJECT=*your project*
```

The HuggingFace token must be passed with the environment variable HUGGINGFACE_TOKEN
```
export HUGGINGFACE_TOKEN=*your token*
```

Then run a training with the training.py script.

Example:
`python training.py --n_epoch 2 --train_dataset ~/data/CRIMS-v1 --test_dataset ~/data/CRIMS-test`

## Inference
You can run a simple inference by executing

`python infer.py test_image.jpg`
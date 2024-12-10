# The Game
We have designed a game that's about making an AI model say a specific word, which is quite fun and sometimes trickier than one might imagine.

# Models
We have trained three models in our exploratory study of the possibilities of fine-tuning.

## Common hyperparameters:
Base lr: 2e-4

r=16

gradient accumulation steps: 4

Optimizer: 8 bit Adam

weight_decay = 0.01

## DrDomedag/LocoLamav3
Description: An ambitious attempt to train on the full Tome dataset. The fact that the overhead ended up being around one hour stopped this attempt, but the model is still not terrible.

Trained on: The Tome (https://huggingface.co/datasets/arcee-ai/The-Tome)

Training epochs: ~0.1

Hyperparameters emphasising speed:

4-bit quantization

warmup steps: 5

lr-scheduler-type: linear

## T3lli/Test
Description: Using a more fit-for-purpose dataset containing human dialogue, the speed of training it enabled drove us to train it for a full 10 epochs, leading to significant forgetfulness and loss of performance.

Trained on: DIALOGSum (https://huggingface.co/datasets/knkarthick/dialogsum)

Training epochs: 10 epochs

No quantization (16 bit floating point parameters)

lr-scheduler-type: linear

warmup steps: 5

## T3lli/HumanDialog
Description: Also trained on the smaller dataset but for a shorter time and with slightly tuned hyperparameters, this is subjectively our best performing model.

Trained on: DIALOGSum (https://huggingface.co/datasets/knkarthick/dialogsum)

Training epochs: 3 epochs

No quantization (16 bit floating point parameters)

lr scheduler type: Cosine

warmup steps: 100

# UI
## Main UI
The UI/application is hosted at the below HuggingFace space:

https://huggingface.co/spaces/DrDomedag/LocoLama2 (set up with DrDomedag/LocoLamav3)

## Running it locally
Since HuggingFace can be moody at times, using this repository will allow you to run the UI locally:

https://github.com/DrDomedag/LocoLamaInferenceApp (set up with DrDomedag/LocoLamav3)

##Backup UI
While it does not have the full accoutrements of the main UI, this Gradio based UI for some inexplicable reason seems to suffer fewer issues with the HuggingFace model not responding in time.
https://huggingface.co/spaces/T3lli/iris (set up with T3lli/HumanDialog)


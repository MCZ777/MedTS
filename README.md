# MedTS
This repository contains codes and models for the paper: 

MedTS: A BERT-based Generation Model to Transform Medical Texts to SQL Queries for Electronic Medical Records

## Requirements

#### Environments

```
pytorch >= 1.4.0
transformers == 3.0.2
nltk, numpy, tqdm, matplotlib, idna, tushare, sqlalchemy, pandas, 
boto3, requests, regex, more_itertools, interval, translate, num2words
```

## Data preparation
We provide the processed dataset in ./data, including train, validation and test sets.

The original dataset can be found from [TREQS](https://github.com/wangpinggl/TREQS).

## Training
* run ./train.sh to train the model.

```
python -u ./src/train.py \
  --dataset $DATA_DIR \
  --train_data $TRAIN_DATA_PATH \
  --epoch $EPOCH_NUM \
  --save $SAVED_MODEL_DIR \
  --cuda \
  --cuda_device_num $DEVICE_NUM\
```

## Predicting

* run ./predict.sh to get the prediction on the validation/test set.

```
python -u ./src/predict.py \
  --dataset $DATA_DIR \
  --eval_data $PREDICT_DATA_PATH \
  --model_dir $SAVED_MODEL_DIR \
  --model $SAVED_MODEL_NAME \
  --output_dir $OUTPUT_DIR \
  --cuda \
  --cuda_device_num $DEVICE_NUM \
```

## Evaluation
The details of evaluation can be found in [TREQS_evaluation](https://github.com/wangpinggl/TREQS), which is based on the publicly available real-world de-identified [Medical Information Mart for Intensive Care III (MIMIC III)](https://mimic.mit.edu/gettingstarted/access/) dataset.

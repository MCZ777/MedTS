# MedTS
This repository contains codes and models for the paper: 
MedTS: a BERT-based Medical Text-to-SQL Generation Method with Incorporating Tree-structured Intermediate Representation

## Requirements

#### Environments

```
pytorch >= 1.4.0
transformers == 3.0.2
nltk, numpy, tqdm, matplotlib, idna, tushare, sqlalchemy, pandas, 
boto3, requests, regex, more_itertools, interval, translate, num2words
```

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

# BirdFSD-YOLOv5


## Setup

```shell
git clone https://github.com/bird-feeder/BirdFSD-YOLOv5.git
cd BirdFSD-YOLOv5

pip install -r requirements.txt
git clone https://github.com/ultralytics/yolov5.git
```

## Dataset preparation

```shell
python json2yolov5.py
mv dataset-YOLO/dataset_config.yml .
python utils/relative_to_abs.py
```

## Training[^1]

```shell
WEIGHTS=
wget $WEIGHTS -qO best.pt

EPOCHS=30
BATCH_SIZE=16
PRETRAINED_WEIGHTS="<weights_download_link>"  # or one of the pretrained models if \
                                              # running for the first time (see footer)

python yolov5/train.py --img-size 768 --batch $BATCH_SIZE --epochs $EPOCHS \
    --data "dataset_config.yml" --weights $PRETRAINED_WEIGHTS
```

[^1]: [yolov5/wiki/Train-Custom-Data](https://github.com/ultralytics/yolov5/wiki/Train-Custom-Data)

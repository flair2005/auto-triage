# `auto-triage`

## Introduction
This project is a reproduction of the `SIGGRAPH 2016` paper `Automatic Triage for a Photo Series` written in `Python` with the help of `Keras` and `TensorFlow`.

## Structure
```
data/             # benchmark dataset (Princeton Adobe photo triage dataset)
| demos/          # three demo scenarios (jpeg files)
| download.sh     # data downloading and preparation
src/              # source code
| data.py         # data loading and preprocessing
| models.py       # models with different settings
| train.py        # script for training
| evaluate.py     # script for evaluation
| predict.py      # script for prediction
```

## Usages

### Requirements
* `Python 2.7`
* `OpenCV 2`
* `Keras 2.0+`
* `TensorFlow 1.0+`

### Training
```bash
python train.py <options>
```

#### Options

```
--exp            experiment identifier (default: default)
--gpu            GPU used for training (default: 0)
--epochs         number of training epochs (default: 16)
--batch          mini-batch size (default: 4)
--model          model (default: vgg16)                          (vgg16 | vgg19 | resnet50)
--siamese        weight sharing (default: share)                 (share | separate)
--weights        transfer learning (default: imagenet)           (imagenet | random)
--module         feature interaction (default: subtract)         (subtract | bilinear | neural)
--activation     activation function (default: tanh)             (tanh | relu)
--regularizer    regularizatiation function (default: l2)        (l2 | none)
```

### Evaluation

```shell
python evaluate.py <options>
```

#### Options

```
--exp            experiment identifier (default: default)
--gpu            GPU used for training (default: 0)
```

### Prediction

```
python predict.py <options> <image-list>
```

#### Options

```
--exp            experiment identifier (default: default)
--gpu            GPU used for training (default: 0)
```

## License

This project is released under the [open-source MIT license](https://github.com/zhijian-liu/auto-triage/blob/master/LICENSE).

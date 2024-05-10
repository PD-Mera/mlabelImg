# Adapted LabelImg for Enhanced User Experience

This repository is a copy from [HumanSignal/labelImg](https://github.com/HumanSignal/labelImg). The original repository is archived and no longer being maintained. So I make a copy from the latest version (1.8.6) to modify some function and fix some error for personal use.

[Original README](./original_README.rst)

## Installation

### Install with pip

``` bash
pip install -U mlabelImg
```

### Install from source

``` bash
git clone https://github.com/PD-Mera/mlabelImg
pip install pyqt5 lxml
pyrcc5 -o mlabelImg/libs/resources.py mlabelImg/resources.qrc
pip install -e mlabelImg
```

## Usage

### Setup directory

Create a folder structure same as below

```
├── data
    ├── images
    └── labels
```

Put all of your image in `images` directory. And create a `classes.txt` contain all class you want to label. Example of `classes.txt` as below

``` txt
dog
cat
pig
```

Put `classes.txt` in 2 place, in `labels` directory and same level as `labels` directory

Full structure of workspace as below

```
├── data
    ├── images
    │   ├── img1.jpg
    │   ├── img2.jpg
    │   └── ...
    ├── labels
    │   └── classes.txt
    └── classes.txt
```

### Run mlabelImg

Run mlabelImg with

``` shell
# mlabelImg [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
mlabelImg .\data\images\ .\data\classes.txt
```

On GUI of labelImg: 

- `File -> Change Save Dir -> (save label directory)`
- Choose `YOLO` format on the left tray

Next and previous image with `D -> A`

Label with `W`

Delete `.\data\classes.txt` after labeling

### Label format

With `YOLO` format, label will be saved with format `label_index x_center y_center w h` and normalize to scale `[0, 1]`

``` txt
1 0.415842 0.863095 0.102970 0.101190
1 0.228713 0.315476 0.077228 0.053571
1 0.756436 0.328869 0.114851 0.050595
```

## Reference

- Author: TzuTa Lin
- Author Email: tzu.ta.lin@gmail.com
- [tzutalin/labelImg](https://github.com/tzutalin/labelImg)
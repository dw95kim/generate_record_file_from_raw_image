# generate_record_file_from_raw_image
## Requirement Version

```
python 2.7
OpenCV >= 3.0
numpy, tqdm, lxml
```

## Open Labeling (png or jpg to xml)

```
1. input folder 에 image 나 video 넣기

2. class_list.txt 파일에 class 구분하여 넣기 (one class name per line)

3. python main.py
```

## GUI usage (Keyboard / Mouse)
```
keyboard
a/d : previous/next image
s/w : previous/next class
e : edges
h : gelp
q : quit

Mouse
Right-click -> quick delete
middle mouse -> zoom
double click -> bounding box
```

## Precaution
```
1. 만들때 모든 파일 포맷을 같은 것으로 하기 (jpg or png)

2. 사이즈도 최대한 맞추기

3. images/train/ 폴더 안에는 jpg와 xml 파일 겹쳐서 두기
```

## Generate record file from xml

```
1. xml 에서 csv 파일 만들기
python xml_to_csv.py
(input : images/train/  --> output : images/)

2. csv 파일에서 pbtxt 파일 만들기
python generate_pbtxt.py 'csv' images/train_labels.csv images/train_labels.pbtxt

3. 있는 파일로 record 파일 만들기
python generate_tfrecord.py --csv_input=images/train_labels.csv  --image_dir=images/train --output_path=test.record
```

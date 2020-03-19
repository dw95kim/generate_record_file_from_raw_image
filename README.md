# generate_record_file_from_raw_image
## Requirement Version

```
python2.7
```

## Open Labeling (png or jpg to xml)

```
1. openlabeling 으로 xml 파일 만들기

2. 만들때 모든 파일 포맷을 같은 것으로 하기 (jpg or png)

3. 사이즈도 최대한 맞추기
```

## Generate record file from xml

```
1. xml 에서 csv 파일 만들기
python xml_to_csv.py

2. csv 파일에서 pbtxt 파일 만들기
python generate_pbtxt.py [-h] 'csv' data/train_labels.csv data/train_labels.pbtxt

3. 있는 파일로 record 파일 만들기
python generate_tfrecord.py data/train_labels.csv data/train_labels.pbtxt images/image_train/ ./
```

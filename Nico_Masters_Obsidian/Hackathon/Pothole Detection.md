
Useful link for custom segmentation YOLOv8 algorithm can be found [here](https://www.youtube.com/watch?v=Fe8W2lNTnU4)


# Trained Model on 8 pictures for testing
Trained Model on 8 pictures for following API  Key:
```Jupiter
!pip install roboflow

                    from roboflow import Roboflow
                    rf = Roboflow(api_key="klxp8JYFP4iqVNmIG9Qr")
                    project = rf.workspace("nicopotholledetection").project("yolov8segnico")
                    version = project.version(1)
                    dataset = version.download("yolov8")
                
```

```terminal
curl -L "https://app.roboflow.com/ds/N3At6pCSZL?key=MpQ94zR2D3" &gt; roboflow.zip; unzip roboflow.zip; rm roboflow.zip
```

```RAW URL
https://app.roboflow.com/ds/N3At6pCSZL?key=MpQ94zR2D3
```

Install Dependencies in VSCode using:
```Shell
py -m pip  install ultralytics
```
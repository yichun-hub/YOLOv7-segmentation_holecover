# YOLOv7-segmentation_holecover
  ## Detail informaion can be browsed on my [Medium](https://medium.com/@fearless_fusion_snake_755/yolov7-instance-segmentation-%E8%A8%93%E7%B7%B4%E6%95%99%E5%AD%B8-3b9059aafe8a).
  ## 1. Converts the format of VGG Image Annotator (VIA) to the YOLOv7 segmentation format.
  Classes:manhole, handhole
  code of format coversion: link

  ## 2. Modify data.yaml
  Modify a yaml file for the classes of the custom dataset in `yolov7-mask/data/`
  give images and labels path and classes.

  ## 3. Training
      python segment/train.py --data ./data/data.yaml --batch 16 --weights ./runs/train-seg/yolov7-seg/weights/last.pt  --cfg yolov7-seg.yaml --epochs 100 --name yolov7-seg --img 640 --hyp hyp.scratch-high.yaml
      
  ## 4. Evaluation
      python segment/predict.py --weights ./runs/train-seg/yolov7-seg2/weights/best.pt --source /content/drive/MyDrive/final_hole/images/val/170727_020736227_Camera_4.jpg --iou-thres 0.5 --conf-thres 0.6
      
  ## 5. Visulization  
      python segment/val.py --weights ./runs/train-seg/yolov7-seg2/weights/best.pt --data ./data/data.yaml --iou-thres 0.5 --conf-thres 0.6
      
  ## 6. Result
 
  Manhole
  ![image](https://github.com/yichun-hub/YOLOv7-segmentation_holecover/blob/main/result/200724_023433016_Camera_2.jpg)
  
  Handhole
  
  ![image](https://github.com/yichun-hub/YOLOv7-segmentation_holecover/blob/main/result/200707_033718669_Camera_1.jpg)

# LocalizadorPatentes

## ¿Qué es YOLO?

YOLO v4 es un one-stage object detector (a diferencia de los two-stage, no tiene Region Proposal Networks). YOLO es rapido y preciso.
Por el entrenamiento de distintas escalas de imagenes (multi-scale training) se pueden usar los mismos weights/parametros aprendidos para imagenes de distintas resoluciones. Cabe rescatar que mayor la resolución, mayor el costo de computación (Cada filtro de la CNN tiene que pasar mas veces -> mayores (MAC)[https://en.wikipedia.org/wiki/Multiply%E2%80%93accumulate_operation])

## Entrenamiento

El modelo fue entrenado con los siguientes datasets:
- [x] [OpenImages](https://storage.googleapis.com/openimages/web/download.html)
- [x] [Romanian Dataset of License Plates](https://github.com/RobertLucian/license-plate-dataset)
- [x] [OpenALPR benchmark dataset](https://github.com/openalpr/benchmarks)
- [ ] [CCPD Chinese City Parking Dataset, ECCV](https://github.com/detectRecog/CCPD)

Los detalles de entramiento se encuentran en el yolov4_custom.cfg.
Se uso 448x448 para (height,width), con random=1 (multi-scale training) y mosaic=1 (Mosaic Data Augmentation)

## Como usarlo

Para descargar, compilar y usar YOLO v4 seguí el (tutorial oficial)[https://github.com/AlexeyAB/darknet]
Para las patentes usa la .cfg y .weights provista en este repo.

## Citas

`
@inproceedings{xu2018towards,
  title={Towards End-to-End License Plate Detection and Recognition: A Large Dataset and Baseline},
  author={Xu, Zhenbo and Yang, Wei and Meng, Ajin and Lu, Nanxue and Huang, Huan},
  booktitle={Proceedings of the European Conference on Computer Vision (ECCV)},
  pages={255--271},
  year={2018}
}
`

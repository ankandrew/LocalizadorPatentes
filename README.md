# LocalizadorPatentes

## ¿Qué es YOLO?

YOLO v4 es un one-stage object detector (a diferencia de los two-stage, no tiene Region Proposal Networks). YOLO es rapido y preciso.
Por el entrenamiento de distintas escalas de imagenes (multi-scale training) se pueden usar los mismos weights/parametros aprendidos para imagenes de distintas resoluciones. Cabe rescatar que mayor la resolución, mayor el costo de computación (Cada filtro de la CNN tiene que mas pasadas)

## Entrenamiento

El modelo fue entrenado con los siguientes datasets:
- [x] [OpenImages](https://storage.googleapis.com/openimages/web/download.html)
- [x] [Romanian Dataset of License Plates](https://github.com/RobertLucian/license-plate-dataset)
- [x] [OpenALPR benchmark dataset](https://github.com/openalpr/benchmarks)
- [ ] [CCPD Chinese City Parking Dataset, ECCV](https://github.com/detectRecog/CCPD)

Los detalles de entramiento se encuentran en el yolov4_custom.cfg.
Se uso:
* 448x448 para (height,width)
* random=1 (multi-scale training)
* mosaic=1 (Mosaic Data Augmentation)

## Gráfico del entrenamiento
<img src="training_chart.png" width="480" height="480">

** No se muestra validation loss no se uso mientras se entrenaba. Se valido luego en dataset de prueba de OpenImages (VehiclePlates)

###### Resultados de la validación (448x448)

| Iteracion  | mAP |
| ----------- | ----------- |
| 1000  | 0.7763  |
| 2000  | 0.8487  |
| 3000  | 0.8699  |
| 4000  | 0.8701  |
| 5000  | 0.8714  |
| 6000  | **0.8760**  |
| 7000  | 0.8698  |
| 8000  | 0.8614  |

Luego de la 6000 iteración empiezar a decaer el performance ([over-fitting](https://en.wikipedia.org/wiki/Overfitting))

*Nota: El .weights es el modelo correspondiente a la iteración 6000*

## Como usarlo

Para descargar, compilar y usar YOLO v4 seguí el [tutorial oficial](https://github.com/AlexeyAB/darknet)

Solo hay que utilizar el [.cfg](yolov4-custom.cfg) y .[weights](https://ufile.io/3fbpbqfh) provista en este repo.

## Citas

```
@inproceedings{xu2018towards,
  title={Towards End-to-End License Plate Detection and Recognition: A Large Dataset and Baseline},
  author={Xu, Zhenbo and Yang, Wei and Meng, Ajin and Lu, Nanxue and Huang, Huan},
  booktitle={Proceedings of the European Conference on Computer Vision (ECCV)},
  pages={255--271},
  year={2018}
}
```

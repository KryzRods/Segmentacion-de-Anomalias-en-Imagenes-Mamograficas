# Segmentación de Anomalías en Imágenes Mamográficas con el Modelo LiteMedSAM
LiteMedSAM es un nuevo modelo de segmentación de imagenes médicas

En este repositorio se encuentran los códigos utilizados para el preprocesamiento de imágenes médicas en la tesis de *Segmentación de Anomalías en Imágenes Mamográficas con el Modelo LiteMedSAM* escrita por Krystian Rodriguez Santos, alumno de la Facultad de Ciencias Físico Matemáticas de la BUAP. 

El articulo original se puede enconntrar en [MedSAM](https://www.nature.com/articles/s41467-024-44824-z) 

En el siguiente [Colab](https://colab.research.google.com/drive/1HmTyEg0C95yRnA-MFfwjZZku57yeaCsy?usp=sharing) se encuetran todos los codigos para su ejeción aplicando un conjunto de imagenes. 

El modelo afinado se pude encontrar en [mamografía](https://drive.google.com/drive/folders/10hDzl3oqbeozg6eF8umF9gYYLBv65qBd?usp=sharing), el cual ya pude ser implementado para segmentación de anomalias.  

## Fini-tuning
Para entrenar a Lite-MedSAM en una sola GPU, se corre:
```python
!python /content/drive/MyDrive/liteMedSAM/train_one_gpu.py \
    -data_root /content/drive/MyDrive/liteMedSAM/data/dt_train \
    -pretrained_checkpoint /content/drive/MyDrive/liteMedSAM/work_dir/lite_medsam.pth \
    -work_dir /content/drive/MyDrive/liteMedSAM/work_dir \
    -num_workers 4 \
    -batch_size 4 \
    -num_epochs 55
```
## Validación
Para la validación de Lite-MedSAM, se corre:
```python
!python /content/drive/MyDrive/liteMedSAM/CVPR24_LiteMedSAM_inferFine.py -i /content/drive/MyDrive/liteMedSAM/data/cdd/imgs -o /content/drive/MyDrive/liteMedSAM/data/cdd/segs_breas_Fine
```

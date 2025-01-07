# Segmentación de tejidos adiposos usando Machine Learning para estudio de obesidad sarcopénica

## Objetivo General
Implementar y evaluar modelos de segmentación de tejidos adiposos del abdomen usando redes convolucionales neuronales profundas para caracterizar la distribución del tejido adiposo en imágenes de tomografía computarizada, facilitando la investigación y diagnóstico de enfermedades relacionadas.

## Arquitecturas Implementadas
Se evaluaron cinco arquitecturas diferentes:
- U-Net++
- ResNet  
- Dense U-Net
- SegNet
- Residual U-Net

## Configuración del Entrenamiento
- Learning rate inicial: 1×10^-4
- Batch size: 8
- Optimizador: Adam con clipnorm=1.0  
- Épocas máximas: 125
- Función de pérdida: Entropía cruzada categórica dispersa
- Tamaño de entrada: 512×512×1

## Resultados por Arquitectura (Coeficiente DICE)
| Arquitectura    | Fondo  | Tejido Subcutáneo | Tejido Visceral | Músculo | Promedio |
|----------------|---------|---------|---------|---------|----------|
| U-Net++        | 0.9954  | 0.9561  | 0.8716  | 0.9809  | 0.9510   |
| ResNet         | 0.9950  | 0.9439  | 0.8119  | 0.9663  | 0.9293   |
| Dense U-Net    | 0.9959  | 0.9398  | 0.8156  | 0.9597  | 0.9278   |
| SegNet         | 0.9915  | 0.9456  | 0.8322  | 0.9615  | 0.9327   |
| Residual U-Net | 0.9958  | 0.9593  | 0.8710  | 0.9799  | 0.9515   |

![image](https://github.com/user-attachments/assets/3799f09b-73c7-44b0-80d2-55f0798ed3ed)

## Principales Conclusiones
1. La Residual U-Net y U-Net++ mostraron el mejor rendimiento global con DICE promedio de 0.9515 y 0.9510 respectivamente.
2. La segmentación del tejido visceral presentó el mayor desafío para todas las arquitecturas, con puntuaciones entre 0.81 y 0.87.
3. El modelo muestra alta efectividad en la zona abdominal pero requiere adaptaciones para su uso en otras regiones corporales.
4. Los resultados confirman el potencial de estas arquitecturas para implementación en entornos clínicos donde la precisión es fundamental.

## Limitaciones
- El modelo está específicamente optimizado para la zona abdominal
- La precisión disminuye significativamente al analizar otras zonas corporales
- Requiere adaptaciones específicas para su uso en diferentes regiones anatómicas

## Trabajo Futuro
- Optimizar el rendimiento en la segmentación del tejido visceral
- Explorar la aplicabilidad en otras regiones corporales
- Realizar validaciones adicionales con expertos en salud
- Evaluar la capacidad de generalización con datasets externos

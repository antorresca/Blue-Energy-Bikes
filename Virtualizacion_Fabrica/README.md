# Módulo 6: Virtualización de Fábrica

## Modelado CAD 

Para empezar, se buscó un modelo CAD que tuviera los componentes necesarios para una adecuada simulación, para ello se empleó el modelo [Honda NSR 150SP-1997](https://grabcad.com/library/honda-nsr-150sp-1997-1) que se ve en la siguiente imagen:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Moto_CAD.png'>
</div>

**NOTA:** _El modelo original no tenia los soportes, estos fueron agregados para evitar que se cayera durante el transporte_

Dicho modelo se desglosó para las diferentes etapas de la linea de producción planteada, en la siguiente imagen se puede observar el chasis inicial, el chasis hasta la estación bateria y el chasis hasta la estación frenos y llantas:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Moto_Partes_CAD.png'>
</div>

**Nota:** _Para saber mas sobre cada estación de la linea de producción leer [Gestion de Produccion](https://github.com/antorresca/Blue-Energy-Bikes/tree/main/Gestion_Produccion)_

Teniendo el modelo de la moto, se buscaron los demás archivos CAD que se encuentran en la carpeta [ArchivosCAD](ArchivosCAD) que permitieron crear la linea de producción que se ve en al siguiente imagen, para facilidad de ubicación y entendimiento cada estación tiene su nombre a un costado.:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/ModeloCAD_Fusion.png'>
</div>

En la siguiente imagen se puede observar con mayor detalle la estación robotizada (Estación Chasis), los robots empleados se describen en el módulo [Celda Robotizada](https://github.com/antorresca/Blue-Energy-Bikes/tree/main/Celdas_Robotizada)

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/ModeloCAD_Fusion_Detalle.png'>
</div>

Cada estación de la linea de producción tiene actuadores, sensores, banda transportadora y rodillos de transporte interno, como se observa en la siguiente imagen.

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/ModeloCAD_SyA.png'>
</div>

**Nota:** _por simplicidad, los sensores para la simulación son de presencia y actuadores de tipo motor sin entrar en detalles no requeridos en esta etapa._

Por otro lado, la estación _Porta Placas_ emplea una cortadora laser:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Corte_Laser_CAD.png'>
</div>

Una vez hecho el ensamble de la linea en _Autodesk Fusion_ se exportó el archivo general en formato STEP para poderlo emplear de la manera adecuada en Siemens NX

## Siemens NX


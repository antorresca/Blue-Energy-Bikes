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

Exportado el archivo CAD en formato STEP, se procede a importar en Siemens NX dicho archivo como se muestra en la siguiente imagen:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Linea_Produccion_NX.jpg'>
</div>

Posteriormente se configuran los cuerpos rígidos y cuerpos de colisión, es decir todo lo que va a estar en contacto y queremos simular su comportamiento, además de configurar las fuentes y sumideros de productos para ver el flujo de materiales a lo largo de la línea de producción así como configurar los transformadores para poder visualizar la transformación de las motos. Dicha configuración se ve en las siguientes imágenes:


<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Cuerpos_Colision1.jpg'>
</div>
<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Cuerpos_Colision2.jpg'>
</div>

Después de esto, se configuraron las superficies de transporte, teniendo en cuenta que las bandas transportadoras van a ser la conexión entre las estaciones y los rodillos van a ser las estaciones como tal, cada banda transportadora y rodillos tienen 2 sensores de presencia, uno al inicio y otro al final para fines prácticos de lógica de programación. Como se muestra en las siguientes imágenes:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Superficies_Transporte.jpg'>
</div>
<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Sensores.jpg'>
</div>

Lo siguiente que se hizo fue definir cada una de las señales que se van a utilizar en la programación en Ladder, por lo se tiene que especificar el sensor o actuador y que señal se quiere enviar al controlador:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Adaptador_Senal1.jpg'>
</div>
<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Adaptador_Senal2.jpg'>
</div>

Después de realizar esto, se hace el paso más importante que es realizar la conexión con el servidor OPC UA, del cual se van extraer y a enviar las señales de los sensores y actuadores, teniendo en cuenta que cada señal debe tener su respectiva etiqueta en el servidor OPC UA.

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Conexion_Senal1.jpg'>
</div>
<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Conexion_Senal2.jpg'>
</div>

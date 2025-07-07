# Módulo 2: Gestión de Producción
## Descripción

## Plant Simulation
### Planta inicial
En la planta inicial (es decir, el estado actual) se tiene el siguiente layout
<div align="center">
  <img src="https://raw.githubusercontent.com/natc27/Blue-energy-landing/main/Multimedia/Simulacion_Plant.png" width="400" style="display:inline-block; margin-right: 10px;">
  <img src="https://raw.githubusercontent.com/natc27/Blue-energy-landing/main/Multimedia/Layout_Planta_Actual.png" width="400" style="display:inline-block;">
</div>
alli se tienen las siguientes estaciones:

1. **Chasis**
2. **Baterias**
3. **Motor**
4. **Llantas**
5. **Frenos**
7. **Manillar**
8. **Luces**
9. **Ensamble**
10. **Asiento**

Como se puede observar, el proceso de fabricación es lineal. Para la simulación se asignaron los siguientes valores a cada estacion:

<div align='center'>
  <table><thead><tr><th>Estacion</th><th>Tiempo de proceso</th><th>Tiempo de set-up</th><th>Falla</th><th>Distribución</th><th>Tiempo de reparación</th></tr></thead><tbody><tr><td rowspan="4">chasis</td><td rowspan="4">65:00</td><td rowspan="4">5:00</td><td>alineacion_deficiente</td><td>Negexp(1200)</td><td>10:00</td></tr><tr><td>herramienta_danada</td><td>Negexp(1500)</td><td>9:00</td></tr><tr><td>pieza_mal_colocada</td><td>Negexp(1800)</td><td>8:00</td></tr><tr><td>error_de_medicion</td><td>Negexp(2100)</td><td>10:00</td></tr><tr><td rowspan="4">baterias</td><td rowspan="4">85:00</td><td rowspan="4">4:00</td><td>fuga_electrolito</td><td>Negexp(2400)</td><td>12:00</td></tr><tr><td>error_polaridad</td><td>Negexp(3000)</td><td>10:00</td></tr><tr><td>celdas_danadas</td><td>LogNorm(1800,600)</td><td>12:00</td></tr><tr><td>conexion_deficiente</td><td>Negexp(2700)</td><td>9:00</td></tr>
<tr><td rowspan="4">motor</td><td rowspan="4">95:00</td><td rowspan="4">6:00</td><td>desalineacion_eje</td><td>Negexp(1800)</td><td>10:00</td></tr><tr><td>fallo_ensamble</td><td>LogNorm(1500,450)</td><td>9:00</td></tr><tr><td>calibracion_incorrecta</td><td>Negexp(2400)</td><td>10:00</td></tr><tr><td>daño_en_carcasa</td><td>Negexp(3000)</td><td>12:00</td></tr><tr><td rowspan="3">llantas</td><td rowspan="3">75:00</td><td rowspan="3">4:00</td><td>llanta_deformada</td><td>Negexp(1800)</td><td>10:00</td></tr><tr><td>error_balanceo</td><td>Negexp(2100)</td><td>9:00</td></tr><tr><td>fijacion_incorrecta</td><td>LogNorm(1600,400)</td><td>10:00</td></tr><tr><td rowspan="3">frenos</td><td rowspan="3">80:00</td><td rowspan="3">5:00</td><td>fuga_hidraulica</td><td>Negexp(2400)</td><td>12:00</td></tr><tr><td>error_purga</td><td>Negexp(1800)</td><td>9:00</td></tr><tr><td>sensor_frenos</td><td>LogNorm(1500,400)</td><td>10:00</td></tr>
<tr><td rowspan="3">manillar</td><td rowspan="3">78:00</td><td rowspan="3">3:00</td><td>torque_inadecuado</td><td>Negexp(1500)</td><td>8:00</td></tr><tr><td>manillar_desviado</td><td>Negexp(1800)</td><td>10:00</td></tr><tr><td>pieza_incompleta</td><td>LogNorm(1200,350)</td><td>10:00</td></tr><tr><td rowspan="3">luces</td><td rowspan="3">90:00</td><td rowspan="3">4:00</td><td>corto_luces</td><td>Negexp(2400)</td><td>12:00</td></tr><tr><td>conexion_defectuosa</td><td>Negexp(2100)</td><td>10:00</td></tr><tr><td>direccion_mal_marcada</td><td>LogNorm(1800,500)</td><td>9:00</td></tr><tr><td rowspan="3">ensamble</td><td rowspan="3">105:00</td><td rowspan="3">6:00</td><td>pieza_olvidada</td><td>Negexp(3000)</td><td>12:00</td></tr><tr><td>fallo_estructura</td><td>LogNorm(2000,600)</td><td>10:00</td></tr><tr><td>ajuste_incompleto</td><td>Negexp(2400)</td><td>9:00</td></tr>
<tr><td rowspan="3">asiento</td><td rowspan="3">60:00</td><td rowspan="3">4:00</td><td>fijacion_incompleta</td><td>Negexp(1800)</td><td>10:00</td></tr><tr><td>tapizado_defectuoso</td><td>Negexp(2100)</td><td>9:00</td></tr><tr><td>estructura_dañada</td><td>LogNorm(1600,400)</td><td>12:00</td></tr></tbody></table>
</div>

Además de esto, se consideraron 15 trabajadores con un único horario de trabajo de 7:00 a 16:00 con un descanso de 12:00 a 13:00 de lunes a viernes y descanso sabado y domingo. Al realizar l realizar la simulación con un tiempo de 1 semana (7 dias) se obtuvo la siguiente gráfica:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Grafica_plantaActual.png' width=400>
</div>

Resultados

disponibilidad (%)
73.3636246297819
rendimiento (%)
72.718253968254
calidad (%)
40
el oee es de (%)
21.3394987514405

### Planta propuesta

<div align="center">
  <img src="https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Simulacion_Plant_Propuesta.png" width="400" style="display:inline-block; margin-right: 10px;">
  <img src="https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Layout_Planta_Propuesta_1.png" width="400" style="display:inline-block;">
</div>

Las estaciones son:

1. Marcado
2. Chasis
3.  Bateria
4.  Manillar y llantas
5.  Motor
6.  Frenos y suspension
7.  Luces y cableado
8.  Porta_placa
9.  Asiento y detalles
10.  Inspeccion

Se usaron los siguientes datos para cada una de las estaciones

<div align='center'>
<table><thead><tr><th>Estación</th><th>Tiempo de proceso</th><th>Tiempo de set-up</th><th>Falla</th><th>Distribución</th><th>Tiempo de reparación</th></tr></thead><tbody><tr><td rowspan="5">Marcado</td><td rowspan="5">8:00</td><td rowspan="5">3:00</td><td>desalineacion_marcado</td><td>Negexp(0.0926)</td><td>3:00</td></tr><tr><td>error_marcado</td><td>Negexp(0.0694)</td><td>4:00</td></tr><tr><td>fallo_lectura</td><td>Negexp(0.0463)</td><td>8:00</td></tr><tr><td>contaminacion_chasis</td><td>Negexp(0.0463)</td><td>6:00</td></tr><tr><td>error_datos</td><td>Negexp(0.0278)</td><td>10:00</td></tr><tr><td rowspan="5">chasis</td><td rowspan="5">20:00</td><td rowspan="5">6:00</td><td>desalineacion_estacion</td><td>Negexp(0.0833)</td><td>3:00</td></tr><tr><td>fallo_sujecion</td><td>Negexp(0.0667)</td><td>4:00</td></tr><tr><td>error_robot</td><td>Negexp(0.0556)</td><td>5:00</td></tr><tr><td>defecto_soldadura</td><td>Negexp(0.0417)</td><td>7:00</td></tr>
<tr><td>fallo_vision</td><td>Negexp(0.0278)</td><td>10:00</td></tr><tr><td rowspan="5">bateria</td><td rowspan="5">35:00</td><td rowspan="5">4:00</td><td>desalineacion_caja</td><td>Negexp(0.0056)</td><td>9:00</td></tr><tr><td>tornillos_sueltos</td><td>Negexp(0.0042)</td><td>12:00</td></tr><tr><td>conexion_bateria</td><td>Negexp(0.0028)</td><td>10:00</td></tr><tr><td>polaridad_invertida</td><td>Negexp(0.0019)</td><td>15:00</td></tr><tr><td>fijacion_cableado</td><td>Negexp(0.0048)</td><td>12:00</td></tr><tr><td rowspan="5">manillar_llantas</td><td rowspan="5">45:00</td><td rowspan="5">5:00</td><td>desalineacion_manillar</td><td>Negexp(0.0926)</td><td>3:00</td></tr><tr><td>torque_incorrecto</td><td>Negexp(0.0694)</td><td>5:00</td></tr><tr><td>fallo_conexion</td><td>Negexp(0.0556)</td><td>7:00</td></tr><tr><td>defecto_llantas</td><td>Negexp(0.0463)</td><td>6:00</td></tr><tr><td>error_documentacion</td><td>Negexp(0.0278)</td><td>10:00</td></tr>
<tr><td rowspan="3">motor</td><td rowspan="3">40:00</td><td rowspan="3">4:00</td><td>fallo_herramienta</td><td>LogNorm(12)</td><td>12:00</td></tr><tr><td>fallo_electrico</td><td>LogNorm(25)</td><td>25:00</td></tr><tr><td>fallo_alineacion</td><td>LogNorm(15)</td><td>15:00</td></tr><tr><td rowspan="5">frenos_suspension</td><td rowspan="5">35:00</td><td rowspan="5">5:00</td><td>colocacion_mordazas</td><td>Negexp(0.0833)</td><td>5:00</td></tr><tr><td>cableado_defectuoso</td><td>Negexp(0.0667)</td><td>4:00</td></tr><tr><td>fuga_hidraulica</td><td>Negexp(0.0417)</td><td>8:00</td></tr><tr><td>alineacion_suspension</td><td>Negexp(0.0556)</td><td>6:00</td></tr><tr><td>daño_estructural</td><td>Negexp(0.0139)</td><td>15:00</td></tr><tr><td rowspan="3">luces_cableado</td><td rowspan="3">40:00</td><td rowspan="3">4:00</td><td>corto_sistema</td><td>Negexp(0.0017)</td><td>10:00</td></tr><tr><td>mal_enrutamiento</td><td>Negexp(0.0050)</td><td>10:00</td></tr>
<tr><td>fallo_verificacion</td><td>Negexp(0.0019)</td><td>15:00</td></tr><tr><td rowspan="5">porta_placa</td><td rowspan="5">5:00</td><td rowspan="5">2:00</td><td>fijacion_lamina</td><td>Negexp(0.0694)</td><td>4:00</td></tr><tr><td>configuracion_motor</td><td>Negexp(0.0556)</td><td>5:00</td></tr><tr><td>lente_sucia</td><td>Negexp(0.0333)</td><td>10:00</td></tr><tr><td>material_defectuoso</td><td>Negexp(0.0417)</td><td>4:00</td></tr><tr><td>error_cad</td><td>Negexp(0.0208)</td><td>15:00</td></tr><tr><td rowspan="4">asiento_detalles</td><td rowspan="4">60:00</td><td rowspan="4">6:00</td><td>adhesivo_mal</td><td>LogNorm(4)</td><td>4:00</td></tr><tr><td>carcasa_mal</td><td>LogNorm(10)</td><td>10:00</td></tr><tr><td>pieza_defectuosa</td><td>LogNorm(8)</td><td>8:00</td></tr><tr><td>daño_superficial</td><td>LogNorm(15)</td><td>15:00</td></tr><tr><td rowspan="5">inspeccion</td><td rowspan="5">20:00</td><td rowspan="5">3:00</td><td>fallo_mecanico</td><td>Negexp(0.0926)</td><td>5:00</td></tr>
<tr><td>fallo_electrico_basico</td><td>Negexp(0.0694)</td><td>4:00</td></tr><tr><td>bateria_suelta</td><td>Negexp(0.0463)</td><td>6:00</td></tr><tr><td>daño_cosmetico</td><td>Negexp(0.0347)</td><td>10:00</td></tr><tr><td>problema_grave</td><td>Negexp(0.0139)</td><td>20:00</td></tr></tbody></table>
</div>

Por otro lado se tuvo como horario de trabajo de lunes a viernes, con descanso sábado y domingo:

<div align='center'>
  <table><thead><tr><th>Turno</th><th>Entrada</th><th>Salida</th><th>Descanso</th></tr></thead><tbody><tr><td>Diurno</td><td>6:00 pm</td><td>5:00 pm</td><td>9:00 am - 10:00 am<br>12:00 pm - 1:00 pm</td></tr><tr><td>Nocturno</td><td>6:00 pm</td><td>5:00 am</td><td>9:00 pm - 10:00 pm<br>00:00 am - 1:00 am</td></tr></tbody></table>
</div>

Con ello se obtuvo los siguientes datos

<div align='center'>
<table><thead><tr><th>Tiempo simulado</th><th>7 dias</th></tr></thead><tbody><tr><td>Unidades ideales</td><td>38</td></tr><tr><td>Piezas Hechas</td><td>34</td></tr><tr><td>Fallas</td><td>4</td></tr><tr><td>Disponibilidad</td><td>84.567%</td></tr><tr><td>Rendimiento</td><td>88.71%</td></tr><tr><td>Calidad</td><td>88.235%</td></tr><tr><td>OEE</td><td>66.194%</td></tr></tbody></table>
</div>

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Grafica_plantapropuesta.png' width=400>
</div>


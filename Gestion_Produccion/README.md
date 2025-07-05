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

<div class="card" align='center'>
<table><thead><tr><th>Estación</th><th>Tiempo de Proceso (MM:SS)</th><th>Falla (Duración,Disponibilidad)</th><th>Set-Up</th><th>Recovery Time</th></tr></thead><tbody><tr><td>Chasis</td><td>30:00</td><td>2:00, 88%</td><td>2:00</td><td>Lognorm(1:40,0:10)</td></tr><tr><td>Baterías</td><td>30:00</td><td>Uniform(2:00,3:00), 98.324%</td><td>1:00</td><td>5:00</td></tr><tr><td>Motor</td><td>30:00</td><td>2:00,98.654%</td><td>Lognorm(2:00,0:10)</td><td>5:00</td></tr><tr><td>Llantas</td><td>25:00</td><td>2:00, 98.654%</td><td>2:00</td><td>5:00</td></tr><tr><td>Frenos</td><td>30:00</td><td>2:00, 98.654%</td><td>2:00</td><td>Uniform(0:01,5:01)</td></tr><tr><td>Manillar</td><td>30:00</td><td>Uniform(2:00,10:00), 96.069%</td><td>2:00</td><td>5:00</td></tr><tr><td>Luces y cableado</td><td>30:00</td><td>2:00, 98.654%</td><td>2:00</td><td>Uniform(10:00,10:00)</td></tr><tr><td>Ensamble eléctrico</td><td>30:00</td><td>Normal(20:00,0:01), 88%</td><td>2:00</td><td>Erlang(1:00,20:00)</td></tr>
<tr><td>Asiento y detalles</td><td>30:00</td><td>30:00,83.018%</td><td>2:00</td><td>5:00</td></tr></tbody></table>
</div>

Además de esto, se consideraron 15 trabajadores con un único horario de trabajo de 7:00 a 16:00 con un descanso de 12:00 a 13:00 de lunes a viernes y descanso sabado y domingo. Al realizar l realizar la simulación con un tiempo de 1 semana (7 dias) se obtuvo la siguiente gráfica:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Grafica_plantaActual.png' width=400>
</div>

### Planta propuesta

<div align="center">
  <img src="https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Simulacion_Plant_Propuesta.png" width="400" style="display:inline-block; margin-right: 10px;">
  <img src="https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Layout_Planta_Propuesta_1.png" width="400" style="display:inline-block;">
</div>

<div align='center'>
  <img src='https://github.com/user-attachments/assets/25b06e82-713f-4d63-87f9-bd27cac82104' width=400>
</div>

<div align='center'>
  <table><thead><tr><th>Estación</th><th>Tiempo de&nbsp;&nbsp;&nbsp;proceso</th><th>Tiempo de set-up</th><th>Falla</th><th>Probabilidad</th><th>Tiempo de&nbsp;&nbsp;&nbsp;repación</th></tr></thead><tbody><tr><td rowspan="5">marcado</td><td rowspan="5">8:00</td><td rowspan="5">3:00</td><td>desalineacion_marcado</td><td>0.09%</td><td>3:00</td></tr><tr><td>error_marcado</td><td>0.07%</td><td>4:00</td></tr><tr><td>fallo_lectura</td><td>0.05%</td><td>8:00</td></tr><tr><td>contaminacion_chasis</td><td>0.05%</td><td>6:00</td></tr><tr><td>error_datos</td><td>0.03%</td><td>10:00</td></tr><tr><td rowspan="5">chasis</td><td rowspan="5">20:00</td><td rowspan="5">6:00</td><td>desalineacion_estacion</td><td>0.08%</td><td>3:00</td></tr><tr><td>fallo_sujecion</td><td>0.07%</td><td>4:00</td></tr><tr><td>error_robot</td><td>0.06%</td><td>5:00</td></tr><tr><td>defecto_soldadura</td><td>0.04%</td><td>7:00</td></tr><tr><td>fallo_vision</td><td>0.03%</td><td>10:00</td></tr>
<tr><td rowspan="5">bateria</td><td rowspan="5">35:00</td><td rowspan="5">4:00</td><td>desalineacion_caja</td><td>0.01%</td><td>9:00</td></tr><tr><td>tornillos_sueltos</td><td>0.004%</td><td>12:00</td></tr><tr><td>conexion_bateria</td><td>0.003%</td><td>10:00</td></tr><tr><td>polaridad_invertida</td><td>0.002%</td><td>15:00</td></tr><tr><td>fijacion_cableado</td><td>~0.003%</td><td>12:00</td></tr><tr><td rowspan="5">manillar_llantas</td><td rowspan="5">45:00</td><td rowspan="5">5:00</td><td>desalineacion_manillar</td><td>0.09%</td><td>3:00</td></tr><tr><td>torque_incorrecto</td><td>0.07%</td><td>5:00</td></tr><tr><td>fallo_conexion</td><td>0.06%</td><td>7:00</td></tr><tr><td>defecto_llantas</td><td>0.05%</td><td>6:00</td></tr><tr><td>error_documentacion</td><td>0.03%</td><td>10:00</td></tr><tr><td rowspan="3">motor</td><td rowspan="3">40:00</td><td rowspan="3">4:00</td><td>fallo_herramienta</td><td>~0.09%</td><td>12:00</td></tr>
<tr><td>fallo_electrico</td><td>0.002%</td><td>20:00</td></tr><tr><td>fallo_alineacion</td><td>0.003%</td><td>15:00</td></tr><tr><td rowspan="5">frenos_suspension</td><td rowspan="5">35:00</td><td rowspan="5">5:00</td><td>colocacion_mordazas</td><td>0.08%</td><td>5:00</td></tr><tr><td>cableado_defectuoso</td><td>0.07%</td><td>4:00</td></tr><tr><td>fuga_hidraulica</td><td>0.04%</td><td>8:00</td></tr><tr><td>alineacion_suspension</td><td>0.06%</td><td>6:00</td></tr><tr><td>daño_estructural</td><td>0.01%</td><td>15:00</td></tr><tr><td rowspan="3">luces_cableado</td><td rowspan="3">40:00</td><td rowspan="3">4:00</td><td>corto_sistema</td><td>0.003%</td><td>10:00</td></tr><tr><td>mal_enrutamiento</td><td>~0.1%</td><td>10:00</td></tr><tr><td>fallo_verificacion</td><td>0.002%</td><td>15:00</td></tr><tr><td rowspan="5">porta_placa</td><td rowspan="5">5:00</td><td rowspan="5">2:00</td><td>fijacion_lamina</td><td>0.07%</td><td>4:00</td></tr>
<tr><td>configuracion_motor</td><td>0.06%</td><td>5:00</td></tr><tr><td>lente_sucia</td><td>0.03%</td><td>10:00</td></tr><tr><td>material_defectuoso</td><td>0.04%</td><td>4:00</td></tr><tr><td>error_cad</td><td>0.02%</td><td>15:00</td></tr><tr><td rowspan="4">asiento_detalles</td><td rowspan="4">20:00</td><td rowspan="4">6:00</td><td>adhesivo_mal</td><td>0.003%</td><td>4:00</td></tr><tr><td>carcasa_mal</td><td>0.003%</td><td>10:00</td></tr><tr><td>pieza_defectuosa</td><td>0.001%</td><td>8:00</td></tr><tr><td>daño_superficial</td><td>~0.1%</td><td>15:00</td></tr><tr><td rowspan="5">inspeccion</td><td rowspan="5">20:00</td><td rowspan="5">3:00</td><td>fallo_mecanico</td><td>0.09%</td><td>5:00</td></tr><tr><td>fallo_electrico_basico</td><td>0.07%</td><td>4:00</td></tr><tr><td>bateria_suelta</td><td>0.05%</td><td>6:00</td></tr><tr><td>daño_cosmetico</td><td>0.03%</td><td>10:00</td></tr><tr><td>problema_grave</td><td>0.01%</td><td>20:00</td></tr></tbody></table>
</div>

<div align='center'>
  <table><thead><tr><th>Tiempo simulado</th><th>7 dias</th></tr></thead><tbody><tr><td>Unidades ideales</td><td>38</td></tr><tr><td>Piezas Hechas</td><td>33</td></tr><tr><td>Fallas</td><td>4</td></tr><tr><td>Disponibilidad</td><td>84.259%</td></tr><tr><td>Rendimiento</td><td>86.101%</td></tr><tr><td>Calidad</td><td>87.879%</td></tr><tr><td>OEE</td><td>63.754%</td></tr></tbody></table>
</div>


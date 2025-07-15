# Módulo 2: Gestión de Producción
## Descripción

## Plant Simulation

Para revisar cuestiones de mejora en la linea de producción, se realizó la simulacion de la planta inicial y de la planta propuesta en el programa _Plant Simulation_ para facilitar las variaciones que se quieran realizar y realizar el proceso de iteraciones.

### Planta inicial
En la planta inicial (es decir, el estado actual) se tiene el siguiente modelo CAD de simulación y el layout correspondiente:

<div align="center">
  <img src="https://raw.githubusercontent.com/natc27/Blue-energy-landing/main/Multimedia/Simulacion_Plant.png" width="400" style="display:inline-block; margin-right: 10px;">
  <img src="https://raw.githubusercontent.com/natc27/Blue-energy-landing/main/Multimedia/Layout_Planta_Actual.png" width="400" style="display:inline-block;">
</div>

En esta simulacion inicail se tienen las siguientes estaciones:

<div align='center'>
  <table border="1">
  <tr><th>Estación</th><th>Función</th></tr>
  <tr><td>Chasis</td><td>Base estructural de la moto.</td></tr>
  <tr><td>Motor</td><td>Instala el sistema de propulsión.</td></tr>
  <tr><td>Baterías</td><td>Coloca el sistema de energía.</td></tr>
  <tr><td>Frenos</td><td>Ensamble del sistema de frenado.</td></tr>
  <tr><td>Llantas</td><td>Montaje de ruedas al chasis.</td></tr>
  <tr><td>Manillar</td><td>Instala dirección y controles.</td></tr>
  <tr><td>Luces</td><td>Fija luces delanteras y traseras.</td></tr>
  <tr><td>Asiento</td><td>Coloca el asiento al chasis.</td></tr>
  <tr><td>Ensamble</td><td>Integración y revisión final.</td></tr>
</table>
</div>

Una vez definidas las estaciones se realizaron las configuraciones necesarias como el tiempo de preparación, el tiempo de proceso, las fallas (probabilidad de ocurrencia y duración) entre otras; los datos asignados a cada estación se pueden ver en la siguiente tabla:

<div align='center'>
  <table><thead><tr><th>Estacion</th><th>Tiempo de proceso</th><th>Tiempo de set-up</th><th>Falla</th><th>Distribución</th><th>Tiempo de reparación</th></tr></thead><tbody><tr><td rowspan="4">chasis</td><td rowspan="4">65:00</td><td rowspan="4">5:00</td><td>alineacion_deficiente</td><td>Negexp(1200)</td><td>10:00</td></tr><tr><td>herramienta_danada</td><td>Negexp(1500)</td><td>9:00</td></tr><tr><td>pieza_mal_colocada</td><td>Negexp(1800)</td><td>8:00</td></tr><tr><td>error_de_medicion</td><td>Negexp(2100)</td><td>10:00</td></tr><tr><td rowspan="4">baterias</td><td rowspan="4">85:00</td><td rowspan="4">4:00</td><td>fuga_electrolito</td><td>Negexp(2400)</td><td>12:00</td></tr><tr><td>error_polaridad</td><td>Negexp(3000)</td><td>10:00</td></tr><tr><td>celdas_danadas</td><td>LogNorm(1800,600)</td><td>12:00</td></tr><tr><td>conexion_deficiente</td><td>Negexp(2700)</td><td>9:00</td></tr>
<tr><td rowspan="4">motor</td><td rowspan="4">95:00</td><td rowspan="4">6:00</td><td>desalineacion_eje</td><td>Negexp(1800)</td><td>10:00</td></tr><tr><td>fallo_ensamble</td><td>LogNorm(1500,450)</td><td>9:00</td></tr><tr><td>calibracion_incorrecta</td><td>Negexp(2400)</td><td>10:00</td></tr><tr><td>daño_en_carcasa</td><td>Negexp(3000)</td><td>12:00</td></tr><tr><td rowspan="3">llantas</td><td rowspan="3">75:00</td><td rowspan="3">4:00</td><td>llanta_deformada</td><td>Negexp(1800)</td><td>10:00</td></tr><tr><td>error_balanceo</td><td>Negexp(2100)</td><td>9:00</td></tr><tr><td>fijacion_incorrecta</td><td>LogNorm(1600,400)</td><td>10:00</td></tr><tr><td rowspan="3">frenos</td><td rowspan="3">80:00</td><td rowspan="3">5:00</td><td>fuga_hidraulica</td><td>Negexp(2400)</td><td>12:00</td></tr><tr><td>error_purga</td><td>Negexp(1800)</td><td>9:00</td></tr><tr><td>sensor_frenos</td><td>LogNorm(1500,400)</td><td>10:00</td></tr>
<tr><td rowspan="3">manillar</td><td rowspan="3">78:00</td><td rowspan="3">3:00</td><td>torque_inadecuado</td><td>Negexp(1500)</td><td>8:00</td></tr><tr><td>manillar_desviado</td><td>Negexp(1800)</td><td>10:00</td></tr><tr><td>pieza_incompleta</td><td>LogNorm(1200,350)</td><td>10:00</td></tr><tr><td rowspan="3">luces</td><td rowspan="3">90:00</td><td rowspan="3">4:00</td><td>corto_luces</td><td>Negexp(2400)</td><td>12:00</td></tr><tr><td>conexion_defectuosa</td><td>Negexp(2100)</td><td>10:00</td></tr><tr><td>direccion_mal_marcada</td><td>LogNorm(1800,500)</td><td>9:00</td></tr><tr><td rowspan="3">ensamble</td><td rowspan="3">105:00</td><td rowspan="3">6:00</td><td>pieza_olvidada</td><td>Negexp(3000)</td><td>12:00</td></tr><tr><td>fallo_estructura</td><td>LogNorm(2000,600)</td><td>10:00</td></tr><tr><td>ajuste_incompleto</td><td>Negexp(2400)</td><td>9:00</td></tr>
<tr><td rowspan="3">asiento</td><td rowspan="3">60:00</td><td rowspan="3">4:00</td><td>fijacion_incompleta</td><td>Negexp(1800)</td><td>10:00</td></tr><tr><td>tapizado_defectuoso</td><td>Negexp(2100)</td><td>9:00</td></tr><tr><td>estructura_dañada</td><td>LogNorm(1600,400)</td><td>12:00</td></tr></tbody></table>
</div>

Por otro lado, se consideró la siguiente informacion sobre los trabajadores

* Número de trabajadores: 15.
* Horario de trabajo: de 7:00am a 4:00pm con un descanso de 12:00pm a 1:00pm.
* Dias laborales: lunes a viernes y descanso sabado y domingo.

Al realizar la simulación con un tiempo de 1 semana (7 dias=604800segundos) se obtuvo la siguiente gráfica:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Grafica_plantaActual.png' width=400>
</div>

Una vez realizada la simulación, se calculó el OEE con un código de _simTalk_ ([OEE_Inicial.txt](Archivos/OEE_Inicial.txt)). Un fragmento se puede observar

```simtalk
var tiempo = eventController.end

var total_time = chasis.statWorkingTime+baterias.statWorkingTime+motor.statWorkingTime+llantas.statWorkingTime+frenos.statWorkingTime+manillar.statWorkingTime+luces.statWorkingTime+ensamble.statWorkingTime+asiento.statWorkingTime
var proc_time =  chasis.procTime+baterias.procTime+motor.procTime+llantas.procTime+frenos.procTime+manillar.procTime+luces.procTime+ensamble.procTime+asiento.procTime

var unidades_ideal = tiempo/proc_time

var dispo := total_time / tiempo
var rend := total / unidades_ideal
var cal := (total-fallas) / total

var oee := dispo*rend*cal*100
```

Dando 

<div align='center'>
<table><thead><tr><th>Tiempo simulado</th><th>7 dias</th></tr></thead><tbody><tr><td>Unidades ideales</td><td>14</td></tr><tr><td>Piezas Hechas</td><td>10</td></tr><tr><td>Fallas</td><td>6</td></tr><tr><td>Disponibilidad</td><td>73.363%</td></tr><tr><td>Rendimiento</td><td>72.71%</td></tr><tr><td>Calidad</td><td>40%</td></tr><tr><td>OEE</td><td>21.339%</td></tr></tbody></table>
</div>


### Planta propuesta

Para la planta propuesta, se creó el siguiente modelo CAD de simulación con su correspondiente Layout

<div align="center">
  <img src="https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Simulacion_Plant_Propuesta.png" width="500" style="display:inline-block; margin-right: 10px;">
  <img src="https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Layout_Planta_Propuesta_1.png" width="500" style="display:inline-block;">
</div>

Las estaciones son:

<div align='center'>
  <table border="1">
  <tr><th>Estación</th><th>Función</th></tr>
  <tr><td>Marcado</td><td>Identificación y registro del chasis.</td></tr>
  <tr><td>Chasis</td><td>Base estructural para ensamblaje.</td></tr>
  <tr><td>Batería</td><td>Instalación del sistema de energía.</td></tr>
  <tr><td>Manillar y llantas</td><td>Montaje de dirección y ruedas.</td></tr>
  <tr><td>Motor</td><td>Colocación del sistema de propulsión.</td></tr>
  <tr><td>Frenos y suspensión</td><td>Instala frenos y sistema de soporte.</td></tr>
  <tr><td>Luces y cableado</td><td>Ensamble de iluminación y conexiones.</td></tr>
  <tr><td>Porta_placa</td><td>Fijación del soporte de matrícula.</td></tr>
  <tr><td>Asiento y detalles</td><td>Colocación del asiento y acabados.</td></tr>
  <tr><td>Inspección</td><td>Revisión final y control de calidad.</td></tr>
</table>
</div>

Se usaron los siguientes datos para cada una de las estaciones

<div align='center'>
<table><thead><tr><th>Estación</th><th>Tiempo de proceso</th><th>Tiempo de set-up</th><th>Falla</th><th>Distribución</th><th>Tiempo de reparación</th></tr></thead><tbody><tr><td rowspan="5">Marcado</td><td rowspan="5">8:00</td><td rowspan="5">3:00</td><td>desalineacion_marcado</td><td>Negexp(720)</td><td>3:00</td></tr><tr><td>error_marcado</td><td>Negexp(1080)</td><td>4:00</td></tr><tr><td>fallo_lectura</td><td>Negexp(2160)</td><td>8:00</td></tr><tr><td>contaminacion_chasis</td><td>Negexp(1440)</td><td>6:00</td></tr><tr><td>error_datos</td><td>Negexp(2880)</td><td>10:00</td></tr><tr><td rowspan="5">chasis</td><td rowspan="5">20:00</td><td rowspan="5">6:00</td><td>desalineacion_estacion</td><td>Negexp(600)</td><td>3:00</td></tr><tr><td>fallo_sujecion</td><td>Negexp(960)</td><td>4:00</td></tr><tr><td>error_robot</td><td>Negexp(1200)</td><td>5:00</td></tr><tr><td>defecto_soldadura</td><td>Negexp(1500)</td><td>7:00</td></tr><tr><td>fallo_vision</td><td>Negexp(2400)</td><td>10:00</td></tr>
<tr><td rowspan="5">bateria</td><td rowspan="5">35:00</td><td rowspan="5">4:00</td><td>desalineacion_caja</td><td>Negexp(18000)</td><td>9:00</td></tr><tr><td>tornillos_sueltos</td><td>Negexp(24000)</td><td>12:00</td></tr><tr><td>conexion_bateria</td><td>Negexp(36000)</td><td>10:00</td></tr><tr><td>polaridad_invertida</td><td>Negexp(54000)</td><td>15:00</td></tr><tr><td>fijacion_cableado</td><td>LogNorm(480,180)</td><td>12:00</td></tr><tr><td rowspan="5">manillar_llantas</td><td rowspan="5">45:00</td><td rowspan="5">5:00</td><td>desalineacion_manillar</td><td>Negexp(900)</td><td>3:00</td></tr><tr><td>torque_incorrecto</td><td>Negexp(1200)</td><td>5:00</td></tr><tr><td>fallo_conexion</td><td>Negexp(1800)</td><td>7:00</td></tr><tr><td>defecto_llantas</td><td>Negexp(1500)</td><td>6:00</td></tr><tr><td>error_documentacion</td><td>Negexp(3000)</td><td>10:00</td></tr>
<tr><td rowspan="3">motor</td><td rowspan="3">40:00</td><td rowspan="3">4:00</td><td>fallo_herramienta</td><td>LogNorm(900,300)</td><td>12:00</td></tr><tr><td>fallo_electrico</td><td>Negexp(43200)</td><td>25:00</td></tr><tr><td>fallo_alineacion</td><td>Negexp(28800)</td><td>15:00</td></tr><tr><td rowspan="5">frenos_suspension</td><td rowspan="5">35:00</td><td rowspan="5">5:00</td><td>colocacion_mordazas</td><td>Negexp(900)</td><td>5:00</td></tr><tr><td>cableado_defectuoso</td><td>Negexp(1200)</td><td>4:00</td></tr><tr><td>fuga_hidraulica</td><td>Negexp(2100)</td><td>8:00</td></tr><tr><td>alineacion_suspension</td><td>Negexp(1500)</td><td>6:00</td></tr><tr><td>daño_estructural</td><td>Negexp(6000)</td><td>15:00</td></tr><tr><td rowspan="3">luces_cableado</td><td rowspan="3">40:00</td><td rowspan="3">4:00</td><td>corto_sistema</td><td>Negexp(36000)</td><td>10:00</td></tr><tr><td>mal_enrutamiento</td><td>LogNorm(720,240)</td><td>10:00</td></tr>
<tr><td>fallo_verificacion</td><td>Negexp(54000)</td><td>15:00</td></tr><tr><td rowspan="5">porta_placa</td><td rowspan="5">5:00</td><td rowspan="5">2:00</td><td>fijacion_lamina</td><td>Negexp(1080)</td><td>4:00</td></tr><tr><td>configuracion_motor</td><td>Negexp(1500)</td><td>5:00</td></tr><tr><td>lente_sucia</td><td>Negexp(2400)</td><td>10:00</td></tr><tr><td>material_defectuoso</td><td>Negexp(1800)</td><td>4:00</td></tr><tr><td>error_cad</td><td>Negexp(3600)</td><td>15:00</td></tr><tr><td rowspan="4">asiento_detalles</td><td rowspan="4">60:00</td><td rowspan="4">6:00</td><td>adhesivo_mal</td><td>Negexp(27000)</td><td>4:00</td></tr><tr><td>carcasa_mal</td><td>Negexp(36000)</td><td>10:00</td></tr><tr><td>pieza_defectuosa</td><td>Negexp(72000)</td><td>8:00</td></tr><tr><td>daño_superficial</td><td>LogNorm(480,160)</td><td>15:00</td></tr><tr><td rowspan="5">inspeccion</td><td rowspan="5">20:00</td><td rowspan="5">3:00</td><td>fallo_mecanico</td><td>Negexp(720)</td><td>5:00</td></tr>
<tr><td>fallo_electrico_basico</td><td>Negexp(900)</td><td>4:00</td></tr><tr><td>bateria_suelta</td><td>Negexp(1200)</td><td>6:00</td></tr><tr><td>daño_cosmetico</td><td>Negexp(1500)</td><td>10:00</td></tr><tr><td>problema_grave</td><td>Negexp(4800)</td><td>20:00</td></tr></tbody></table>
</div>

Para facilitar los cambios se diseñó un código de _SimTalk_ el cual permite cambiar los tiempos de cada estación y crear las diferentes fallas. Un fragmento del código es:

```simtalk
marcado.procTime.setTypeAndAttr("Const","8:00") //Tiempo de proceso
marcado.setupTime.setTypeAndAttr("Const","3:00") //Tiempo de preparacion
marcado.setupAfterNumParts := 2 //Frecuencia de preparacion
marcado.ShiftCalendarObject := ShiftCalendar //Horarios utiles de la estacion

//Fallas
marcado.Failures.createFailure("desalineacion_marcado","Negexp,1080","Const,180")
marcado.Failures.createFailure("error_marcado","Negexp,1440","Const,240")
marcado.Failures.createFailure("fallo_lectura","Negexp,2160","Const,480")
marcado.Failures.createFailure("contaminacion_chasis","Negexp,2160","Const,360")
marcado.Failures.createFailure("error_datos","Negexp,3600","Const,600")
```
**Nota:** El código está en [Codigo_Estaciones.txt](Archivos/Codigo_Estaciones.txt) (Este código debe ser colocado en un objeto tipo 'metodo' en Plant Simulation para su funcionamiento)

Ya con las estaciones definidas se determinó el horario de trabajo de lunes a viernes, con descanso sábado y domingo:

<div align='center'>
  <table><thead><tr><th>Turno</th><th>Entrada</th><th>Salida</th><th>Descanso</th></tr></thead><tbody><tr><td>Diurno</td><td>6:00 pm</td><td>5:00 pm</td><td>9:00 am - 10:00 am<br>12:00 pm - 1:00 pm</td></tr><tr><td>Nocturno</td><td>6:00 pm</td><td>5:00 am</td><td>9:00 pm - 10:00 pm<br>00:00 am - 1:00 am</td></tr></tbody></table>
</div>

De la misma forma se creó un código de _SimTalk_ para facilitar el proceso de iteracion

```simtalk
var rt: table                               
WorkerPool.getWorkersToCreateTable(rt) 
rt [2,1]:= 15 //Cantidad de trabajadores

WorkerPool.setWorkersToCreateTable(rt)

var t:table := ShiftCalendar.ShiftPlan
t["From", 1] := 6:00:00 //Hora de entrada turno 1
t["To", 1] := 17:00:00 //Hora de salida turno 1
t["Pauses", 1] := "9:00-10:00 12:00-13:00" //Descanso turno 1
t["From", 2] := 18:00:00 //Hora de entrada turno 2
t["To", 2] := 5:00:00 //Hora de salida turno 2
t["Pauses", 2] := "21:00-22:00 00:00-01:00" //Descanso turno 2

ShiftCalendar.ShiftPlan := t
```

Con estas configuraciones, se realizó la simulación con un tiempo de 1 semana (7 dias=604800segundos) se obtuvo la siguiente gráfica:

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/Grafica_plantapropuesta.png' width=400>
</div>

Al emplear el codigo de SimTalk descrito en la sección [Planta Inicial](#planta-inicial) (([OEE_Propuesta.txt](Archivos/OEE_Propuesta.txt)) se obtuvieron los siguientes datos

<div align='center'>
<table><thead><tr><th>Tiempo simulado</th><th>7 dias</th></tr></thead><tbody><tr><td>Unidades ideales</td><td>38</td></tr><tr><td>Piezas Hechas</td><td>34</td></tr><tr><td>Fallas</td><td>4</td></tr><tr><td>Disponibilidad</td><td>84.567%</td></tr><tr><td>Rendimiento</td><td>88.71%</td></tr><tr><td>Calidad</td><td>88.235%</td></tr><tr><td>OEE</td><td>66.194%</td></tr></tbody></table>
</div>



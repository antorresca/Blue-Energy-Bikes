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

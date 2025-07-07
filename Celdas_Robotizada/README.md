# Módulo 5: Celdas de Manufactura Robotizadas
## Descripción
## Celda robotizada
### Selección de Estación

**Estación a Robotizar:** Chasis

**Entrada:** Chasis pintado sin soportes.

**Salida:** Chasis limpio y listo para ensamblaje.

Su función principal es preparar el esqueleto estructural de la moto, sobre el cual se montarán los demás componentes.

**Actividades de la estación:**
- Recepción del chasis prefabricado o soldado.
- Limpieza del chasis (por aire comprimido o cepillo rotativo).
- Inserción de tuercas remachables o pernos de fijación.
- Liberación del chasis a la siguiente estación.


### Descripción de la celda robotizada

La celda se centrará en el alistamiento de soportes adicionales adheridos al chasis de la motocicleta. Esta actividad se desglosa en los siguientes ítems:

- **Estado de entrada del producto:**  
  Se recibe el chasis previamente desempacado del proveedor, con suciedad acumulada, pintado del color requerido para la motocicleta y sin soportes adicionales para cableado, piezas, etc.

- **Estado de salida del producto:**  
  Se entrega a la siguiente estación un chasis limpio, con la capa de pintura sin daños y con los soportes adicionales requeridos para el cableado, piezas, etc., como tuercas remachables y pernos de fijación.

- ***Takt Time:***  
  Dado que se trata de motos de alta potencia, se puede esperar un *Takt Time* de aproximadamente **4.8 minutos** o **288 segundos**, considerando una jornada laboral de 8 horas/día y una producción de 100 unidades/día. Esto teniendo en cuenta el cuidado requerido con el producto.

- **Throughput Time:**  
  Buscando reducir este tiempo para evitar cuellos de botella y agilizar la producción, se tiene como objetivo un *Throughput Time* de **5 minutos** o **300 segundos**, tratando de igualar el *Takt Time*. Este tiempo se compone de:

  - **Tiempo de espera antes de entrar a la celda:** 1 minuto o 60 segundos.  
  - **Tiempo total del proceso:** 3 minutos o 180 segundos.  
  - **Tiempo de transporte entre estaciones:** 1 minuto o 60 segundos.


### Elementos

<div align='center'>
  <table border="1">
  <thead>
    <tr>
      <th>Categoría</th>
      <th>Elementos</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Máquinas de proceso</td>
      <td>
        <ul>
          <li>Estación de limpieza por aire o cepillo rotativo</li>
          <li>Máquina de inserción de tuercas remachables o pernos</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Manipuladores</td>
      <td>
        <ul>
          <li>Brazo articulado o grúa pórtico para recepción y liberación del chasis</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Séptimos ejes</td>
      <td>
        <ul>
          <li>Mesa deslizante para mover el chasis dentro de la celda</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Elementos de transporte</td>
      <td>
        <ul>
          <li>Banda transportadora o carro autónomo (AGV) para entrada y salida del chasis</li>
          <li>Pallets de sujeción para estabilizar el chasis durante el proceso</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Otros</td>
      <td>
        <ul>
          <li>Panel HMI para supervisión del operador</li>
          <li>Sensores de presencia para detectar posición del chasis</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

</div>

### Elementos de seguridad
<div align='center'>
  <table><thead><tr><th>Elemento</th><th>Necesidad</th></tr></thead><tbody><tr><td>Mallas metálicas con puertas con enclavamiento.</td><td>Delimitar el área de trabajo y evitar el acceso no autorizado.</td></tr><tr><td>Cerraduras electromecánicas con sensores de posición.</td><td>Impide que el robot opere si la puerta está abierta.</td></tr><tr><td>Alfombras sensibles a presión o sensores ultrasónicos.</td><td>Detectar la presencia de personas en áreas peligrosas sin contacto físico.</td></tr><tr><td>Cuerdas de emergencia perimetrales.</td><td>Permitir al operario detener el sistema inmediatamente ante peligro.</td></tr><tr><td>Torres de señal (andon) con códigos de colores estándar.</td><td>Avisar del estado del robot: en operación, error, encendido, etc.</td></tr><tr><td>Controladores con funciones “safe move”</td><td>Impide movimientos peligrosos por error de programación o fallo lógico.</td></tr>
<tr><td>Control manual con botón de “velocidad reducida” (deadman switch).</td><td>Reduce velocidad al programar cerca del robot.</td></tr></tbody></table>
</div>

### Simulación en RobotStudio

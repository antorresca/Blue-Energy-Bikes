# Módulo 5: Celdas de Manufactura Robotizadas

## 1. Selección de Estación

- **Estación a robotizar:** Chasis  
- **Entrada:** Chasis pintado sin soportes  
- **Salida:** Chasis limpio y listo para ensamblaje  

**Descripción general:**  
La estación tiene como función principal preparar el esqueleto estructural de la motocicleta, sobre el cual se montarán los demás componentes.

**Actividades principales:**
- Recepción del chasis prefabricado o soldado.
- Limpieza del chasis (por aire comprimido o cepillo rotativo).
- Inserción de tuercas remachables o pernos de fijación.
- Liberación del chasis hacia la siguiente estación.



## 2. Hoja de ruta

<div align='center'>
  <img src='https://github.com/natc27/Blue-energy-landing/blob/main/Multimedia/FlowChart.png' width=600>
</div>



## 3. Descripción de la Celda Robotizada

La celda está diseñada para el alistamiento de soportes adicionales en el chasis, necesarios para el cableado y montaje posterior.

- **Estado de entrada:**  
  Chasis desempacado del proveedor, con suciedad superficial, pintado y sin soportes adicionales.

- **Estado de salida:**  
  Chasis limpio, con pintura intacta y con soportes colocados y soldados (tuercas remachables, pernos, etc.).

- **Takt Time:**  
  4.8 minutos (288 segundos), basado en un turno de 8 horas y 100 unidades/día.

- **Throughput Time:**  
  Tiempo objetivo de 20 minutos (1200 segundos), con el siguiente desglose:
  - Espera antes de entrar a la celda: 1 minuto
  - Tiempo de configuración: 6 minutos  
  - Proceso dentro de la celda: 11 minutos 
  - Transporte a la siguiente estación: 2 minutos



## 4. Elementos de la Celda

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
          <li>Robot soldador con efector final para soldadura con arco</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Manipuladores</td>
      <td>
        <ul>
          <li>Robot ABB IRB 2600ID</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Elementos de transporte</td>
      <td>
        <ul>
          <li>Banda transportadora para entrada/salida del chasis</li>
          <li>Soportes de sujeción para estabilizar el chasis de forma vertical durante su deslizamiento</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Otros</td>
      <td>
        <ul>
          <li>Panel HMI para supervisión del operador</li>
          <li>Sensores de presencia para detección del chasis</li>
          <li>Elementos de seguridad para personas en los alrededores</li>
          <li>Encerramiento físico y sensor de detección de apertura para detención inmediata</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
  
</div>

 

## 5. Peligros y Elementos de Seguridad

### Peligros

<div align='center'>
  
<table border="1">
  <thead>
    <tr>
      <th>#</th>
      <th>Peligro</th>
      <th>Descripción</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>Golpe del robot en movimiento</td><td>El operador puede recibir un impacto durante el periodo de programación, enseñanza o mantenimiento.</td></tr>
    <tr><td>2</td><td>Atrapamiento</td><td>Riesgo de atrapamiento entre el robot y otros elementos de la celda.</td></tr>
    <tr><td>3</td><td>Fallo en el sistema de parada de emergencia</td><td>La celda puede seguir funcionando en caso de emergencia.</td></tr>
    <tr><td>4</td><td>Contacto con piezas calientes</td><td>Algunas herramientas pueden calentarse durante la operación.</td></tr>
    <tr><td>5</td><td>Descarga eléctrica</td><td>Fallos en el aislamiento eléctrico o conexiones inseguras.</td></tr>
    <tr><td>6</td><td>Interferencia con el sistema de visión</td><td>Falsa lectura de posición o presencia por obstrucción o suciedad.</td></tr>
    <tr><td>7</td><td>Caída de herramientas</td><td>Herramientas mal sujetas pueden caer y causar daño.</td></tr>
    <tr><td>8</td><td>Colapso estructural o mal anclaje</td><td>Partes del sistema pueden soltarse por instalación deficiente.</td></tr>
    <tr><td>9</td><td>Ruido excesivo</td><td>El funcionamiento genera niveles de ruido superiores a lo permitido.</td></tr>
    <tr><td>9</td><td>Exceso de vibraciones</td><td>Las vibraciones no controladas pueden afectar la calidad del producto o generar un desgaste prematuro de los elementos.</td></tr>
    <tr><td>10</td><td>Acceso no autorizado</td><td>Personas no capacitadas pueden activar el sistema accidentalmente.</td></tr>
  </tbody>
</table>
</div>

### Evaluacion de Riesgos

<div align='center'>
  
<table border="1">
  <thead>
    <tr>
      <th>#</th>
      <th>Peligro</th>
      <th>Severidad (S)</th>
      <th>Frecuencia (F)</th>
      <th>Probabilidad de Evitación (P)</th>
      <th>Posibilidad de Exposición (E)</th>
      <th>HRN = S × F × P × E</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>Golpe del robot en movimiento</td><td>3</td><td>3</td><td>2</td><td>2</td><td>36</td></tr>
    <tr><td>2</td><td>Atrapamiento</td><td>3</td><td>3</td><td>2</td><td>2</td><td>36</td></tr>
    <tr><td>3</td><td>Fallo parada emergencia</td><td>4</td><td>2</td><td>2</td><td>2</td><td>32</td></tr>
    <tr><td>4</td><td>Contacto con piezas calientes</td><td>2</td><td>3</td><td>2</td><td>2</td><td>24</td></tr>
    <tr><td>5</td><td>Descarga eléctrica</td><td>4</td><td>2</td><td>2</td><td>1</td><td>16</td></tr>
    <tr><td>6</td><td>Interferencia sistema visión</td><td>2</td><td>2</td><td>3</td><td>2</td><td>24</td></tr>
    <tr><td>7</td><td>Caída de herramientas</td><td>3</td><td>2</td><td>2</td><td>2</td><td>24</td></tr>
    <tr><td>8</td><td>Colapso estructural</td><td>4</td><td>1</td><td>2</td><td>1</td><td>8</td></tr>
    <tr><td>9</td><td>Ruido excesivo</td><td>2</td><td>3</td><td>2</td><td>2</td><td>24</td></tr>
    <tr><td>9</td><td>Exceso de vibraciones</td><td>1</td><td>3</td><td>2</td><td>2</td><td>12</td></tr>
    <tr><td>10</td><td>Acceso no autorizado</td><td>3</td><td>2</td><td>2</td><td>3</td><td>36</td></tr>
  </tbody>
</table>
</div>

### Medidas de mitigación y componentes de seguridad

<div align='center'>
  
<table border="1">
  <thead>
    <tr>
      <th>#</th>
      <th>Peligro</th>
      <th>Mitigación / Componente de Seguridad</th>
      <th>Tipo de Acción</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>Golpe del robot</td><td>Sensores de presencia, barreras fotoeléctricas</td><td>Componente de seguridad</td></tr>
    <tr><td>2</td><td>Atrapamiento</td><td>Zonificación, diseño ergonómico</td><td>Mitigación + seguridad</td></tr>
    <tr><td>3</td><td>Fallo emergencia</td><td>Redundancia en botoneras, pruebas periódicas</td><td>Componente de seguridad</td></tr>
    <tr><td>4</td><td>Superficie caliente</td><td>Etiquetas de advertencia, EPP térmico</td><td>Mitigación</td></tr>
    <tr><td>5</td><td>Descarga eléctrica</td><td>Interruptores diferenciales, aislamientos, EPP</td><td>Seguridad + mitigación</td></tr>
    <tr><td>6</td><td>Visión obstruida</td><td>Mantenimiento regular del sistema de visión</td><td>Mitigación</td></tr>
    <tr><td>7</td><td>Caída herramientas</td><td>Revisión del acople y sistemas de sujeción</td><td>Mitigación</td></tr>
    <tr><td>8</td><td>Colapso estructural</td><td>Análisis estructural y pruebas de carga</td><td>Mitigación</td></tr>
    <tr><td>9</td><td>Ruido</td><td>Aislamiento acústico, protectores auditivos</td><td>Mitigación</td></tr>
    <tr><td>10</td><td>Acceso no autorizado</td><td>Cerramientos, control de acceso, señalización</td><td>Componente de seguridad</td></tr>
  </tbody>
</table>
</div>


## 6. Simulación en RobotStudio

## 7. Referencias

* Zhang, H., & Fang, Y. (2020). *Industrial Robotics Safety*. In _Industrial Robotics_, Capítulo 12.
* ISO 12100:2010 – Seguridad de las máquinas - Principios generales para el diseño.
* ISO 13849-1:2015 – Partes del sistema de control relacionadas con la seguridad.



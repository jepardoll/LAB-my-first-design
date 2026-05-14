# Sistema de Respaldo Eléctrico Residencial 

Este repositorio contiene la documentación técnica, diseño y solución de un del laboratorio My First Design. El laboratorio consistia en diseñar un Sistema Lógico de Respaldo Eléctrico que gestiona de manera automática la prioridad de alimentación entre la red eléctrica convencional y un banco de baterías, incorporando medidas de seguridad mediante un botón de paro de emergencia.

El proyecto está estructurado bajo tres dominios fundamentales del diseño electrónico: **Comportamental**, **Estructural** y **Físico**.

---

## 1. Dominio Comportamental

Este dominio define qué hace el sistema, sus interfaces y su lógica de control, sin entrar en detalles de la implementación del hardware interno.

### Diagrama de Caja Negra
Establece las señales de entrada (estímulos/sensores) y las señales de salida (actuadores/indicadores) del sistema.

![Diagrama de Caja Negra](Imagenes/DiagramaCajaNegra.jpg)

### Diagrama de Flujo
Describe el algoritmo de toma de decisiones para conmutar entre las fuentes de energía y responder a las condiciones de seguridad.

![Diagrama de Flujo](DiagramaFlujo.jpg)

### Tabla de Verdad y Ecuaciones Booleanas
Define la lógica combinacional exacta del sistema. La imagen muestra todas las combinaciones posibles de entrada y las ecuaciones booleanas simplificadas resultantes para cada salida.

![Tabla de Verdad y Ecuaciones](TablaVerdad.png)

* **C1 / C2:** Señales de control para la conmutación de energía.
* **CE:** Indicador de Casa Energizada.
* **B / SL / SRE:** Indicadores lógicos de estado (Batería, Sistema Listo, Sensor Red Eléctrica).

---

## ⚙️ 2. Dominio Estructural

Este dominio detalla *cómo* está construida la lógica interna mediante la interconexión de bloques y compuertas lógicas digitales.

### Diagrama de Compuertas
Esquemático que implementa las ecuaciones booleanas utilizando lógica digital estándar (compuertas **AND**, **OR** y **NOT**). Muestra el flujo de las señales desde las entradas hasta su respectiva salida lógica.

![Diagrama de Compuertas](DiagramaCompuertas.png)

---

## 🔌 3. Dominio Físico

Este dominio abarca la materialización del circuito, considerando componentes electrónicos reales, niveles de voltaje y etapas de aislamiento/potencia.

### Circuito Físico
Implementación del esquemático electrónico. Incluye las entradas configuradas con resistencias de *pull-down*, la unidad central de procesamiento lógico, la etapa de señalización visual mediante LEDs y la etapa de conmutación de potencia basada en relés.

![Circuito Físico](CircuitoFisico.png)

---

## 📋 Especificaciones del Sistema

| Tipo | Señal | Descripción |
| :--- | :--- | :--- |
| **Entrada** | `P` | Botón de Paro (Emergencia) |
| **Entrada** | `RE` / `F1` | Disponibilidad de Red Eléctrica |
| **Entrada** | `Ba` / `F2`| Disponibilidad de Batería de Respaldo |
| **Entrada** | `Ls` / `L` | Sensor de Luz Solar |
| **Salida** | `CE` | Casa Energizada |
| **Salida** | `C1` / `C2` | Control de Relés (Red / Batería) |
| **Salida** | `IL` / `IB` / `IRE` | LEDs indicadores de estado |

---
*Documentación generada para el modelado de sistemas lógicos y arquitectura de hardware.*

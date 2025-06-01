
# Simulación de Trayectoria Circular del Robot Móvil X3

## Objetivo

Simular una trayectoria circular del robot móvil X3 en un entorno virtual utilizando ROS 2 y Gazebo, demostrando el control básico de movimiento mediante comandos de velocidad.

---

##  Pasos Realizados

### 1. Configuración del Entorno de Trabajo

- Se creó un espacio de trabajo ROS 2 llamado `x3_ws`.
- Se clonó el repositorio:  
  ```bash
  git clone https://github.com/taviox/x3_ws.git
  ```
- Se compilaron los paquetes necesarios:
  ```bash
  colcon build
  source install/setup.bash
  ```

### 2. Descripción del Robot

- Se definió el modelo del robot en un archivo `.xacro`, especificando:
  - Estructura del robot (`base_link`, `base_footprint`, etc.).
  - Ruedas con joints de tipo `continuous`.
  - Mallas visuales para representar el robot en Rviz y Gazebo.

### 3. Lanzamiento de la Simulación

- Se utilizó un archivo de lanzamiento (`.launch.py`) para iniciar Gazebo y Rviz con el modelo del robot:
  ```bash
  ros2 launch omni_bringup simple_velocity_controller.launch.py
  ```

### 4. Control del Robot

- Se enviaron comandos de velocidad para mover el robot en una trayectoria circular:
  ```bash
  ros2 topic pub /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.1}, angular: {z: 0.2}}"
  ```
- Se observó el movimiento del robot en Gazebo y Rviz, verificando que seguía una trayectoria circular.

### 5. Ajustes y Observaciones

- Se ajustaron los valores de velocidad lineal y angular para obtener una trayectoria circular más precisa.
- Se notó que las ruedas no giraban visualmente en la simulación, ya que no se implementó un plugin de control de ruedas. Sin embargo, el movimiento del robot era correcto.

---

##  Video de la Simulación

Se adjunta un video [aquí](https://drive.google.com/file/d/1__XXZ5eXunOfsvB428ExPHfWK_q-WWGe/view?usp=drive_link)  que muestra el robot X3 siguiendo una trayectoria circular en Gazebo.

---

##  Conclusiones

- Se logró simular exitosamente una trayectoria circular del robot móvil X3 utilizando ROS 2 y Gazebo.
- El control básico mediante comandos de velocidad fue suficiente para demostrar el movimiento deseado.
- Aunque las ruedas no giraban visualmente, el comportamiento del robot en la simulación fue correcto.
- Este proyecto sienta las bases para futuras implementaciones de control más avanzadas y realistas.

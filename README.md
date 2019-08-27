Simulador usado pela equipe UFRN no Desafio de Robótica Petrobrás CBR 2019. O simulador roda no ROS 16.04 Kinetic.

# Instalação

Instalação ROS -> https://omecatronico.com.br/blog/439-2/

Caso já tenha o ROS kinetic instalado:

**Instalar o hector_quadrotor** (tirado desse site https://darienmt.com/autonomous-flight/2018/10/20/flying-ros-and-hector.html)

```bash
mkdir ~/desafio_petrobras
cd ~/desafio_petrobras
wstool init src https://raw.github.com/tu-darmstadt-ros-pkg/hector_quadrotor/kinetic-devel/tutorials.rosinstall
```

Instale também esses pacotes


```bash
sudo apt-get install ros-kinetic-geographic-info
sudo apt-get install ros-kinetic-ros-control
sudo apt-get install ros-kinetic-gazebo-ros-control
```

**Clonar o repositório cbr_petrobras:**

```bash
cd ~/desafio_petrobras/src
git clone https://github.com/Natalnet/cbr_petrobras.git
```

**Compilar**

```bash
cd ~/desafio_petrobras
catkin_make
```

# Rodar o simulador

```bash
source ~/desafio_petrobras/devel/setup.bash
roslaunch cbr_petrobras petrobras_flight.launch
```

**Controlando o drone**

Antes de mais nada deve-se ativar os motores do drone com o comando:

```bash
rosservice call /enable_motors "enable:true"
```

que é confirmado com a mensagem *success: True*

O pacote hector_quadrotor_teleop oferece 3 tipos de controle:

Controle sony

```bash
roslaunch hector_quadrotor_teleop sony_dualshock3.launch
```

Controle xbox

```bash
roslaunch hector_quadrotor_teleop xbox_controller.launch
```

Alternativamente também é possível mover o drone controlando a velocidade pelo tópico */cmd_vel*:

Copie e cole o comando no terminal:
```bash
rostopic pub /cmd_vel 
```
aperte tab duas vezes para completar o resto da mensagem. Ai é só escolher a velocidade na dimensão desejada.

```bash
rostopic pub /cmd_vel geometry_msgs/Twist "linear:
  x: 0.0
  y: 0.0
  z: 0.0
angular:
  x: 0.0
  y: 0.0
  z: 0.0" 
```

Mais alternativamente ainda ***ALTERNATIVE INTENSIFIES***  você pode setar uma pose desejada para o drone no tópico */command/pose*

```bash
rostopic pub /command/pose geometry_msgs/PoseStamped "header: 
  seq: 0
  stamp:
    secs: 0
    nsecs: 0
  frame_id: 'world'
pose:
  position:
    x: 2.0
    y: 2.0
    z: 2.0
  orientation:
    x: 0.0
    y: 0.0
    z: 1.0
    w: 0.0" 
```

> Importante notar que o *frame_id* deve ser 'world'.

Boa sorte.

Simulador usado pela equipe UFRN no Desafio de Robótica Petrobrás CBR 2019. O simulador roda no ROS 16.04 Kinetic.

# Instalação
Instalar o hector_quadrotor

```bash
mkdir ~/hector_quadrotor_tutorial
cd ~/hector_quadrotor_tutorial
wstool init src https://raw.github.com/tu-darmstadt-ros-pkg/hector_quadrotor/kinetic-devel/tutorials.rosinstall
```
Ou siga esse tutorial -> [https://darienmt.com/autonomous-flight/2018/10/20/flying-ros-and-hector.html]

Ai é só clonar esse repositório no mesmo workspace do stack hector_quadrotor, compilar e rodar

```bash
roslaunch cbr_petrobras petrobras_flight.launch
```

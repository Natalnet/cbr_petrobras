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

Pacotes adicionais


```bash
sudo apt-get install ros-kinetic-geographic-info
sudo apt-get install ros-kinetic-ros-control
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


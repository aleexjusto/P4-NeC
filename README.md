# P4-NeC
## Docker network

**Crear unha rede en docker**

Para crear a rede empreguei o seguinte comando `docker network create --driver=bridge --subnet=172.28.0.0/16 --ip-range=172.28.5.0/24 --gateway=172.28.5.254 alexrede ` , onde o nome da rede é alexrede.

**Crear dous contenedores unidos a esa rede**

Para crear un contenedor nesta rede, empreguei o comando `docker run -itd --name=justo2 --network=alexrede ubuntu`e o comando `docker run -itd --name=justo1 --network=alexrede ubuntu`, onde debemos por o nombre que queremos que teña cada contenedor, a rede á que unimos (neste caso alexrede) e por último a imaxe.


**Comprobar que os contenedores están na rede**

Para ver os contenedores da rede, empregamos o comando `docker network inspect alexrede`.


**Comprobar que os contenedores poden verse entre eles**

Para comprobalo, necesitamos entrar na terminal dun dos contenedores, e instalar ping, a través de comando `apt install -y iputils-ping`. Unha vez feito, si estamos no contenedor justo1, empregamos o comando `ping justo2` .

**Listar os contenedores conectados á rede**

Para listar os contenedores, empregamos o comando `docker network ls`onde no meu caso listou o seguinte:

```
NETWORK ID     NAME       DRIVER    SCOPE
cef799e2c06d   alexrede   bridge    local
```

**Listar as propiedades da rede**
Para ver as propiedades, simplemento usaremos o comando `docker network inspect alexrede`.

**Crea outra rede**

Para crear outra rede empregaremos o comando do inicio, pero cambiando o nome e as direccions IP, é dicir, `docker network create --driver=bridge --subnet=172.29.0.0/16 --ip-range=172.29.5.0
/24 --gateway=172.29.5.254 yustiiix` 

**Lanza dous contenedores novos conectados a esa nova rede**

docker run -itd --name=alex1 --network=yustiiix ubuntu
docker run -itd --name=alex2 --network=yustiiix ubuntu

**Comproba as posibles conexións entre os 4 contenedores**
DESDE ALEX1
ping justo1 -- da error al ser de distinta red
ping alex2 -- da ping al ser de la misma red

## Docker compose: 

**Segue os pasos da guía de iniciación de docker-compose, e explica coas túas palabras os pasos que segues e qué fan**

~/composetest$ docker compose up
http://localhost:8000/

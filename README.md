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

Para crear outra rede empregaremos o comando do inicio, pero cambiando o nome e as direccions IP, é dicir, `docker network create --driver=bridge --subnet=172.29.0.0/16 --ip-range=172.29.5.0/24 --gateway=172.29.5.254 yustiiix` 

**Lanza dous contenedores novos conectados a esa nova rede**

Como fixemos anteriormente, empreguei os seguintes comandos:
```
docker run -itd --name=alex1 --network=yustiiix ubuntu
docker run -itd --name=alex2 --network=yustiiix ubuntu
```

**Comproba as posibles conexións entre os 4 contenedores**

Como fixen anteriormente, instelei ping no contenedor alex1, e primeiro fixen ping a justo1 da outra rede co comando `ping justo1`, onde ao ser de distinta rede pis da erro, mentre que facendo `ping alex2` non da erro ao ser da mesma rede.

## Docker compose: 

**Segue os pasos da guía de iniciación de docker-compose, e explica coas túas palabras os pasos que segues e qué fan**
Seguindo os pasos da web, primeiro facemos o arquivo, onde metemos os ficheiros necesarios, e ao realizar o comando `docker compose up` e buscar no navegador o noso localhost, poderemos ver tanto na páxina como na terminal o número de veces que accedimos.

**Agora que sabes algo máis de docker-compose, crea un arquivo (ou varios arquivos) de configuración que ó ser lanzados cun docker-compose up, resulten nunha rede docker á que estean conectados 3 contenedores, explica os parámetros do .yaml usado**

Os parametros do documento son os seguintes:
Versióm: versión de docker compose
Volumes : directorio nun directorio do contenedor
Image: neste caso empreguei nginx
Container_name: o nome que queremos do contenedor
Networks: redes as que están conectadas
ports: mapeo o porto 

**Busca e proba 4 parámetros e configuracións diferentes que podes incluir no arquivo compose, explica qué fan. (por exemplo diferentes cousas que facer coa opción RUN)**

Build: se queremos crear una imaxe 
Restars: para configurar o reinicio automatico
Expose: o porto que poñamos queda exposto para outros contenedores pero sin que esté accesible dende o host
Privileged(true/false): da permisos ao contenedor, o que permite o acceso completo ao resto de host.





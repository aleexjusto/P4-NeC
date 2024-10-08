# P4-NeC
**Docker network**

**Crear unha rede en docker**
docker network create --driver=bridge --subnet=172.28.0.0/16 --ip-range=172.28.5.0/24 --gateway=172.28.5.254 alexrede

**Crear dous contenedores unidos a esa rede**
docker run -itd --name=justo2 --network=alexrede ubuntu
docker run -itd --name=justo1 --network=alexrede ubuntu


**Comprobar que os contenedores están na rede**
docker network inspect alexrede


**Comprobar que os contenedores poden verse entre eles**

**Listar os contenedores conectados á rede**

**Listar as propiedades da rede**

**Crea outra rede**

**Lanza dous contenedores novos conectados a esa nova rede**

**Comproba as posibles conexións entre os 4 contenedores**

**Docker compose:**

**Segue os pasos da guía de iniciación de docker-compose, e explica coas túas palabras os pasos que segues e qué fan**

**Agora que sabes algo máis de docker-compose, crea un arquivo (ou varios arquivos) de configuración que ó ser lanzados cun docker-compose up, resulten nunha rede docker á que estean conectados 3 contenedores, explica os parámetros do .yaml usado**

**Busca e proba 4 parámetros e configuracións diferentes que podes incluir no arquivo compose, explica qué fan. (por exemplo diferentes cousas que facer coa opción RUN)**

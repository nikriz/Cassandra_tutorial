# Installation Guide 

---

### Install Java SDK (1.8.0_251)


#### 1. Run installation file

Download from https://www.oracle.com/java/technologies/javase/javase8u211-later-archive-downloads.html considering your OS.

Check your install directory while installing

ex. `C:\Program Files\Java\jdk1.8.0_251`


#### 2. Add environment variables

ex. 

JAVA_HOME: `C:\Program Files\Java\jdk1.8.0_251`

PATH: `C:\Program Files\Java\jdk1.8.0_251\bin` (Append)


**Windows**: Win+R `sysdm.cpl` → Advanced(고급) 

→ Environmental Variables(환경 변수) → New or Edit(새로 만들기/편집)


**Linux/Mac**: Open `~/.bash-profile`(Mac) or `~/.bashrc`(Linux) 

→ Add line `export JAVA_HOME=[DIRECTORY]` and `export PATH=$PATH:[DIRECTORY]` to append

→ Run `source ~/.bash-profile` or `source ~/.bashrc`


#### 3. Check installation

`java -version` in cmd/terminal

---

### Install Cassandra (3.0.27)

#### 1. Download installation file

Download from https://www.apache.org/dyn/closer.lua/cassandra/3.0.27/apache-cassandra-3.0.27-bin.tar.gz

Unzip to your install directory.

#### 2. Add environment variables

ex. 

CASSANDRA_HOME: `C:\Cassandra\apache-cassandra-3.0.27`

PATH: `C:\Cassandra\apache-cassandra-3.0.27\bin` and `C:\Cassandra\apache-cassandra-3.0.27\tools\bin` (Append)

#### 3. Check installation

`cassandra` in cmd/terminal

---

### Install Python (2.7 for cqlsh, 3.8 for Datastax Python Driver)

#### Install Anaconda

Download from https://www.anaconda.com/products/distribution

#### Set environment with wanted version

`conda create -n cas python=2.7` or `3.8`

`conda activate cas`

#### Test

`cqlsh` and `SHOW VERSION` in python 2.7

`pip install cassandra-driver` and `python -c 'import cassandra; print cassandra.__version__'` in python 3.8


---


### Install Docker (for distributed environment, copied from Assignment 1)

For Windows/Mac

* Docker-desktop: [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/) 

For Ubuntu

* Docker: [https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)
* docker-compose: [https://docs.docker.com/compose/install/linux/](https://docs.docker.com/compose/install/linux/) 

For cassandra setup commands, see the tutorial in the jupyter notebook. 


### Q&As

(Update 2022.10.11) 

- Search for `8u251` at JAVA installation file download directory, install the one starting with `jdk` and that suits your OS

- (MAC) JAVA Mac Default Installation Directory: `/Library/Java/JavaVirtualMachines/jdk1.8.0_251.jdk/Contents/Home`

- (MAC) If docker commands in distributed setting get errors / or dockers are working but not connected each other when `nodetool status`
  
  change `$INSTANCE1=[~]` to `export INSTANCE1=[~]` due to shell command differences. 

- If python cassandra driver doesn't work on jupyter notebook, but works in anaconda prompt, reinstall jupyter notebook in the environment with `conda install jupyter`

- If shell commands doesn't work on jupyter notebook check the PATH with `!echo $PATH` or `sys.path` and manually update the missing directories with `!export PATH=$PATH:[~] or sys.path.append([~])`

- For timestamp, insert with string format referring https://docs.datastax.com/en/cql-oss/3.x/cql/cql_reference/timestamp_type_r.html 


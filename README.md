```bash
# 1. Check and Install Java
javac --version
sudo apt install default-jdk
sudo apt install default-jre
```

```bash
# 2. Create working directory
mkdir abc
cd abc
```

```bash
# 3. Hadoop Setup
tar xvzf hadoop-3.2.2.tar.gz
cd hadoop-3.2.2
gedit bash.sh
# → In gedit, paste exactly these lines:
# export JAVA_HOME=$(readlink -f $(which javac) | awk 'BEGIN {FS="/bin"} {print $1}')
# export PATH=$(echo $PATH):$(pwd)/bin
# export CLASSPATH=$(hadoop classpath)
# → Save & close
source bash.sh
# Verify JAVA_HOME and PATH are correct
hadoop
```

```bash
# 4. Spark Setup
# (keep spark tar file in ~/abc folder)
hadoop
tar xvzf spark-3.5.2-bin-hadoop3.tgz
cd spark-3.5.2-bin-hadoop3
gedit bash.sh
# → In gedit, paste exactly this line:
# export PATH=$(echo $PATH):$(pwd)/bin
# → Save & close
source bash.sh
spark-shell --version
```

```bash
# 5. Pig Setup
# (keep pig tar file in ~/abc folder)
hadoop
tar -xvf pig-0.17.0.tar.gz
cd pig-0.17.0
gedit bash.sh
# → In gedit, paste exactly these lines:
# export PIG_INSTALL=$(pwd)
# export PATH=$PATH:$(pwd)/bin
# → Save & close
source bash.sh
pig -version
pig
```

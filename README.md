# javaJDKTutorial
Este repositório armazena pontos importantes para compilar e executar projetos Java no terminal (Windows e Linux), além de uma forma de fazer um projeto que funcione em diferentes IDEs (no caso, VSCode e NetBeans).
## JDK
Inicialmente, devemos instalar o [JDK (Java Development Kit)](https://pt.wikipedia.org/wiki/Java_Development_Kit), cujos downloads se encontram no [site da Oracle](https://www.oracle.com/br/java/technologies/downloads/). Se optar por algum update específico (como o JDK 21.0.7, ao invés do mais atual JDK 21.0.8), pode encontrá-lo no Java Archive, de acordo com a versão, em links do tipo [https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html), substituindo o '21' do link pela versão desejada (dentre as disponíveis 11, 17, 21...), se for o caso, com exceção da versão 8, cujos updates antigos se encontram em [https://www.oracle.com/br/java/technologies/javase/javase8-archive-downloads.html](https://www.oracle.com/br/java/technologies/javase/javase8-archive-downloads.html).

Caso queira, pode instalar pelo terminal do Linux, usando os comandos abaixo.
Pesquisar versoes do jdk disponiveis para download no linux
```
apt search openjdk-.*-jdk
```

baixar alguma no linux (17 no exemplo abaixo)
```
sudo apt install openjdk-17-jdk
```


escolher versao a ser usada, dentre as instaladas no linux
```
sudo update-alternatives --config java
```


saber a versao atual do jdk
```
java -version
```

verificar as versoes ja instaladas no windows:
```
dir "C:\Program Files\Java\"
```
mudar a versao a ser utilizada:
```
set JAVA_HOME=C:\Program Files\Java\jdk-21
```
O comando acima mudaria para a versao 21; caso queira outra, basta mudar o número no comando.



Os comandos de compilação e execução são os mesmos nos dois sistemas operacionais; usemos os arquivos Java deste repositório como exemplo:
Para compilar, é usado o comando *javac* do JDK, e digitamos, separados por espaço, os arquivos .java a serem compilados.
```
javac src/Funcs.java src/Main.java
```
Para executar, usamos o comando *java*, seguido de *-cp*, da pasta que contém o arquivo e apenas o nome do arquivo que contém a função *main*:
```
java -cp src Main
```
Observe que o arquivo Java que contém a função *main* possui o nome *Main* nesse caso, mas não é necessário que ele seja nomeado dessa forma.

compilar projeto maven
```
javac -d target/classes -cp src/main/java src/main/java/com/github/tavinescada/*.java
```
note que a última parte do comando, "com/github/tavinescada", coincide com o *group ID* definido como "com.github.tavinescada". Se o *group ID* fosse "com.example", o comando deveria ser
```
javac -d target/classes -cp src/main/java src/main/java/com/example/*.java
```

Executar o projeto maven
```
java -cp target/classes com.github.tavinescada.Main
```
note que o comando de execução também deve coincidir com o *group ID*. Se ele fosse "com.example", o comando deveria ser
```
java -cp target/classes com.example.Main
```

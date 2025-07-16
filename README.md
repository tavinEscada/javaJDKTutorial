# javaJDKTutorial
Este repositório armazena pontos importantes para compilar e executar projetos Java no terminal (Windows e Linux). Inicialmente, devemos instalar o JDK (Java Development Kit), disponível no [site da Oracle](https://www.oracle.com/br/java/technologies/downloads/). ********



Os comandos de compilação e execução são os mesmos nos sistemas operacionais; usemos os arquivos Java deste repositório como exemplo:
Para compilar, é usado o comando *javac* do JDK, e digitamos, separados por espaço, os arquivos .java a serem compilados.
```
javac src/Funcs.java src/Main.java
```
Para executar, usamos o comando *java*, seguido de *-cp*, da pasta que contém o arquivo e apenas o nome do arquivo que contém a função *main*:
```
java -cp src Main
```
Observe que o arquivo Java que contém a função *main* possui o nome *Main* nesse caso, mas não é necessário que ele seja nomeado dessa forma.

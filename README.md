# javaJDKTutorial
Este repositório armazena pontos importantes para compilar e executar projetos Java no terminal (Windows e Linux). Note que existem duas classes no repositório, que podem ser usadas como exemplo de teste para os comandos usados.
## JDK
Inicialmente, deve-se instalar o [JDK (Java Development Kit)](https://pt.wikipedia.org/wiki/Java_Development_Kit). Os [downloads mais recentes](https://www.oracle.com/br/java/technologies/downloads/) são referentes às versões 21 e 24. Ao optar por alguma versão anterior (8, 11, e 17, ou updates anteriores do 21 e 24), pode-se encontrá-la no Java Archive:
* [JDK 8](https://www.oracle.com/br/java/technologies/javase/javase8-archive-downloads.html)
* [JDK 11](https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html)
* [JDK 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
* [Versões antigas do JDK 21](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html)
* [Versões antigas do JDK 24](https://www.oracle.com/java/technologies/javase/jdk24-archive-downloads.html)

É possível manejar o JDK pelo terminal, como mostrado a seguir.

### Terminal do Linux
* Pesquisar versões do JDK disponíveis para download no Linux:
```
apt search openjdk-.*-jdk
```

* Instalar alguma (como a 17 no exemplo abaixo):
```
sudo apt install openjdk-17-jdk
```

* Instalar update específico (JDK 21.0.7, por exemplo):
```
sudo apt install openjdk-21-jdk=21.0.7+6~us1-0ubuntu1~24.04 
```

* Saber a versão ativa do JDK:
```
java -version
```

* Escolher versão a ser usada, dentre as já instaladas:
```
sudo update-alternatives --config java
```

### Terminal do Windows
* Verificar versão ativa:
```
java -version
```
  
* Verificar as versões já instaladas:
```
dir "C:\Program Files\Java\"
```

* Mudar a versão a ser utilizada (como a 21 no exemplo abaixo):
```
set JAVA_HOME=C:\Program Files\Java\jdk-21
```

## Compilação e execução
Os comandos de compilação e execução são os mesmos nos dois sistemas operacionais; usemos os arquivos Java deste repositório como exemplo:

* Para compilar, é usado o comando *javac* do JDK, e digitamos, separados por espaço, os arquivos .java a serem compilados.
```
javac src/Funcs.java src/Main.java
```
É possível, nesse caso, compilar os arquivos de forma mais simples: como todos os arquivos em questão estão na mesma pasta, podemos usar
```
javac src/*.java
```
Assim, selecionamos todos os arquivos.java da pasta *src*.

* Para executar, tenhamos em mente o *arquivo.java* que contém a função *main* e que a compilação cria arquivos .class referentes aos arquivos.java no projeto. Usamos, então, o comando *java*, seguido de *-cp*, da pasta que contém o arquivo .class referente àquele com a *main* e, por fim, o nome do arquivo em questão (no nosso caso, a pasta é *src*, e o arquivo com a *main* tem o nome *Main*). No caso do projeto no repositório, portanto, o comando é:
```
java -cp src Main
```
Observe que o arquivo que contém a função *main* possui o nome *Main.java* nesse caso, mas não é necessário que ele seja nomeado dessa forma.

Para fins de organização, podemos criar, na pasta do projeto, um diretório auxiliar, algo como 'target/classes', onde serão armazenados os arquivos .class que são criados na compilação. Nesse caso, compilamos com
```
javac -d target/classes -cp src src/*.java
```
de forma a informar o destino (target/classes) dos arquivos .class, e executamos tudo com
```
java -cp target/classes Main
```
visto que nesse caso a pasta que contém o *Main.class* é a target/classes.


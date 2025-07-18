# javaJDKTutorial
Este repositório armazena pontos importantes para compilar e executar projetos Java no terminal (Windows e Linux).
## JDK
Inicialmente, devemos instalar o [JDK (Java Development Kit)](https://pt.wikipedia.org/wiki/Java_Development_Kit). Os [downloads mais recentes](https://www.oracle.com/br/java/technologies/downloads/) são referentes às versões 21 e 24. Se optar por alguma versão anterior (como o JDK 17 ou updates anteriores do 21 e 24), pode encontrá-la no Java Archive:
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


* Instalar update específico:
```

```


* Saber a versão ativa do JDK:
```
java -version
```

* Escolher versão a ser usada, dentre as já instaladas:
```
sudo update-alternatives --config java
```

## Terminal do Windows
* Verificar versão ativa:
```
java -version
```
  
* Verificar as versões já instaladas no Windows:
```
dir "C:\Program Files\Java\"
```

* Mudar a versão a ser utilizada (como a 21 no exemplo abaixo):
```
set JAVA_HOME=C:\Program Files\Java\jdk-21
```

## Compilação e execução
Os comandos de compilação e execução são os mesmos nos dois sistemas operacionais; usemos os arquivos Java deste repositório como exemplo:
Para compilar, é usado o comando *javac* do JDK, e digitamos, separados por espaço, os arquivos .java a serem compilados.
```
javac src/Funcs.java src/Main.java
```
Para executar, tenhamos em mente o *arquivo.java* que contém a função *main*; usamos o comando *java*, seguido de *-cp*, do endereço do arquivo - com o nome das pastas separaods por espaço - e, por fim, o nome do arquivo. No caso do projeto no repositório, o comando é:
```
java -cp src Main
```
Observe que o arquivo que contém a função *main* possui o nome *Main.java* nesse caso, mas não é necessário que ele seja nomeado dessa forma.

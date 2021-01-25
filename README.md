# JAVA

Java é uma linguagem de programação orientada a objetos desenvolvida na década de 90 por uma equipe de programadores chefiada por James Gosling, na empresa Sun Microsystems. Em 2008 o Java foi adquirido pela empresa Oracle Corporation. Diferente das linguagens de programação modernas, que são compiladas para código nativo, a linguagem Java é compilada para um bytecode que é interpretado por uma máquina virtual (Java Virtual Machine, mais conhecida pela sua abreviação JVM). A linguagem de programação Java é a linguagem convencional da Plataforma Java, mas não é a sua única linguagem. J2ME Para programas e jogos de computador, celular, calculadoras, ou até mesmo o rádio do carro.
Em 1991, na Sun Microsystems, foi iniciado o Green Project, o berço do Java, uma linguagem de programação orientada a objetos. Os mentores do projeto eram Patrick Naughton, Mike Sheridan, e James Gosling. Eles acreditavam que, eventualmente, haveria uma convergência dos computadores com os equipamentos e eletrodomésticos frequentemente usados pelas pessoas no seu dia-a-dia.

Para provar a viabilidade desta ideia, 13 pessoas trabalharam arduamente durante 18 meses. No verão de 1992 eles emergiram de um escritório de Sand Hill Road, no Menlo Park, com uma demonstração funcional da ideia inicial. O protótipo se chamava *7 (lê-se “Star Seven”), um controle remoto com uma interface gráfica touchscreen. Para o *7, foi criado um mascote, hoje amplamente conhecido no mundo Java, o Duke. O trabalho do Duke no *7 era ser um guia virtual ajudando e ensinando o usuário a utilizar o equipamento. O *7 tinha a habilidade de controlar diversos dispositivos e aplicações. James Gosling especificou uma nova linguagem de programação para o *7. Gosling decidiu batizá-la de “Oak”, que quer dizer carvalho, uma árvore que ele podia observar quando olhava através da sua janela.
Exemplos de código
Método main
O método main é onde o programa inicia. Pode estar presente em qualquer classe. Os parâmetros de linha de comando são enviados para o array de Strings chamado args.

public class OláMundo {
   /**
* Método que executa o programa
* public = É visto em qualquer lugar da aplicação. É o modificador de acesso
* static = é iniciado automaticamente pela JVM, sem precisar de uma instância
* void = Método sem retorno (retorno vazio)
* main = Nome do método, que é obrigatório ser este para que seja executado como o método principal da aplicação. A aplicação só pode ter um método denominado main. Recebe como parâmetro um array de String.
* String[] args = Array de argumentos que podem ser repassados na chamada do programa.
* /
   public static void main(String[] args) {
      System.out.println("Olá, Mundo!"); //Imprime na tela a frase
   }
}
Classes
Exemplo:

public abstract class Animal {
   public abstract void fazerBarulho();
}

public class Cachorro extends Animal {
   public void fazerBarulho() {
      System.out.println("AuAu!");
   }
}

public class Gato extends Animal {
   public void fazerBarulho() {
      System.out.println("Miau!");
   }
}
O exemplo acima cria a classe Animal e duas classes derivadas de Animal. É importante observar que nas classes derivadas temos a redefinição do método fazerBarulho(). Esta redefinição é classificada como uma sobreposição (override) de métodos. O conceito de sobreposição somente pode ser identificado e utilizado quando temos classes dispostas em um relacionamento de herança.

Java não suporta herança múltipla, devido a possibilidade de uma classe pai ter um método com o mesmo nome de outra classe pai, e gerar possíveis falhas ao chamar o método, e todas as classes em Java derivam da classe Object. A única possibilidade de se ver herança múltipla em Java é no uso de interfaces, pois uma classe pode implementar várias interfaces.

Interfaces
Uma interface modela um comportamento esperado. Pode-se entendê-la como uma classe que contenha apenas métodos abstratos. Embora uma classe não possa conter mais de uma super classe, a classe pode implementar mais de uma interface. Exemplo:

public interface Pesado {
   double obterPeso();
}

public interface Colorido {
   Color obterCor();
}

public class Porco extends Animal implements Pesado, Colorido {
   public void fazerBarulho() {
      System.out.println(" Óinc!");
   }

   // Implementação da interface Pesado
   public double obterPeso() {
      return 50.00;
   }

   // Implementação da interface Colorido
   public Color obterCor() {
      return Color.BLACK;
   }

   // Uma propriedade só do porco
   public boolean enlameado() {
      return true;
   }
}
Objetos anônimos
Podemos ter também objetos anônimos, onde não é necessário instanciar o objeto em uma variável para utilizá-lo. Exemplo:

public class MostraBarulho {
   public static void main(String args[]) {
      new Cavalo().fazerBarulho(); // Objeto anônimo.

      // Abaixo um objeto e classe anônimos!
      new Animal() {
         public void fazerBarulho() {
            System.out.println("QUAC!");
         }
      }.fazerBarulho();
   }
}
Programação funcional
A partir da versão 8, o Java adiciona aspectos de linguagem funcional, permitindo utilizar técnicas funcionais, como mapeamento, redução, bem como tratar funções como variáveis. Para tanto, a linguagem utiliza interfaces para esse tipo de manipulação, quase que eliminando a necessidade do uso das chamadas classes anônimas. [11]

Exemplo:

import java.util.ArrayList;
import java.util.List;

public class Main {

   public static void main(String[] args) {
      // Lista de paradigmas
      List<String> paradigmas = new ArrayList<>();

      // Adiciona paradigmas
      paradigmas.add("Genérico (1.5)");
      paradigmas.add("Funcional (8)");

      // Abre uma stream
      paradigmas.stream()
         // Faz todos os textos na lista ficarem em maiúsculo
         .map(String::toUpperCase)
         // Faz loop em todos paradigmas em maiúsculo.
         .forEach(paradigma -> System.out.println(paradigma)); // ou .forEach(System.out::println);
   }
}
Ferramentas
Frameworks
É possível utilizar frameworks para facilitar o desenvolvimento de aplicações, dos quais os mais utilizados podem-se destacar:

Hibernate ferramenta para ORM
Junit ferramenta para auxiliar na criação de testes unitários
Log4j ferramenta para facilitar a criação de logs na aplicação
Spring ferramenta que auxilia principalmente implementação de injeção de dependências e inversão de controle
Struts controlador MVC (Model 2) web

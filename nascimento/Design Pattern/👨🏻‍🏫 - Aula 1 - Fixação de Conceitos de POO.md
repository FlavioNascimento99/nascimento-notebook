# 🏗 Introdução
Dentro da área de desenvolvimento de Software é de suma importância ter a visão de importantes métricas como custo e tempo, pois ambas, ao meu ver são sinônimos, afinal, tempo é dinheiro, consequentemente recurso. 

Acontece que um problema aparente no inicio da história do desenvolvimento de software é o **Alto Acoplamento** de código, que implica em camadas dificultadoras relacionadas a manutenção do mesmo.

É citado a necessidade de uma API capaz de conectar com Facebook e Twitter/X com o Reddit ou/e Instagram. Pra isso ser possível de maneira simples é necessário possuir uma visão futura acerca de um sistema projetado de maneira escalável, que permita a extensão das funcionalidades daquele software (ou middleware no exemplo, como um intermediário).


#### 🔐 Encapsulamento
Se trata de uma maneira estrutural de manter a "casa em ordem" dentro de um código Orientado à Objetos, garantindo a imutabilidade de atributos ou métodos de uma Classe. 

Por exemplo, imagine dentro de um sistema bancário onde o atributo *saldo* não possui uma assinatura *private* que por consequência, permite a alteração do valor ali inserido apenas instanciando a classe de referência, seria um desastre.  Por isso é tão importante entender esse conceito, pois isso vai garantir total controle a possíveis alterações desse dado. 

Para evitar esse tipo de *vulnerabilidade* primeiro teríamos que implementar a assinatura *private* que garantiria a segurança daquele dado, este que por sua vez possuiria métodos específicos para acessá-lo com o objetivo de modificar seu valor, como por exemplo um método *sacar()* ou *depositar()*. 

#### 🎭 Polimorfismo
Polimorfismo é a capacidade de um mesmo método ou comportamento possuir diferentes implementações, variando apenas de acordo com o contexto no qual o mesmo será inserido.

Imagine uma Classe Calculadora, que possui diferentes métodos de soma, um para números inteiros *Int* outro para números "quebrados" *Double*, essa é conhecida como **Polimorfismo de Sobrecarga**(*ou Overloading*), mesma Classe, Nome, mas diferentes Parâmetros.

Agora imagine a seguinte `Classe Animal`, que possui um método `fazerSom()`, mas que possui uma `Classe Gato extends Animal`, que por sua vez estará hábil à utilizar dos métodos de seu pai (nesse caso `fazerSom()`), porém existe um detalhe, ao utilizarmos `fazerSom()`de `Gato()` o retorno do método será diferente, neste caso estamos falando de **Polimorfismo de Substituição** (ou *Overloading*), mesmo método porém, redefinido em uma subclasse.

Existem inúmeras maneiras de se utilizar polimorfismo, a mais simples é na criação de uma Classe abstrata com métodos e retornos genéricos que serão modificados em suas classes filha.


#### 📃 Interface
Particularmente não gosto da ideia de entender como um "*contrato*" de Classe, mas sinta-se livre de fazer essa leitura, mas Interface é um contrato de Classe, que diz a mesma o que ela possui e o que pode fazer, mas não implementa nada, apenas obriga a seguir as regras impostas na interface, ou seja **TUDO QUE FOR DEFINIDO EM UMA INTERFACE DEVE SER IMPLEMENTADA PELA CLASSE**.

É interessante fazer o uso de Interfaces pelos seguintes motivos, vai te permitir fazer o tratamento de diferentes classes de maneira uniforme(*igualitária*), separa o famoso "*o que fazer?*" do "*como fazer?*" mantendo tudo no seu devido lugar e de fácil visualização e por fim e talvez o mais impactante em relação custo/tempo, facilita na mudança de implementações sem necessidade de mexer diretamente no código que a utiliza(*a interface, no caso*).

No geral é legal fazer um apanhado do que pode ou não ser implementado em uma Interface, então aqui vai.

- Atributos de instância **NÃO PODEM SER PASSADOS**
- Atributos de Classe, podem passar sem problemas desde que sejam `public static final` (*logo, são constantes*)
- Métodos devem ser passados, via polimorfismo ou em casos especiais como `default` ou `static`(*são os métodos que possuem apenas um retorno, não mutáveis.*)

Princípio `SOLID` *“Programe para o uso de interface, não para implementação. Dependa de abstrações, e não de classes concretas”.*

Entenda por fim que, ao trabalharmos utilizando Interfaces, iremos facilitar implementações futuras, pois a partir do momento em que implementamos Interfaces dentro do projeto estamos possibilitando a escalabilidade dentro do nosso código sem o medo de quebrar o que já funciona.

Pra mim é relevante destrinchar ao máximo como essa ideia de interface e polimorfismo funcionam em conjunto. Vamos a um exemplo. 

   1. Temos uma `Interface Payment`, responsável pelo controle de meios de pagamentos dentro de um Sistema, possui os métodos `pay()` e `collectPaymentDetails()`.

   2. Com isso temos alguns meios de pagamento, um deles, `PayByCreditCard() implements Payment` que possui seu obejto `CreditCard` e alguns métodos de lógica para pagar (`pay()` sobrescrito) e coleta de dados (`collectPaymentDetails()` também sobrescrito).

   3. Em `Cart()` fazemos uma instanciação da Interface `Payment` e a utilizamos para construírmos o objeto `Cart(Payment paymentMethod)`, com isso estamos afirmando que precisamos de um objeto que implemente `Payment` não importa seu tipo (`PayByPix` ou `PayByCreditCard`, não importa).

   4. Com isso criamos um `Cart()` que utiliza exatamente de quaisquer meios de pagamento já implementados ou que ainda serão.

### 👨‍👦 Herança e 🧩 Composição

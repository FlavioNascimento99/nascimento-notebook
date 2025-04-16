Aqui iremos falar um pouco sobre os pilares da orientação à objetos Abstração, Encapsulamento, Herança e Polimorfismo.
   1. **Abstração** é a conversão de algo do mundo real para código, como exemplo ``class Carro{}``
   2. **Encapsulamento** é uma maneira de manter um objeto e/ou classe protegida de alterações indevidas.
   3. **Herança** é a possibilidade de reaproveitar métodos ou atributos de uma classe(Pai) em outra (Filha).
   4. **Polimorfismo** é tu poder adicionar um comportamento à um método presente em sua classe pai.
Utilizar essas assinaturas dentro de um projeto exige um certo grau de visão de negócio, visto que, uma vez construída uma aplicação, dependendo das escolhas arquiteturais dentro do teu Software, fazer alterações posteriores as vezes pode trazer uma tremenda dor de cabeça. Então, com isso podemos adentrar profundamente dentro de cada um destes conceitos.
#### Abstração
Dentro do desenvolvimento de Software com a Orientação à Objetos, temos o conceito de abstração, que nada mais é que, transformar objetos ou estruturas reais em código. Como exemplo, podemos trazer um Carro, este possui sua fabricante, modelo, cor, placa e outros atributos, isso tudo é possível ser transformado em código. 
```
class Carro {
	String fabricante;
	String modelo;
	String placa; 
	String cor;
}
```

Não se limitando apenas à características superficiais como estas, também podemos adicionar dentro da Orientação à Objetos, a ideia de comportamentos possíveis de serem performados pelo veículo, como:
```
class Carro {
	public void iniciarPartidaDoVeiculo(){
		System.out.println("Dando partida no veículo...")
	}
}
```

]
### Encapsulamento
Também dentro da programação orientada à objet0s é possível garantir a segurança de determinados dados dentro de um objeto instanciado por uma classe, garantindo assim que os dados em questão necessitem passar por métodos específicos para serem não só acessados,  mas também alterados. Estes métodos em questão são popularmente chamados de "*métodos acessores*" ou "*getters e setters*". 

Segue um bom exemplo de métodos acessores e modificadores: 
```
public String getName() {
	return name;
}

public void setName(String newName) {
	name = newName;
}
```
- Note o detalhe quanto às assinaturas assinaturas presentes nos métodos acima, o acessor(get) precisa ser tipado, afinal, o mesmo irá retornar um determinado valor de atributo. Enquanto que o modificador, por sua vez, não precisa de retorno, mas sim, modificar um determinado atributo sem a necessidade de retornar o novo valor, logo, "sem retorno = void". 
- Outro detalhe, imagine que você possua uma classe Aluno dentro do teu código, onde o mesmo irá instanciar, consequentemente, objetos do tipo Aluno, e dentro destes, temos um atribulo chamado telefones, que se trata de uma lista de String. Para tal atributo é importante ter em mente que não será necessário fazer mais que um método acessor, para termos o retorno dos dados dentro da lista, visto que, caso seja criado e utilizado um método modificador como um setter convencional, TODOS os dados dentro da mesma será sobrescrito, o que em 99% dos casos não se trata de um comportamento desejado para esse tipo de caso. Para isso é mais interessante criar métodos específicos de busca, deleção e/ou alteração de cada um dos itens dentro desta. 

### Herança
Agora a coisa começa a ficar interessante, por que herança trás à orientação à objetos, a possibilidade de fazer o reaproveitamento no sentido literal da palavra, de código. 
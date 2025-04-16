## 🧱 SOLID e GRASP
Existem regras ou princípios relacionados à construção de software, dentre eles existem dois de suma importância, são eles SOLID e GRASP.

### 📦 SOLID
Princípios definidos com foco em manter o desenvolvimento de software mais bem estruturado e manutível. São formados por 5 ideias bem estabelecidas pela comunidade, sendo estes: 

- **S** de *Single responsibility Principle*
- **O** de *Open and Closed Principle*
- **L** de *Liskov Substitution Principle*
- **I** de *Interface Segregation Principle*
- **D** de *Dependency Inversion*

Existe um por quê dessas "regras", apesar de soarem complexas, são de suma importância para um melhor aproveitamento de tempo e redução de trabalho quanto à manutenção de software.

##### 1. Single Responsability
Uma classe deve possuir apenas uma única tarefa dentrodo teu sistema, uma `Class Knife()` deve apenas possuir o papel de cortar coisas, não abrir garrafas, por exemplo. Matando as bizarras "God Classes", estas capazes de efetuar inúmeras tarefas.

Algumas vantagens interessantes disso é a alta coesão, facilitando a compreensão do papel da classe dentro do sistema, fora a facilidade de na manutenção e reuso do código. 

Importante ter em mente que o mesmo princípio não deve ser apenas compreendido como regra para classes, mas também à métodos e funções, apenas garanta que o mesmo ***seja responsável apenas por aquilo que ele se propõe a fazer***.

##### 2. Open/Closed
Dentro do desenvolvimento de software uma das práticas que mais pode custar caro em relação à recursos é a manutenção de código, visto que isso pode trazer infinitas consequências incalculáveis. Por isso fora criada a regra em questão, onde é definido que, ***Objetos ou Entidades devem ser fechados para alterações, porém não para extensões***.

De grosso modo, o que já foi feito, testado e implementado dentro de um sistema, provavelmente não precisa passar por alterações na sua estrutura original, mas sim alimentado com novo código ou utilizado dentro de um novo contexto.

Esse tipo de regra remete muito ao uso de Interfaces dentro do sistema, facilitando a implementação de código dentro do mesmo sem necessidade de alterar aquilo que já funciona, mas sim, criando dentro dos contratos a possibilidade de chamar um novo método ou nova classe. ***Programe para Interface, não para classes concretas***.

##### 3. Liskov's Substitution
"*Se tu cria uma subclasse, ela deve poder substituir tranquilamente a superclasse sem causar nenhum tipo de quebra de código*".

Para ser substituível é ***requisito mínimo se comportar de maneira semelhante ao seu pai*** e quando afirma-se isso, não estamos falando exatamente de trazer o exato mesmo resultado. Imagine que se irei utilizar `@Override` para substituir uma classe, este deve trazer as mesmas possibilidades ou mais, mas nunca menos.

Isso exige que o sistema possua uma *herança correta* uma classe filha deve respeitar o contrato da classe pai, evitando possíveis instabilidades dentro do sistema.

**Exemplo**: Imagine uma `Class Bird()` com o método `fly()`, agora temos uma `Class Avestruz() extends Bird`, porém não faz sentido avestruz voar, logo o contrato foi quebrado. Para isso, seria necessário alterar o contrato presente dentro de `Bird.fly()` para, por exemplo, `Bird.move()`, que faria mais sentido dentro do contexto, englobando pássaros que possam ou não voar.

##### 4. 
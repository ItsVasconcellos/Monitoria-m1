# Revisão - Módulo 1

## Exemplo de PseudoCódigo

### Jogo de adivinha 

&emsp; Esse código cria um jogo em pseudocódigo. Nele, o jogador deve adivinhar qual número a máquina escolheu.

``` js
algoritmo adivinha 
INICIO 
// Definir o número aleatório que o jogador deve adivinhar
numero_secreto <- GerarNumeroAleatorioEntre(1, 100)

// Definir o contador de tentativas
tentativas <- 0

// Pedir ao jogador para inserir um palpite
Enquanto verdadeiro:
    escreva("Digite um número entre 1 e 100:")
    var palpite <- leia() 

    // Verificar se o palpite é válido
    SE palpite < 1 OU palpite > 100:
        escreva("Por favor, digite um número entre 1 e 100.")
        Continuar // Volta ao início do loop
    FIM SE
    SE palpite == numero_secreto
      escreva("Você ganhou!")
      break
    // Incrementar o contador de tentativas
    tentativas <- tentativas + 1
FIM ENQUANTO
FIM ALGORITMO 
```

### Exemplo de For/Para

```js 
// Utilizando o comando PARA para imprimir números de 1 a 10
Para i de 1 até 10 passo 1:
    Escrever(i)
```


### Exemplo de Enquanto/While

```js 
// Utilizando o comando ENQUANTO     para imprimir números de 1 a 10
contagem <- 0
Enquanto contagem < 10:
    Escrever(contagem)
    contagem <- contagem + 1
```

## Exemplo - Listas 
```js
algoritmo Listas
INICIO

FUNCAO AdivinhacaoDeNumeros():
    numero_aleatorio <- GerarNumeroAleatorio()  // Gera um número aleatório entre 1 e 100
    tentativas <- []  // Lista para armazenar as tentativas do jogador
    
    ENQUANTO Verdadeiro:
      palpite <- leia()  // Solicita ao jogador que faça um palpite
      AdicionarElemento(tentativas, palpite)  // Adiciona o palpite à lista de tentativas
      SE palpite = numero_aleatorio:
          escreva("Parabéns! Você acertou o número em", TamanhoDaLista(tentativas), "tentativas.")
          break
      SENAO palpite < numero_aleatorio:
          escreva("O número é maior que", palpite)
      FIM SENAO
      SENAO
          escreva("O número é menor que", palpite)
      FIM SENAO
    FIM ENQUANTO
            
FIM FUNCAO

FUNCAO GerarNumeroAleatorio():
    Retorna um número aleatório entre 1 e 100
FIM FUNCAO

FUNCAO SolicitarPalpite():
    escreva("Digite seu palpite (entre 1 e 100): ")
    palpite <- leia() 
    Retorna palpite
FIM FUNCAO
```

## Exemplos POO

### Exemplo Classe e objeto
```js
// Definição da classe 'Carro'
class Carro {
  // Construtor da classe
  constructor(marca, modelo, ano) {
    this.marca = marca;
    this.modelo = modelo;
    this.ano = ano;
    this.velocidade = 0; // Velocidade inicial é 0
  }

  // Método para acelerar o carro
  acelerar(aceleracao) {
    this.velocidade += aceleracao;
    console.log(`O ${this.marca} ${this.modelo} acelerou para ${this.velocidade} km/h.`);
  }

  // Método para frear o carro
  frear() {
    this.velocidade -= 10; // Reduz a velocidade em 10 km/h
    console.log(`O ${this.marca} ${this.modelo} reduziu a velocidade para ${this.velocidade} km/h.`);
  }
}

// Criando objetos da classe 'Carro'
const carro1 = new Carro('Toyota', 'Corolla', 2022);
const carro2 = new Carro('Honda', 'Civic', 2023);

// Acelerando carro1
carro1.acelerar(50);

// Freando carro2
carro2.frear();
```

## Exercícios 

### Ex 1 - O lobo pede sempre

&emsp;O nosso querido amigo lobinho está com muita fome! Crie um pseudocódigo no qual o Lobo pai  escreva uma quantidade de colheres de farinha que ele pode comer. Logo em seguida, alimente-o de acordo com a quantidade de colheres disponíveis.

### Resposta - Ex - 1
``` js
// Lê a quantidade de colheres que o lobo pai disponibilizou
colheres <- leia("Quantas colheres de farinha seu filho pode comer?")

//Verifica se o lobo Pai doou alguma colher de farinha
SE colheres > 0:
  Escrever("Hora de alimentar o Lobinho!")
  // Faz um loop nas colheres disponíveis
  ENQUANTO colheres > 0:
      Escrever("O Lobinho come uma colher de farinha.")
      // Retira a colher que o lobinho comeu da contagem
      colheres <- colheres - 1
  Escrever("O Lobinho está satisfeito!")
FIM SE
SENAO
  Escrever("O Lobinho não soube pedir auuuu")
FIM SENAO 
FIM ALGORITMO
```
### Ex 2 - De onde vim? Para onde irei?

&emsp; Vamos supor que um amigo seu deseja saber quais são os países das faculdades parceiras do inteli. Para isso, vocês combinaram de brincar de adivinha (novamente :P ). Sendo assim, faça um código (preferencialmente em JS, mas pode ser pseudo) que receba um país e verifique se ele é parceiro do inteli!  

### Resposta - Ex - 2 
```js
// Lista de países parceiros
const paisesParceiros = ["Brasil", "Argentina", "Estados Unidos", "Alemanha", "França"];

// Função para verificar se o país é parceiro
function verificarParceiro(pais) {
    if (paisesParceiros.includes(pais)) {
        console.log(pais + " é um país parceiro.");
        var index = paisesParceiros.indexOf(pais) // Função que acha o index do país na lista
         paisesParceiros.splice(index, 1); // Remove o país da lista de países parceiros
    } else {
        console.log(pais + " não é um país parceiro.");
    }
}


// Loop para permitir ao usuário inserir países n vezes
while (paisesParceiros.length > 0) {
    // Solicitar ao usuário que insira o nome de um país
    let pais = prompt("Digite o nome de um país: ");

    // Verificar se o país é parceiro
    verificarParceiro(pais);
}

console.log("Você acertou todos os países parceiros!");
```

### Ex - 3 -> Iguais, mas diferentes!

&emsp;Apesar de parecidos, os lobos e os gatinhos fofinhos, são animais diferentes com diferentes características. Sendo assim, crie um código (preferencialmente em JS, mas pode ser pseudo) , no qual exista uma classe pai - animal e as classes gatinhos fofinhos e lobos herdem de animais.

### Resposta - Ex - 3
```js
// Definição da classe pai 'Animal'
class Animal {
  constructor(nome, idade, tipo) {
    this.nome = nome;
    this.idade = idade;
    this.tipo = tipo;
  }

  // Método para emitir um som genérico
  emitirSom() {
    console.log(`${this.nome} emite um som.`);
  }

  // Método para mostrar informações do animal
  mostrarInfo() {
    console.log(`Nome: ${this.nome}, Idade: ${this.idade}, Tipo: ${this.tipo}`);
  }
}

// Definição da classe filha 'GatinhoFofo' que herda de 'Animal'
class GatinhoFofo extends Animal {
  constructor(nome, idade) {
    super(nome, idade, 'Gatinho Fofo');
  }

  // Método específico para gatinhos fofos
  ronronar() {
    console.log(`${this.nome} está ronronando.`);
  }
}

// Definição da classe filha 'Lobo' que herda de 'Animal'
class Lobo extends Animal {
  constructor(nome, idade) {
    super(nome, idade, 'Lobo');
  }

  // Método específico para lobos
  uivar() {
    console.log(`${this.nome} está uivando.`);
  }
}

// Criando instâncias das classes filhas
const gatinho = new GatinhoFofo('Bolinha', 2);
const lobo = new Lobo('Alfa', 5);

// Chamando métodos das instâncias
gatinho.mostrarInfo();
gatinho.emitirSom();
gatinho.ronronar();

lobo.mostrarInfo();
lobo.emitirSom();
lobo.uivar();
```
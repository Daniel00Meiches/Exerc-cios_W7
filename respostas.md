# Esse documento contém as minhas respostas

1.

<ins>**A) O código avalia a expressão booleana, imprime true, calcula o produto dos números na lista e imprime o resultado no console.**</ins>
<br>
<br>
A primeira parte do código é uma variável declarada que inclui uma expressão booleana que avalia a seguinte condição:

```javascript
//Parte 1
let p = 10;
let q = 3;
let r = 6;

// A expressão booleana da variável 'resultado' vai ser verdadeira se o módulo de p e q é igual a um e se r * 2 é maior do que p. Ela também poderá ser verdadeira se q mais r for menor do que p.
// Importante notar que se (q + r < p) for verdadeiro, mas (p % q === 1) e (r * 2 > p) não for verdadeiro, o booleano é considerado verdadeiro (apenas uma dessas condições devem ser verdadeiras para o booleano ser true).
// Se eu fosse incluir o valor das variáveis no lugar das letras:
// 10 % 3 === 1 --> isso está correto
// 6 * 2 > 10 ---> isso também está correto, então a primeira condição é verdadeira, o que faz com que o booleano seja true
// 3 + 6 < 10 ---> isso está também está certo, mas não importaria se tivesse errado pois a outra condição desse booleano é verdadeira também
let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado); // Saída: true
```
<br>
A segunda parte do código vai calcular os produtos de um número e vai imprimir o resultado desses produtos no console:

```javascript
const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j]; // Isso seria a mesma coisa do que dizer: produto = produto * valores[j]
}

console.log("O produto dos valores é:", produto); // Saída: O produto dos valores é: 29160
```

2.

<ins>**A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.**</ins>

O passo-a-passo das duas funções são iguais e os valores do var compras e var limite são os mesmos, a única coisa que muda de uma função para a outra é a estrutura do loop:

```javascript
// Em analisarCredito1, o loop é um do while
do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

// Em analisarCredito2, o loop é um while
while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

// Ambos os loops adicionam compras[i] à variável totalCompras
```

3.

<ins>**B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".**</ins>
<br>
O código vai seguir a ordem descrita no item B. Todos os condicionais nesse código têm um console.log caso tal condição for verdadeira.

4.

<ins>

**D) Dispositivo 1 ligado. Energia restante: 900**

**Dispositivo 2 ligado. Energia restante: 300**

**Dispositivo 3 ligado com bateria extra. Energia restante: 200**

**Dispositivo 4 não pode ser ligado. Energia insuficiente.**

**Dispositivo 5 não pode ser ligado. Energia insuficiente.**

</ins>
<br>
Seguindo a lógica da programação, as primeiras duas vezes que o código passa pelo loop, vai ser subtraído 300 e 600 de 1200, fazendo com que haja 300 de energia disponível. 1200 - 300 = 900 - 600 = 300. Os dois primeiros dispositivos terão 900 e 300 de energia disponível, respectivamente. Isso quer dizer que a próxima vez que o código passar pelo loop (quando i = 2), 300 < 500, o que quer dizer que o primeiro if é falso, então o código verifica se o else if é verdadeiro. Será, o que quer dizer que o terceiro dispositivo pode ser ligado com bateria extra. Depois, isso leva ao cálculo 400 - (500 - 0) = -100. Com isso, não haverá mais bateria extra disponível, então os outros dispositivos não terão energia o suficiente para serem ligados.

```javascript
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo; // Quando i = 0, energiaDisponivel = 900. Quando i = 1, energiaDisponivel = 300.
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo)); // Quando i = 2, no console.log a energiaDisponivel = 200
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel); // Quando i = 2, energiaDisponivel = 0 e bateriaExtra = -100.
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente."); // Quando i = 3, não haverá mais energia disponível ou bateria extra, então os dispositivos 4 e 5 não poderão ser ligados
    }
}
```
5.

<ins>**B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.**</ins>
<br>
Vou tentar justificar com um exemplo pessoal. Os jogos que eu já desenvolvi com o Phaser, eu sempre implementava os controles do jogador no método update(), pois nele, toda vez que o jogador pressionar uma tecla, o método update terá que atualizar no exato momento em que a tecla é pressionada para os controles serem responsivos. Isso também se aplica a atualizações constantes sendo feitas ao placar dos meus jogos toda vez que meu personagem controlável colecionar um coletável.

6.

<ins>**A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.**</ins>
<br>
A documentação oficial do Phaser comprova isso. Aqui está um trecho traduzido:
```
"O Matter Physics World fornece uma simulação mais avançada e realista de interações físicas em comparação ao Arcade Physics. Construído na biblioteca Matter.js, ele permite comportamento físico mais complexo, como dinâmica de corpo rígido, restrições e detecção avançada de colisão."
```

7.

```javascript
var compras = [40.50, 20.50, 10.25, 30.85, 65.90];
var totalCompras = 0;

// Loop que vai fazer a soma dos preços dos produtos que serão comprados
for (i = 0; i < compras.length; i++) {
    totalCompras += compras[i]; // Ao final do loop, totalCompras = 168
}

console.log(`O preço total de suas compras é R$ ${totalCompras.toFixed(2)}`); // Saída: O preço total de suas compras é R$ 168.00

// Instrução if que vai avaliar se haverá frete baseado no preço total das compras
if (totalCompras < 50) {
    console.log("Frete não disponível!");
} else if (totalCompras >= 50 && totalCompras <= 199.99) {
    console.log("Frete com custo adicional!");
} else {
    console.log("Frete grátis!");
}
```

8.

```javascript
class Veiculo {
    constructor(modelo, ano, quilometragem, litrosAbastecidos) {
        this.modelo = modelo;
        this.ano = ano;
        this.quilometragem = quilometragem;
        this.litrosAbastecidos = litrosAbastecidos;
    }

    calcularConsumo() {
        return this.quilometragem / this.litrosAbastecidos; // Cálculo do consumo do veículo
    }
}

class Carro extends Veiculo {
    constructor(modelo, ano, numPassageiros, combustivel, quilometragem, litrosAbastecidos) {
        super(modelo, ano, quilometragem, litrosAbastecidos);
        this.numPassageiros = numPassageiros;
        this.combustivel = combustivel;
    }

    calcularConsumo() {
        return this.quilometragem / this.litrosAbastecidos;
    }

}

class Moto extends Veiculo {
    constructor(modelo, ano, guidão, exaustão, quilometragem, litrosAbastecidos) {
        super(modelo, ano, quilometragem, litrosAbastecidos);
        this.guidao = guidão;
        this.exaustao = exaustão;
    }

    calcularConsumo() {
        return this.quilometragem / this.litrosAbastecidos;
    }
}
```

9.

```
// Variáveis
velocidadeInicial    = valor
velocidade_pouso     = valor
tempo_max            = valor
desacelaracao        = valor
limite_desaceleracao = valor

tempo = 0
velocidade = velocidade_inicial

// Loop que atualiza a velocidade enquanto o valor da velocidade não 
enquanto velocidade > velocidade_pouso && tempo <= tempo_maximo {
    velocidade = velocidade_inicial - desaceleracao * tempo
    tempo += 1;

    // verificar se a desaceleração não ultrapassa seu limite estabelecido
    se desaceleracao < limite_desaceleracao {
        print 'Ajuste a taixa de desaceleração pois ela está baixa'
    }
}

// Printar caso a sonda conseguiu chegar na velocidade segura dentro do tempo
se velocidade <= velocidade_segura {
    print  `Foi um pouso bem sucedido. Foi feito em ${tempo} segundos`
}

// Printar caso o tempo excedeu o limite e a velocidade segura não foi atingida
se tempo > tempo_max {
    print "O tempo máximo foi ultrapassado e a sonda não pousou com segurança"
}
```

10.

```javascript
// As matrizes que serão utilizadas para testar o código
var investimentosAno1 =
[[1000, 2000],  // Linha 1
 [1500, 2500]]; // Linha 2
var investimentosAno2 =
[[1200, 1800],  // Linha 1
 [1300, 2700]]; // Linha 2


// A função que fará a multiplicação
function multiplicarMatrizesInvestimento(matrizA, matrizB) {

    if (matrizA.length !== matrizB.length) {
        return "As matrizes não podem ser somadas. Elas têm dimensões diferentes.";
    } else {
        // Colunas e linhas de ambas as matrizes. Vão ser usadas em um loop que fará a multiplicação
        var colunasA = matrizA.length; 
        var linhasA  = matrizA[0].length;
        var colunasB = matrizB.length; 

        // Variável que vai armazenar os resultados da multiplicação de matrizes
        var matrizResultado = [];

        // Multiplicação será feito baseado no produto escalar das linhas da matrizA com as colunas da matrizB
        for (i = 0; i < linhasA; i++) {              // Vai atravessar pelas linhas da matrizA
            matrizResultado[i] = [];

            for (var j = 0; j < colunasB; j++) {     // Vai atravessar pelas colunas da matrizB
                matrizResultado[i][j] = 0;  // Inicia com 0
                
                for (var k = 0; k < colunasA; k++) { // Vai atravessar pelas colunas da matrizA
                matrizResultado[i][j] += matrizA[i][k] * matrizB[k][j]; // Em matrizA[i][k], o i representa a posição/index da linha e o k representa a posição/index da coluna. Então, matrizA[0][0] = 1000 e matrizA[0][1] = 2000. Essa mesma ideia se aplica para a matrizB[k][j]
                }
           }
        }
        return matrizResultado; // Retorna o valor à função após a realização dos cálculos
    }
}

// Teste do código
var totalInvestimentos = multiplicarMatrizesInvestimento(investimentosAno1, investimentosAno2);
console.log(totalInvestimentos);
```

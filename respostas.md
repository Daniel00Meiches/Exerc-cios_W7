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
// 3 + 6 < 10 ---> isso está errado, mas não importa pois a outra condição desse booleano é verdadeira
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


4.

<ins>

**D) Dispositivo 1 ligado. Energia restante: 900**

**Dispositivo 2 ligado. Energia restante: 300**

**Dispositivo 3 ligado com bateria extra. Energia restante: 200**

**Dispositivo 4 não pode ser ligado. Energia insuficiente.**

**Dispositivo 5 não pode ser ligado. Energia insuficiente.**

</ins>

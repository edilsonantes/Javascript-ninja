# Desafio da semana #4

```js
/*
Declare uma variável chamada `isTruthy`, e atribua a ela uma função que recebe
um único parâmetro como argumento. Essa função deve retornar `true` se o
equivalente booleano para o valor passado no argumento for `true`, ou `false`
para o contrário.
*/
var isTruthy = function(a) {
    if (a)
        return true;
    else
        return false;
}

// Invoque a função criada acima, passando todos os tipos de valores `falsy`.
isTruthy(0);
//false
isTruthy(-0);
//false
isTruthy(NaN);
//false
isTruthy('');
//false
isTruthy("");
//false
isTruthy(false);
//false
isTruthy(undefined);
//false
isTruthy(null);
//false

/*
Invoque a função criada acima passando como parâmetro 10 valores `truthy`.
*/
isTruthy(1);
//true
isTruthy(true);
//true
isTruthy("a");
//true
isTruthy('b');
//true
isTruthy('2');
//true
isTruthy('3');
//true
isTruthy('4');
//true
isTruthy('5');
//true
isTruthy('6');
//true
isTruthy('7');
//true

/*
Declare uma variável chamada `carro`, atribuindo à ela um objeto com as
seguintes propriedades (os valores devem ser do tipo mostrado abaixo):
- `marca` - String
- `modelo` - String
- `placa` - String
- `ano` - Number
- `cor` - String
- `quantasPortas` - Number
- `assentos` - Number - cinco por padrão
- `quantidadePessoas` - Number - zero por padrão
*/
var carro = {
    marca: 'Honda',
    modelo: 'Civic',
    placa: 'BAR-8E30',
    ano: 2008,
    cor: 'Cinza',
    quantasPortas: 4,
    assentos: 5,
    quantidadePessoas: 0
}

/*
Crie um método chamado `mudarCor` que mude a cor do carro conforme a cor
passado por parâmetro.
*/
carro.mudaCor = function(newColor) {
    carro.cor = newColor;
}

/*
Crie um método chamado `obterCor`, que retorne a cor do carro.
*/
carro.obterCor = function() {
    return carro.cor;
}

/*
Crie um método chamado `obterModelo` que retorne o modelo do carro.
*/
carro.obterModelo = function() {
    return carro.modelo;
}

/*
Crie um método chamado `obterMarca` que retorne a marca do carro.
*/
carro.obterMarca = function() {
    return carro.marca;
}

/*
Crie um método chamado `obterMarcaModelo`, que retorne:
"Esse carro é um [MARCA] [MODELO]"
Para retornar os valores de marca e modelo, utilize os métodos criados.
*/
carro.obterMarcaModelo = function() {
    return 'Esse carro é um ' + carro.obterMarca() + ' ' + carro.obterModelo();
}

/*
Crie um método que irá adicionar pessoas no carro. Esse método terá as
seguintes características:
- Ele deverá receber por parâmetro o número de pessoas entrarão no carro. Esse
número não precisa encher o carro, você poderá acrescentar as pessoas aos
poucos.
- O método deve retornar a frase: "Já temos [X] pessoas no carro!"
- Se o carro já estiver cheio, com todos os assentos já preenchidos, o método
deve retornar a frase: "O carro já está lotado!"
- Se ainda houverem lugares no carro, mas a quantidade de pessoas passadas por
parâmetro for ultrapassar o limite de assentos do carro, então você deve
mostrar quantos assentos ainda podem ser ocupados, com a frase:
"Só cabem mais [QUANTIDADE_DE_PESSOAS_QUE_CABEM] pessoas!"
- Se couber somente mais uma pessoa, mostrar a palavra "pessoa" no retorno
citado acima, no lugar de "pessoas".
*/
carro.addPessoas = function(n) {
    var auxAssentos = carro.assentos - carro.quantidadePessoas;
    if((carro.quantidadePessoas < carro.assentos) && (n <= auxAssentos)){
        carro.quantidadePessoas += n;
        return 'Já temos ' + carro.quantidadePessoas + ' pessoas no carro!';
    } else if (carro.quantidadePessoas == carro.assentos){
        return 'O carro já está lotado';
    } else if(n > auxAssentos){
        var auxPessoas = ' pessoas!'
        auxAssentos === 1 ? auxPessoas = ' pessoa!' : auxPessoas = ' pessoas!'
        return 'Só cabem mais ' + auxAssentos + auxPessoas;
    }
}

/*
Agora vamos verificar algumas informações do carro. Para as respostas abaixo,
utilize sempre o formato de invocação do método (ou chamada da propriedade),
adicionando comentários _inline_ ao lado com o valor retornado, se o método
retornar algum valor.

Qual a cor atual do carro?
*/
carro.obterCor();
//'Cinza'

// Mude a cor do carro para vermelho.
carro.mudaCor('Vermelho');

// E agora, qual a cor do carro?
carro.obterCor();
//'Vermelho'

// Mude a cor do carro para verde musgo.
carro.mudaCor('Verde Musgo');

// E agora, qual a cor do carro?
carro.obterCor();
//'Verde Musgo'

// Qual a marca e modelo do carro?
carro.obterMarcaModelo();
//'Esse carro é um Honda Civic'

// Adicione 2 pessoas no carro.
carro.addPessoas(2);
//'Já temos 2 pessoas no carro!'

// Adicione mais 4 pessoas no carro.
carro.addPessoas(4);
//'Só cabem mais 3 pessoas!'

// Faça o carro encher.
carro.addPessoas(3);
//'Já temos 5 pessoas no carro!'

// Tire 4 pessoas do carro.
carro.quantidadePessoas -= 4;
//1

// Adicione 10 pessoas no carro.
carro.addPessoas(10);
//'Só cabem mais 4 pessoas!'

// Quantas pessoas temos no carro?
carro.quantidadePessoas;
//1
```

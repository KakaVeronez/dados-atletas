# dados-atletas
class Atleta {
    constructor(nome, idade, peso, altura, notas) {
        this.nome = nome;
        this.idade = idade;
        this.peso = peso;
        this.altura = altura;
        this.notas = notas;
    }

    calculaCategoria() {
        if (this.idade >= 9 && this.idade <= 11) {
            return 'Infantil';
        } else if (this.idade >= 12 && this.idade <= 13) {
            return 'Juvenil';
        } else if (this.idade >= 14 && this.idade <= 15) {
            return 'Intermediário';
        } else if (this.idade >= 16 && this.idade <= 30) {
            return 'Adulto';
        } else {
            return 'Sem categoria';
        }
    }

    calculaIMC() {
        return this.peso / Math.pow(this.altura, 2);
    }

    calculaMediaValida() {
        // Ordenar as notas para remover a maior e a menor
        const notasOrdenadas = [...this.notas].sort((a, b) => a - b);
        const notasValidas = notasOrdenadas.slice(1, notasOrdenadas.length - 1);

        // Calcular a média das notas válidas
        const soma = notasValidas.reduce((total, nota) => total + nota, 0);
        return soma / notasValidas.length;
    }

    // Métodos para obter os atributos
    obtemNomeAtleta() {
        return this.nome;
    }
    // ... outros métodos para obter os demais atributos (idade, peso, altura, notas, categoria, IMC, média)
}

// Exemplo de uso:
const atleta = new Atleta("Cesar Abascal", 30, 80, 1.70, [10, 9.34, 8.42, 10, 7.88]);

console.log("Nome:", atleta.obtemNomeAtleta());
console.log("Idade:", atleta.idade);
console.log("Peso:", atleta.peso);
console.log("Altura:", atleta.altura);
console.log("Notas:", atleta.notas);
console.log("Categoria:", atleta.calculaCategoria());
console.log("IMC:", atleta.calculaIMC());
console.log("Média válida:", atleta.calculaMediaValida());

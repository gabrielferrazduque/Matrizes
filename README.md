# Matrizes
Matrizes
include <stdio.h>

#define LIN 3
#define COL 3

// Função para calcular a quantidade de números ímpares na matriz
int contarImpares(int matriz[LIN][COL]) {
    int impares = 0;
    for (int i = 0; i < LIN; i++) {
        for (int j = 0; j < COL; j++) {
            if (matriz[i][j] % 2 != 0) {
                impares++;
            }
        }
    }
    return impares;
}

// Função para buscar um elemento na matriz e retornar sua posição
void buscarElemento(int matriz[LIN][COL], int valor) {
    int encontrado = 0;
    for (int i = 0; i < LIN; i++) {
        for (int j = 0; j < COL; j++) {
            if (matriz[i][j] == valor) {
                printf("Elemento %d encontrado na posição [%d][%d].\n", valor, i, j);
                encontrado = 1;
            }
        }
    }
    if (!encontrado) {
        printf("Elemento %d não encontrado.\n", valor);
    }
}

// Função para calcular o somatório de todos os elementos da matriz
int somatorioMatriz(int matriz[LIN][COL]) {
    int soma = 0;
    for (int i = 0; i < LIN; i++) {
        for (int j = 0; j < COL; j++) {
            soma += matriz[i][j];
        }
    }
    return soma;
}

// Função para calcular a média de todos os elementos da matriz
float mediaMatriz(int matriz[LIN][COL]) {
    int soma = somatorioMatriz(matriz);
    return (float)soma / (LIN * COL);
}

// Função para imprimir a média dos elementos de cada linha
void mediaPorLinha(int matriz[LIN][COL]) {
    for (int i = 0; i < LIN; i++) {
        int soma = 0;
        for (int j = 0; j < COL; j++) {
            soma += matriz[i][j];
        }
        printf("Média dos elementos da linha %d: %.2f\n", i, (float)soma / COL);
    }
}

int main() {
    int matriz[LIN][COL];
    int valor;

    // Preenchendo a matriz
    printf("Digite os elementos da matriz 3x3:\n");
    for (int i = 0; i < LIN; i++) {
        for (int j = 0; j < COL; j++) {
            printf("Elemento [%d][%d]: ", i, j);
            scanf("%d", &matriz[i][j]);
        }
    }

    // Calcula e imprime a quantidade de números ímpares
    int impares = contarImpares(matriz);
    printf("Quantidade de números ímpares na matriz: %d\n", impares);

    // Busca um elemento na matriz
    printf("Digite um elemento para buscar na matriz: ");
    scanf("%d", &valor);
    buscarElemento(matriz, valor);

    // Calcula e imprime o somatório dos elementos
    int soma = somatorioMatriz(matriz);
    printf("Somatório de todos os elementos da matriz: %d\n", soma);

    // Calcula e imprime a média de todos os elementos da matriz
    float media = mediaMatriz(matriz);
    printf("Média de todos os elementos da matriz: %.2f\n", media);

    // Imprime a média de cada linha
    mediaPorLinha(matriz);

    return 0;
}

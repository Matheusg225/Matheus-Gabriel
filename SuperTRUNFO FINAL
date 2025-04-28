#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <stdbool.h>

// Definição da estrutura da carta de país
typedef struct {
    char nome[50];
    int populacao;
    float area;
    float densidade;
    int pib;
} Carta;

// Função para exibir uma carta
void exibirCarta(Carta carta) {
    printf("Nome: %s\n", carta.nome);
    printf("População: %d\n", carta.populacao);
    printf("Área: %.2f km²\n", carta.area);
    printf("Densidade Demográfica: %.2f hab/km²\n", carta.densidade);
    printf("PIB: %d bilhões USD\n", carta.pib);
}

// Função para comparar dois atributos de duas cartas
int compararAtributos(Carta carta1, Carta carta2, int atributo1, int atributo2) {
    float valor1_attr1, valor2_attr1, valor1_attr2, valor2_attr2;

    switch (atributo1) {
        case 1: valor1_attr1 = carta1.populacao; valor2_attr1 = carta2.populacao; break;
        case 2: valor1_attr1 = carta1.area; valor2_attr1 = carta2.area; break;
        case 3: valor1_attr1 = carta1.densidade; valor2_attr1 = carta2.densidade; break;
        case 4: valor1_attr1 = carta1.pib; valor2_attr1 = carta2.pib; break;
        default: return 0; // Atributo inválido
    }

    switch (atributo2) {
        case 1: valor1_attr2 = carta1.populacao; valor2_attr2 = carta2.populacao; break;
        case 2: valor1_attr2 = carta1.area; valor2_attr2 = carta2.area; break;
        case 3: valor1_attr2 = carta1.densidade; valor2_attr2 = carta2.densidade; break;
        case 4: valor1_attr2 = carta1.pib; valor2_attr2 = carta2.pib; break;
        default: return 0; // Atributo inválido
    }

    int pontos1 = 0;
    int pontos2 = 0;

    // Comparação do primeiro atributo
    if (atributo1 == 3) { // Densidade Demográfica: menor valor vence
        if (valor1_attr1 < valor2_attr1) pontos1++;
        else if (valor2_attr1 < valor1_attr1) pontos2++;
    } else { // Outros atributos: maior valor vence
        if (valor1_attr1 > valor2_attr1) pontos1++;
        else if (valor2_attr1 > valor1_attr1) pontos2++;
    }

    // Comparação do segundo atributo
    if (atributo2 == 3) { // Densidade Demográfica: menor valor vence
        if (valor1_attr2 < valor2_attr2) pontos1++;
        else if (valor2_attr2 < valor1_attr2) pontos2++;
    } else { // Outros atributos: maior valor vence
        if (valor1_attr2 > valor2_attr2) pontos1++;
        else if (valor2_attr2 > valor1_attr2) pontos2++;
    }

    if (pontos1 > pontos2) return 1; // Carta 1 vence
    else if (pontos2 > pontos1) return 2; // Carta 2 vence
    else return 0; // Empate
}

int main() {
    // Cartas pré-cadastradas (você pode adicionar mais)
    Carta cartas[3] = {
        {"Brasil", 213000000, 8515767.00, 25.01, 1400},
        {"Argentina", 45000000, 2780400.00, 16.18, 450},
        {"Japão", 126000000, 377975.00, 333.33, 5100}
    };

    Carta carta1 = cartas[0];
    Carta carta2 = cartas[1];

    int escolha1, escolha2;
    bool atributo2_valido = false;

    printf("--- Super Trunfo --- Nível Mestre ---\n\n");

    printf("Carta 1:\n");
    exibirCarta(carta1);
    printf("\nCarta 2:\n");
    exibirCarta(carta2);
    printf("\n");

    // Menu para escolher o primeiro atributo
    printf("Escolha o primeiro atributo para comparar:\n");
    printf("1 - População\n");
    printf("2 - Área\n");
    printf("3 - Densidade Demográfica\n");
    printf("4 - PIB\n");

    do {
        printf("Digite o número do atributo: ");
        if (scanf("%d", &escolha1) != 1) {
            printf("Entrada inválida. Por favor, digite um número.\n");
            while (getchar() != '\n'); // Limpar o buffer de entrada
            escolha1 = 0; // Forçar repetição
        }
    } while (escolha1 < 1 || escolha1 > 4);

    // Menu para escolher o segundo atributo (dinâmico)
    printf("\nEscolha o segundo atributo para comparar:\n");
    if (escolha1 != 1) printf("1 - População\n");
    if (escolha1 != 2) printf("2 - Área\n");
    if (escolha1 != 3) printf("3 - Densidade Demográfica\n");
    if (escolha1 != 4) printf("4 - PIB\n");

    do {
        printf("Digite o número do atributo: ");
        if (scanf("%d", &escolha2) != 1) {
            printf("Entrada inválida. Por favor, digite um número.\n");
            while (getchar() != '\n'); // Limpar o buffer de entrada
            escolha2 = 0; // Forçar repetição
            continue;
        }
        if (escolha2 < 1 || escolha2 > 4) {
            printf("Opção inválida. Por favor, digite um número entre 1 e 4.\n");
            continue;
        }
        if (escolha2 == escolha1) {
            printf("Você já escolheu este atributo. Por favor, escolha outro.\n");
            continue;
        }
        atributo2_valido = true;
    } while (!atributo2_valido);

    printf("\n--- Resultado da Comparação ---\n");
    printf("Atributos escolhidos: ");
    switch (escolha1) {
        case 1: printf("População"); break;
        case 2: printf("Área"); break;
        case 3: printf("Densidade Demográfica"); break;
        case 4: printf("PIB"); break;
    }
    printf(" e ");
    switch (escolha2) {
        case 1: printf("População"); break;
        case 2: printf("Área"); break;
        case 3: printf("Densidade Demográfica"); break;
        case 4: printf("PIB"); break;
    }
    printf("\n\n");

    float valor1_attr1, valor2_attr1, valor1_attr2, valor2_attr2;

    // Obter valores dos atributos para exibição
    switch (escolha1) {
        case 1: valor1_attr1 = carta1.populacao; valor2_attr1 = carta2.populacao; break;
        case 2: valor1_attr1 = carta1.area; valor2_attr1 = carta2.area; break;
        case 3: valor1_attr1 = carta1.densidade; valor2_attr1 = carta2.dens

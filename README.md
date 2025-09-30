# Trabalho-Algoritmos-1
Fabricio
#include <stdio.h>   // Biblioteca para entrada e saída (printf, scanf)
#include <stdlib.h>  // Biblioteca padrão, usada para funções como exit() (não usada diretamente aqui)
#include <math.h>    // Biblioteca para funções matemáticas, como sqrt()

// TRABALHA DIA 25/09 = NOME: Fabricio

// Função para resolver equação de primeiro grau: ax + b = 0
void equacaoDePrimeiroGrau(){
    float a, b;  // Declaração dos coeficientes da equação

    printf("\n= Forma: ax + b = 0 ");  // Exibe a forma da equação
    printf("\n= Informe o Valor de A : ");  
    scanf("%f", &a);  // Lê o valor de 'a' fornecido pelo usuário

    printf("\n= Informe o Valor de B : ");  
    scanf("%f", &b);  // Lê o valor de 'b' fornecido pelo usuário

    printf("\n= Equacao : %.2fx + %.2f = 0", a, b); // Mostra a equação montada

    printf("\n%.2fx = %.2f", a, -b );  // Mostra o passo intermediário: ax = -b
    printf("\nx = %.2f / %.2f", -b, a); // Mostra a divisão que será feita
    printf("\nx = %.2f", -b/a); // Mostra o resultado final da equação
}

// Função para resolver equação de segundo grau: ax² + bx + c = 0
void equacaoDeSegundoGrau(){
    float a, b, c, x1, x2;  // Declara os coeficientes e as raízes

    printf(" Informe o valor de A: ");  
    scanf("%f" , &a);  // Lê o coeficiente 'a'

    printf(" Informe o valor de B: ");  
    scanf("%f", &b);  // Lê o coeficiente 'b'

    printf(" Informe o valor de C: ");  
    scanf("%f", &c);  // Lê o coeficiente 'c'

    // Calculando o delta (b² - 4ac) passo a passo
    printf("\nCalc DELTA = (%.2f)^2 - 4 * %.2f * %.2f", b, a, c);
    float mult = 4 * a * c; // Calcula 4*a*c
    float elev = b * b;      // Calcula b²
    printf("\nB^2 = (%.2f)^2 = %.2f", b , elev);
    printf("\n4*a*c = 4 * %.2f * %.2f = %.2f",a, c , mult);
    float delta = elev - mult; // Calcula delta
    printf("\nDELTA = %.2f - %.2f = %.2f", elev, mult, delta);

    // Verifica o número de raízes reais
    if (delta < 0){
        printf("\nNao existem raizes reais."); // Delta negativo: sem raízes reais
    } else if (delta == 0){
        float x = -b / (2 * a); // Delta zero: raiz única
        printf("\nRaiz unica: x = %.2f", x);
    } else {
        float x1 = (-b + sqrt(delta)) / (2 * a); // Raiz 1
        float x2 = (-b - sqrt(delta)) / (2 * a); // Raiz 2
        printf("\nRaizes: x1 = %.2f , x2 = %.2f", x1, x2); // Mostra as duas raízes
    }
}

// Função principal (main) do programa
int main(){
    int menu; // Variável para armazenar a escolha do usuário no menu

    // Exibe o menu principal
    printf("\n=         === MENU PRINCIPAL ===       =\n");
    printf("= 1 - Resolver Equacao de Pri Grau     =\n"); 
    printf("= 2 - Resolver Equacao de Seg Grau     =\n");
    printf("= 3 - Sobre o Programa                 =\n");
    printf("= 0 - SAIR                             =\n");
    printf("========================================\n");

    printf("\nEscolha uma Opcao (1,2,3,0): ");
    scanf("%d", &menu); // Lê a escolha do usuário

    // Switch-case para escolher a ação baseada no menu
    switch (menu)
    {
        case 1:
            equacaoDePrimeiroGrau(); // Chama função do 1º grau
            break;

        case 2:
            equacaoDeSegundoGrau(); // Chama função do 2º grau
            break;

        case 3:
            // Exibe informações sobre o programa
            printf("\nFazer um programa em que resolva equações de Primeiro e Segundo Grau. usei void para as equacoes e switch para as escolhas.");
            break;

        case 0:
            printf("\nSaindo do Programa...."); // Mensagem de saída
            break;

        default:
            break; // Caso o usuário digite algo inválido, não faz nada
    }
}

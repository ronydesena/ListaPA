#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void crescente(float *e, int n){
    float aux;

    for(int i = 0; i < n; i++){
        for(int j = 0; j < n; j++){
            if(e[i] < e[j]){
                aux = e[i];
                e[i]=e[j];
                e[j]=aux;
            }
        }
    }
}

int main(int argc, char *argv[])
{
    float tempo;
    time_t t_ini, t_fin;

    t_ini = time(NULL);

    int n;
    float *e;

    printf("Digite a quantidade de elementos: ");
    scanf("%d", &n);

    e = (float*)malloc(n*sizeof(float));

    for(int i = 0; i < n; i++){
        printf("Digite o elemento: ");
        scanf("%f", &e[i]);
    }

    printf("Sequencia ordenada: ");
    crescente(e, n);
    for(int i=0; i<n; i++){
        printf("%f " "", e[i]);
    }

    free(e);

    t_fin = time(NULL);

    tempo = difftime(t_fin, t_ini);
    printf("\nTempo: %f\n", tempo);
    return 0;
}
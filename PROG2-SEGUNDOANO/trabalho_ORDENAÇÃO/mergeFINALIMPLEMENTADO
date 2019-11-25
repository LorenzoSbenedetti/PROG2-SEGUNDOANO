#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
void intercalaC(int *v, int n) {
    int meio = n / 2;
    int i = 0, j = meio, k = 0;
    int aux[n];

    while( i < meio && j < n ){
        if( *(v+i) <= *(v+j) )
            *(aux+k) = *(v+i++);
        else
            *(aux+k) = *(v+j++);
        k++;
    }

    if( i == meio )
        while( j < n )
            *(aux+k++) = *(v+j++);
    else
        while( i < meio )
            *(aux+k++) = *(v+i++);

    for( i = 0; i < n; i++ )
        *(v+i) = *(aux+i);
}
void intercalaD(int *v, int n) {
    int meio = n / 2;
    int i = 0, j = meio, k = 0;
    int aux[n];
    while( i < meio && j < n ){
        if( *(v+i) >= *(v+j) )
            *(aux+k) = *(v+i++);
        else
            *(aux+k) = *(v+j++);
        k++;
    }

    if( i == meio )
        while( j < n )
            *(aux+k++) = *(v+j++);
    else
        while( i < meio )
            *(aux+k++) = *(v+i++);

    for( i = 0; i < n; i++ )
        *(v+i) = *(aux+i);
}
void mergeD(int *v, int n){
	int meio = n / 2;
	if( n > 1 ){
		mergeD(v, meio);
		mergeD(v + meio, n - meio);
		intercalaD(v, n);
	}
}
void mergeC(int *v, int n){
	int meio = n / 2;
	if( n > 1 ){
		mergeC(v, meio);
		mergeC(v + meio, n - meio);
		intercalaC(v, n);
	}
}
void bubble_Ponteiros (int v[], int n){
    int k, j, aux;
    for (k = 0; k < n; k++)
    {
        for (j = 0; j < n - 1; j++)
        {
            if (*(v+j) > *(v + j + 1))
            {
                aux = *(v+j);
                *(v+j)= *(v+j+1);
                *(v+j+1) = aux;
            }
        }
    }
}
void bubble_invertido (int v[], int n){
    int k, j, aux;
    for (k = 1; k < n; k++)
    {
        for (j = 0; j < n - 1; j++)
        {
            if (v[j] < v[j + 1])
            {
                aux          = v[j];
                v[j]     = v[j + 1];
                v[j + 1] = aux;
            }
        }
    }
}
void insertionSort_ponteiros(int v[], int n){
    int i, chave, j;
    for (i = 1; i < n; i++)
    {
        chave = v[i];
        j = i-1;
        while (j >= 0 && v[j] > chave)
        {
            *(v+j+1) = *(v+j);
            j = j-1;
        }
        *(v+j+1) = chave;
    }
}
void insertionSort_invertido(int v[], int n){
    int i, chave, j;
    for (i = 1; i < n; i++)
    {
        chave = v[i];
        j = i-1;
        while (j >= 0 && v[j] < chave)
        {
            v[j+1] = v[j];
            j = j-1;
        }
        v[j+1] = chave;
    }
}
void selection_sort_ponteiros (int v[],int max){
    int i, j, min, aux;
    for (i = 0; i < (max - 1); i++)
    {
        min = i;
        for (j = i+1; j < max; j++)
        {
            if (*(v+j) < *(v+min) )
            {
                min = j;
            }
        }
        if (i != min)
        {
            aux = *(v+i);
            *(v+i) = *(v+min);
            *(v+min) = aux;
        }
    }
}
void selection_sort_invertido (int v[],int max){
    int i, j, min, aux;
    for (i = 0; i < (max-1); i++)
    {
        min = i;
        for (j = i+1; j < max; j++)
        {
            if (v[j] > v[min])
            {
                min = j;
            }
        }
        if (i != min)
        {
            aux = v[min];
            v[min] = v[i];
            v[i] = aux;
        }
    }
}
int buscador (int v[],int N,int procurador){
    int i;
    for (i=0; i<N; i++)
    {
        if (procurador == v[i])
        {
            return i;
        }
    }
}
int busca_bin(int v[],int N,int procurador){
    int inicio=0;
    int  fim=N-1;
    int meio;
    while(inicio<=fim)
    {
        meio=(inicio+fim)/2;
        if(procurador == v[meio])
        {
            return 1;
        }
        if(procurador < v[meio])
        {
            fim = meio-1;
        }
        else
        {
            inicio = meio+1;
        }
    }
    return 0;
}
void printador(int v[],int N){
    int i;
    for(i=0; i<N; i++)
    {
        printf("%d\n",v[i]);
    }
}
int main(){
    system("color 2");
    int N;
    printf("\nEscolha o tamanho do vetor :");
    scanf("%d",&N);
    int v[N],i,op,procurador;
    for (i=0; i<N; i++)
    {
        printf("\n%d\tO numero esta na posicao :",i);
        scanf("%d",&v[i]);
    }
    printf("\n\nEscolha seu metodo de ordenação do vetor");
    printf("\n\n1-Bubble Ponteiros");
    printf("\n\n2-Bubble Invertido");
    printf("\n\n3-InserctionSort ponteiros");
    printf("\n\n4-InserctionSort decrescente");
    printf("\n\n5-SelectionSort ponteiros");
    printf("\n\n6-SelectionSort decrescente");
    printf("\n\n7-Buscador");
    printf("\n\n8-Busca binária");
    printf("\n\n9-Merge");
    printf("\n\n0-Termina o Sistema");
    while (op!=0)
    {
        scanf("%d",&op);
        printf("\n\n");
        switch(op)
        {
            scanf("%d",&op);
        case 1:
            bubble_Ponteiros(v,N);
            printador(v,N);
            break;
        case 2:
            bubble_invertido(v,N);
            printador(v,N);
            break;
        case 3:
            insertionSort_ponteiros(v,N);
            printador(v,N);
            break;
        case 4:
            insertionSort_invertido(v,N);
            printador(v,N);
            break;
        case 5:
            selection_sort_ponteiros(v,N);
            printador(v,N);
            break;
        case 6:
            selection_sort_invertido(v,N);
            printador(v,N);
            break;
        case 7:
            printf("\n\nQual numero vc deseja encontrar?");
            scanf("%d",&procurador);
            printf("%d\n\n",buscador(v,N,procurador));
            break;
        case 8:
            printf("\nEscolha o numero que deseja encontrar\n");
            scanf("%d",&procurador);
            if(busca_bin(v,N,procurador)==1)
            {
                printf("\nAchou");
            }
            else
            {
                printf("\nNao achou");
            }
            break;
        case 9:
            intercalaC(v,N);
            intercalaD(v,N);
            mergeD(v,N);
            mergeC(v,N);
            printador(v,N);
            break;
        default:
            printf("\nNenhum comando escolhido");
        }
    }
}

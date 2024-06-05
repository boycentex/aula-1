# aula-1
pratica de alocação dinâmica

#include<stdio.h>
#include<conio.h>
#include<locale.h>
#include<stdlib.h>

void lervetor(float *vetor, int tamanho){ 
	printf("preencha o vetor\n");
	int i;
	for(i=0; i<tamanho;i++){ 
		scanf("%f", &vetor[i]);
	}
}

void imprimir(float *vetor, int tamanho){ 
	int i;
	for(i=0; i<tamanho;i++){ 
		printf("%.2f\n", vetor[i]);
	}	
}

float * criar(int tamanho){ 	
	float *vetor = (float*) malloc(tamanho * sizeof(float));
	if(vetor==NULL){ 
		printf("erro na alocação\n");
		exit (1);
	}
	return vetor;
}

int main(void){
	setlocale(LC_ALL, "Portuguese");
	
	float *vetor=criar(5);
	
	lervetor(vetor, 5);
	printf("\n");
	imprimir(vetor, 5);
	
	free(vetor);	
	return (0);
}

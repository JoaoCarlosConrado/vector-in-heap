# vector-in-heap

Biblioteca em C para criar um vetor com heap minima, adicionar no heap e remover no heap. O usuário específica como quer ordenar com a função de comparação(COMP)

## 🚀 Começando

Essas instruções permitirão que você compile e posso usar a biblioteca em seu projeto.


### 📋 Pré-requisitos

De que coisas você precisa para usar o código?

```
GCC ou G++

Baixar o projeto 
```

Baixe [aqui](https://github.com/JoaoCarlosConrado/vector-in-heap/archive/refs/heads/main.zip)


### 🔧 Gerando a biblioteca

Como gerar a biblioteca para usar no seu código

Execute:

```
gcc -c heap.c
```

Será gerado um arquivo chamado heap.o

Exemplo de como compilar junto com seu código:

```
gcc main.c heap.o -o nome_do_programa
```

## 📦 Implantação
Exemplo de Código que utiliza a biblioteca
```
#include <stdio.h>
#include <stdlib.h>
#include "heap.h"

int comparacao(void* x, void* y){
    if(*(int*)x == *(int*)y){
        return 0;
    }else if(*(int*)x > *(int*)y){
        return -1;
    }else{
        return 1;
    }
}

int main(){
    COMP* comp = comparacao;
    int t = 0;
    printf("Tamanho vetor: ");
    scanf("%d", &t);
    HEAP* veto = HEAP_create(t, comp);
    int in[90] = {};
    int i = 0;
    while(in[i] >= 0){
        printf("NUM: ");
        scanf("%d", &in[i]);
        if(in[i] >= 0){
            HEAP_add(veto, &in[i]);
            i++;
        }
    }
    
    
    //veto->elems[200] = "oi";
    printf("%d removido\n", *(int*)HEAP_remove(veto));
    for(int i = 0;i<veto->P;i++){
        printf("%d ", *(int*)veto->elems[i]);
    }
    //printf(veto->elems[200]);
    return 0;
}
```


⌨️ com ❤️ por [João Conrado](https://gist.github.com/JoaoCarlosConrado) 😊

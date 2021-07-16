# Cadastro-com-valida-o-de-celular-e-dada-de-nascimento
Na linguagem C e C++

//Meu R.A. é: ....Digite seu R.A. aqui Dhonis
//A soma do meu R.A. é: ... Coloque aqui a soma do R.A.
// de acordo com passo 4. Incluir no código seu número de RA, e a soma 
//dos dígitos na parte inicial de cabeçalho do código em forma de comentário.

#include <stdio.h>
#include <locale.h>

typedef struct {
    char nome[10]; //lembrando que aqui vai no lugar do dez a soma do R.A.
    int celular;
    int diaNascimento;
    int mesNascimento;
    int anoNascimento;
} dados;

int main (){
    int i, j;
    int celular;
    int diaNascimento;
    int mesNascimento;
    int anoNascimento;
    long long dig1, dig2, aux;
    dados y[3];
    setlocale(LC_ALL, "");
    for (i=0; i<3; i++){ //inicio do loop
        
        printf ("\n Cadastro %d \n", i+1);
        printf ("Nome: ");
        scanf (" %s", y[i].nome);


        printf ("Celular: ");
        scanf ("%d", &y[i].celular); celular = y[i].celular;
            while (celular < 900000000 || celular > 999999999)  //delimita e confere
                {
                    printf("Favor Realizar uma Nova Digitação, Celular Invalido"); //caso não esteja dentro do intervalo
                    scanf ("%d", &y[i].celular);
                }

        printf ("Data de Nascimento (dia): ");
        scanf ("%d", &y[i].diaNascimento); diaNascimento = y[i].diaNascimento;
            while (diaNascimento < 0 || diaNascimento > 32)  //delimita e confere
                {
                    printf("Favor Realizar uma Nova Digitação, Celular Invalido"); //caso não esteja dentro do intervalo
                    scanf ("%d", &y[i].diaNascimento);
                }
        
        
        printf ("Data de Nascimento (mês): ");
        scanf ("%d", &y[i].mesNascimento); mesNascimento = y[i].mesNascimento;
            while (mesNascimento < 0 || mesNascimento > 13)  //delimita e confere
                {
                    printf("Favor Realizar uma Nova Digitação, Celular Invalido"); //caso não esteja dentro do intervalo
                    scanf ("%d", &y[i].mesNascimento);
                }
        
        printf ("Data de Nascimento (ano): ");
        scanf ("%d", &y[i].anoNascimento); anoNascimento = y[i].anoNascimento;
             while (anoNascimento < 1900 || anoNascimento > 2021)  //delimita e confere
                {
                    printf("Favor Realizar uma Nova Digitação, Celular Invalido"); //caso não esteja dentro do intervalo
                    scanf ("%d", &y[i].anoNascimento);
                }
        
    }


        printf ("\n\n CONSULTA NO CADASTRO \n");
         printf ("Escolha uma posição a exibir (1 a 3): ");
        scanf ("%d", &i);
        printf ("Nome: %s\n", y[i-1].nome);
        printf ("Celular: %d\n", y[i-1].celular);
        printf ("Data de Nascimento: %d/%d/%d\n", y[i-1].diaNascimento, y[i-1].mesNascimento, y[i-1].anoNascimento);
        //esta ultima linha mostra os dados do cadastro de acordo com o que vc escolheu

}

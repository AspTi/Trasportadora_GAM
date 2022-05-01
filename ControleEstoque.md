algoritmo "ControleProdutos"
// Função :  Controle de estoque na  loja qie possui.
//           10 tipos de produtos em estoque.
// Autor :  Aquiles
// Data : 29/04/2022

var
   codigoProd:vetor[1..10] de inteiro
   descricaoProd:vetor[1..10] de caractere
   quantidadeProd:vetor[1..10] de inteiro

   opcaoEscolhida:inteiro
   cont:inteiro
   codigo:inteiro
   quantidade:inteiro
   i:inteiro
   existeCodigo: logico
inicio

   MUDACOR("Amarelo","Frente")
   enquanto verdadeiro faca
       escreval("#===========    MENU DE OPÇÕES    =============#")
       escreval("#                                              #")
       escreval("# [1]- Entrar com os dados do estoque:         #")
       escreval("# [2]- Entrada de produtos no estoque:         #")
       escreval("# [3]- Saida de produtos do estoque:           #")
       escreval("# [4]- Relatório:                              #")
       escreval("# [5]- Sair:                                   #")
       escreval("#==============================================#")
       leia (opcaoEscolhida)
       escolha opcaoEscolhida
          caso 1
              limpatela
              cont<-cont+1
              se(cont <= 10) entao
              MUDACOR("azul","Frente")
                Escreval("==== Cadastro de novos produtos =====:")
                escreva("Digite o código: ")
                leia(codigoProd[cont])
                escreva("Digite a Descrição: ")
                leia(descricaoProd[cont])
                escreva("Digite a Quantidade: ")
                leia(quantidadeProd[cont])
              fimse
          caso 2
              limpatela

              escreval("====     Entrada de Produtos     =====:")
              escreva("Digite o código para pesquisa: ")
              leia(codigo)
              existeCodigo<-falso
              para i de 1 ate 10 faca

                 se codigoProd[i] = codigo entao
                       escreva ("Digite a quantidade a ser adicionada no estoque: ")
                       Leia(quantidade)
                       quantidadeProd[i]<-quantidadeProd[i]+ quantidade
                       existeCodigo<-verdadeiro
                 fimse
              fimpara

                 se nao (existeCodigo) entao
                    escreva("CódigoInexistente:")
                 fimse

          caso 3
             limpatela

             escreval("==    Saída de Produtos so Estoque   ==:")
             escreva("Digite o código para pesquisa: ")
             leia(codigo)
             existeCodigo<-falso
             para i de 1 ate 10 faca
                se codigoProd[i] = codigo entao
                      escreva("Digite a quantidade a ser REMOVIDA do estoque: ")
                      leia(quantidade)

                      se(quantidadeProd[i]>= quantidade)entao
                         quantidadeProd[i]<-quantidadeProd[i]- quantidade
                      senao
                         escreva ("Quantidade em estoque inferior a solicitada!!!")
                      fimse
                      existeCodigo<-Verdadeiro
                fimse
             fimpara

          caso 4
             limpatela
             MUDACOR("verde","Frente")
             escreval("====  Relatório de Produtos   =====:")
             para i de 1 ate 10 faca
                 escreval("Código: ",codigoProd[i],", Descrição: ",descricaoProd[i],", quantidade: ",quantidadeProd[i])
             fimpara

          caso 5

                interrompa
          fimescolha
    fimenquanto
fimalgoritmo

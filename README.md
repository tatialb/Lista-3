# Lista-3
Exercícios da lista 3
#LISTA 3#
#Analise de Dados - Aluna Tatiane Albuquerque#


####Pergunta 1####

#Site do Github: https://github.com/tatialb/Lista-3#
  
####Pergunta 2####

X <- c(2,5,7,8,10,14,24,32,37,39,46,55)
#variavel x de numeros aleatorios#

sum(X)
Y <- c(3,10,23,37,58,67,71,80,92,94,100,105)
#variavel y de numeros aleatorios#

sum(Y)
#somatorio da variavel y#
Z <- X+Y
#atribuição da soma de X e Y a Z#
sum(Z)
#Z multiplicado pelo meu CPF#
Z*11158922400
#Resposta:
#[1] 5.579461e+10 1.673838e+11 3.347677e+11
#[4] 5.021515e+11 7.588067e+11 9.038727e+11
#[7] 1.060098e+12 1.249799e+12 1.439501e+12
#[10] 1.484137e+12 1.629203e+12 1.785428e+12#


####Pergunta 3####

head(mtcars)
#base de dados aleatorias mtcars#
data(mtcars)
#descricao dos tipos#
nrow(mtcars)
# 32 linhas, observacoes#
dim(mtcars)
#numero de dimensoes#
mtcars[3]
#impressao da primeira coluna da base#
mtcars[2,]
#impressao da segunda linha da base#
mtcars[4,2]
#o quarto elemento e o 6 do Hornet 4 Drive na coluna do cyl#

summary(mtcars)
#RESUMO GERAL#

####Pergunta 4####

require(ffbase)
setwd("C:/Users/tatia/Desktop/Mestrado UFPE/ANALISE DE DADOS")
#localizando o arquivo no local#
turmas <- read.csv2.ffdf(file = "TURMAS.csv", sep = "|")
#atribuindo uma nova variavel turmas ao TURMAS.CSV#
dim(turmas)
#observacao da dimensao do objeto#
summary(turmas)
#Resumo#
turmas_pe <- subset(turmas, CO_UF == "26")
#registros referentes ao estado de PE#
dim(turmas_pe)
turmas_pe <- as.data.frame(turmas_pe)
#transformacao em data.frame#
save(turmas_pe, file = "TURMASPE.RData")
#Salvando a base de dados#


####Pergunta 5####

require(ffbase)
library(readr)
setwd("C:/Users/tatia/Desktop/Mestrado UFPE/ANALISE DE DADOS")
load("TURMASPE.RData")
View(turmas_pe)
#visualizacao do banco de dados#
dim(turmas)
#dimensao do objeto#
mean(turmas_pe$NU_MATRICULAS)
#achando a media#

#RESPOSTA FINAL: a media do numero de matriculas e 23.07089#


####Pergunta 6####

getwd("C:/Users/tatia/Desktop/Mestrado UFPE/ANALISE DE DADOS")
#localizando o arquivo#
docentes_ne <- read.csv2.ffdf(file = "DOCENTES_NORDESTE.csv", sep = "|", first.rows=100000)
#atribuindo nova variavel para leitura do arquivo dos DOCENTES_NORDESTE#

dim(docentes_ne)
#resultado da dimensao dos dados : [1] 2930354     132#

docentes_ne <- as.data.frame(docentes_ne)
#salvar como DataFrame#

docentes_pe <- subset(docentes, CO_UF == "26")
#observacao da variavel sobre raça e cor no Censo relacionado ao subconjunto de PE#
#filtrando a base pelo estado de Pernambuco#

docentes_pe <- as.data.frame(docentes_pe)
#criacao do dataframe#
table(docentes_pe$TP_COR_RACA) 
#Tabela docentes_pe referente a cor e raça#

prop.table(table(docentes_pe$TP_COR_RACA))*100
#0          1          2          3          4          5#
#44.0003102 23.7823599  3.5646520 27.7994393  0.3438641  0.5093745
#Porcentagem#

# RESPOSTA: 
#percentual de docentes que não se declararam sobre a cor ou raça = 44%
#alunos se declararam pretos = 3.5%
#alunos se declararam pardos = 27.7%
3.5+27.7
#resultado da soma daqueles que se declararam ser preto e pardo = 31.2%

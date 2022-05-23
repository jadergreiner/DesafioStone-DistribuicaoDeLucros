# DesafioStone-DistribuicaoDeLucros
Desafio de análise de dados

Abaixo está a transcrição do objetivo.

Ao fim da transcrição, segue a lógica utilizada na resolução e qual a fórmula aplicada no código.

# Desafio - Distribuição de lucros

<img src  = "https://seeklogo.com/images/S/stone-pagamentos-logo-781DFFF629-seeklogo.com.png">

## Objetivos gerais

Avaliar o candidato (a) nos conceitos de capacidade analítica , qualidade de código, aplicação de boas práticas,
resiliência, disponibilidade, performance e o bom uso do git (clareza dos commits, divisão do trabalho e
melhores práticas).

## Descrição

Uma empresa fechou o ano de operação com lucro e deseja reparti-lo entre seus funcionários, com o objetivo
de ser justa criou uma regra para a distribuição deste montante por: área, tempo de empresa, e faixa salarial
(os funcionários que ganham menos teriam sua participação incrementada). Para isso foi solicitado ao time de
tecnologia que desenvolva um processo que receba um valor máximo em dinheiro e, olhando a base de dados
da empresa, distribua o montante para os funcionários já cadastrados com os dados abaixo. Tal distribuição
segue determinadas regras descritas a seguir.

## Regras gerais

#### Foi estabelecido um peso por área de atuação (Quanto maior o peso, maior o valor recebido):
* Peso 1: Diretoria;
* Peso 2: Contabilidade, Financeiro, Tecnologia;
* Peso 3: Serviços Gerais;
* Peso 5: Relacionamento com o Cliente;

#### Foi estabelecido um peso por faixa salarial e uma exceção para estagiários(Quanto maior o peso menor o
valor recebido):
* Peso 5: Acima de 8 salários mínimos;
* Peso 3: Acima de 5 salários mínimos e menor que 8 salários mínimos;
* Peso 2: Acima de 3 salários mínimos e menor que 5 salários mínimos;
* Peso 1: Todos os estagiários e funcionários que ganham até 3 salários mínimos;

#### Foi estabelecido um peso por tempo de admissão(Quanto maior o peso maior o valor recebido):
* Peso 1: Até 1 ano de casa;
* Peso 2: Mais de 1 ano e menos de 3 anos;
* Peso 3: Acima de 3 anos e menos de 8 anos;
* Peso 5: Mais de 8 anos

Seguindo as regras estabelecidas, proponha uma fórmula para chegar ao bônus de cada funcionário e faça o cálculo de quanto cada funcionário deveria receber considerando o lucro da empresa de R$ 5.000.000,00.

## Input de dados

Estamos enviando anexo a base de dados de funcionários.

## Retorno esperado

O processo deve ter como resultado além do valor a ser pago para cada funcionário, algumas informações gerenciais:
* Total distribuído = Soma do que foi pago a todos os funcionários
* Total disponibilizado = O valor que a empresa deseja distribuir
* Total distribuído e número de funcionários por área
* Total distribuído e número de funcionários por faixa salarial
* Total distribuído e número de funcionários por tempo de admissão

Além disso, todo o código deve ser disponibilizado via github.

## Dicas

* Surpreenda-nos e lembre-se menos é mais!
* Documentação e explicação do repositório facilita o entendimento de quem está analisando.
* Lembre-se que o seu código é um espelho da sua qualidade!

Desejamos que divirta-se e aproveite ao máximo esse momento de desafio!

# Resolução  do desafio

* Inicialmente recebi os dados e realizar uma primeira análise dos dados e de quais perguntas devemos responder;
* Pensando na estratégia de resolução, optei em desenvolver uma fórmula inicial em planilha, com dados "controlados" e testar a eficácia da fórmula;
* Criei então uma planilha simulada com dados gerais, mas que pudesse atender aos cenários propostos pelo desafio;
* Iniciei a montagem do respositório no Github
* Com a lógica e fórmula definida, gerei o código em um Notebook Python.
* Exportei os dados para Excel e montei visualizações no Tableu no formato público.

## Fórmula utilizada

Fator = (F1 + F2 + F3) / ( SOMA (TOTAL F1) +
                           SOMA (TOTAL F2) + 
                           SOMA (TOTAL F3)
                          )
Bonus a receber = Total a distribuir * fator                          
                          
### Legenda                          
**Fator** = Resultado da fórmula que gera o percentual que será percebido pelo funcionário. Inicialmente somamos os pesos individuais do funcionário (F1 + F2 + F3) e dividimos pelo peso total de toda a base de dados.

**F1** = Peso correspondente a area do funcionário.

**F2** = Peso correspondente a faixa salarial do funcionário. O F2 tem uma metologia para o peso final. Como neste caso, maior o peso, menor o valor recebido, a fórmula do F2 ficou assim = *F2 = 6 - peso*

**F3** = Peso correspondente ao tempo de admissão do funcionário.

**Bonus a receber** = Valor que será destinado a bônus ao funcionário. Corresponde a multiplicação do fator pelo valor total a distribuir.

## Dados gerenciais
* Número de funcionários por area: https://public.tableau.com/app/profile/jader.greiner/viz/DesafioStone-Funcionriosporarea/Planilha2?publish=yes
* Valores distribuidos por area: https://public.tableau.com/app/profile/jader.greiner/viz/DesafioStone-Valoresporarea/Planilha1?publish=yes
* Valores distribuídos por faixa salarial: https://public.tableau.com/app/profile/jader.greiner/viz/DesafioStone-Valorporfaixasalarial/Planilha1?publish=yes
* Número de funcionários por faixa salarial: https://public.tableau.com/app/profile/jader.greiner/viz/DesafioStone-funcionariosporfaixasalarial/Planilha2?publish=yes
* Número de funcionários por tempo de casa: https://public.tableau.com/app/profile/jader.greiner/viz/DesafioStone-funcionariosportempodecasa/Planilha2?publish=yes
* Valores distribuídos por tempo de casa: https://public.tableau.com/app/profile/jader.greiner/viz/DesafioStone-valoresportempodecasa/Planilha1?publish=yes


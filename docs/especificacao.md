# 3. DOCUMENTO DE ESPECIFICAÇÃO DE REQUISITOS DE SOFTWARE

Nesta parte do trabalho você deve detalhar a documentação dos requisitos do sistema proposto de acordo com as seções a seguir. Ressalta-se que aqui é utilizado como exemplo um sistema de gestão de cursos de aperfeiçoamento.

## 3.1 Objetivos deste documento
Descrever e especificar as necessidades da Coordenação do Curso de Sistemas de Informação da PUC Minas que devem ser atendidas pelo projeto SCCA – Sistema de Cadastro de Cursos de Aperfeiçoamento.

## 3.2 Escopo do produto

### 3.2.1 Nome do produto e seus componentes principais
O produto será denominado SCCA – Sistema de Cadastro de Cursos de Aperfeiçoamento. Ele terá somente um componente (módulo) com os devidos elementos necessários à gestão de cursos.

### 3.2.2 Missão do produto
Gerenciar informações sobre a oferta de cursos de aperfeiçoamento, gerenciar a composição das turmas, alunos, professores e matrículas. 

### 3.2.3 Limites do produto
O SCCA não fornece nenhuma forma de avaliação de alunos, pagamento de parcelas do curso, pagamento a professore e agendamentos. O SCCA não contempla o atendimento a vários cursos de Sistemas de Informação de outras unidades da PUC Minas.

### 3.2.4 Benefícios do produto

| # | Benefício | Valor para o Cliente |
|--------------------|------------------------------------|----------------------------------------|
|1	| Facilidade no cadastro de dados |	Essencial |
|2 | Facilidade na recuperação de informações | Essencial | 
|3 | Segurança no cadastro de matrículas | Essencial | 
|4	| Melhoria na comunicação com os alunos	| Recomendável | 

## 3.3 Descrição geral do produto

### 3.3.1 Requisitos Funcionais

| Código | Requisito Funcional (Funcionalidade) | Descrição |
|--------------------|------------------------------------|----------------------------------------|
| RF1 | Gerenciar Curso de Aperfeiçoamento |	Processamento de Inclusão, Alteração, Exclusão e Consulta de Cursos de Aperfeiçoamento |
| RF2 |	Gerenciar Professor	| Processamento de Inclusão, Alteração, Exclusão e Consulta de professores |
| RF3	| Gerenciar Matrícula |	Processamento de Inclusão, Alteração, Exclusão e Consulta de Matrículas de alunos em Cursos de Aperfeiçoamento |
| ... |	...	| ... |

### 3.3.2 Requisitos Não Funcionais

| Código | Requisito Não Funcional (Restrição) |
|--------------------|------------------------------------|
| RNF1 | O ambiente operacional a ser utilizado é o Windows XP. |
| RNF2 | O sistema deverá executar em um computador configurado com uma impressora de tecnologia laser ou de jato de tinta, a ser usada para impressão dos relatórios. |
| RNF3 |	Segurança	O produto deve restringir o acesso por meio de senhas individuais para o usuário. |
| ... |	... |	... |

### 3.3.3 Usuários 

| Ator | Descrição |
|--------------------|------------------------------------|
| Coordenador |	Usuário gerente do sistema responsável pelo cadastro e manutenção de cursos de aperfeiçoamento. Possui acesso geral ao sistema. |
| Secretaria |	Usuário responsável por registros de alunos, professores, turmas e gerência de matrículas. |
| ... |	... |	... |

## 3.4 Modelagem do Sistema

### 3.4.1 Diagrama de Casos de Uso
Como observado no diagrama de casos de uso da Figura 1, a secretária poderá gerenciar as matrículas e professores no sistema, enquanto o coordenador, além dessas funções, poderá gerenciar os cursos de aperfeiçoamento.

#### Figura 1: Diagrama de Casos de Uso do Sistema.

![dcu](https://github.com/user-attachments/assets/41f6b731-b44e-43aa-911f-423ad6198f47)
 
### 3.4.2 Descrições de Casos de Uso

Cada caso de uso deve ter a sua descrição representada nesta seção. Exemplo:

#### Gerenciar Professor (CSU01)

Sumário: A Secretária realiza a gestão (inclusão, remoção, alteração e consulta) dos dados sobre professores.

Ator Primário: Secretária.

Ator Secundário: Coordenador.

Pré-condições: A Secretária deve ser validada pelo Sistema.

Fluxo Principal:

1) 	A Secretária requisita manutenção de professores.
2) 	O Sistema apresenta as operações que podem ser realizadas: inclusão de um novo professor, alteração de um professor, a exclusão de um professor e a consulta de dados de um professor.
3) 	A Secretária seleciona a operação desejada: Inclusão, Exclusão, Alteração ou Consulta, ou opta por finalizar o caso de uso.
4) 	Se a Secretária desejar continuar com a gestão de professores, o caso de uso retorna ao passo 2; caso contrário o caso de uso termina.

Fluxo Alternativo (3): Inclusão

a)	A Secretária requisita a inclusão de um professor. <br>
b)	O Sistema apresenta uma janela solicitando o CPF do professor a ser cadastrado. <br>
c)	A Secretária fornece o dado solicitado. <br>
d)	O Sistema verifica se o professor já está cadastrado. Se sim, o Sistema reporta o fato e volta ao início; caso contrário, apresenta um formulário em branco para que os detalhes do professor (Código, Nome, Endereço, CEP, Estado, Cidade, Bairro, Telefone, Identidade, Sexo, Fax, CPF, Data do Cadastro e Observação) sejam incluídos. <br>
e)	A Secretária fornece os detalhes do novo professor. <br>
f)	O Sistema verifica a validade dos dados. Se os dados forem válidos, inclui o novo professor e a grade listando os professores cadastrados é atualizada; caso contrário, o Sistema reporta o fato, solicita novos dados e repete a verificação. <br>

Fluxo Alternativo (3): Remoção

a)	A Secretária seleciona um professor e requisita ao Sistema que o remova. <br>
b)	Se o professor pode ser removido, o Sistema realiza a remoção; caso contrário, o Sistema reporta o fato. <br>

Fluxo Alternativo (3): Alteração

a)	A Secretária altera um ou mais dos detalhes do professor e requisita sua atualização. <br>
b)	O Sistema verifica a validade dos dados e, se eles forem válidos, altera os dados na lista de professores, caso contrário, o erro é reportado. <br>
 
Fluxo Alternativo (3): Consulta

a)	A Secretária opta por pesquisar pelo nome ou código e solicita a consulta sobre a lista de professores. <br>
b)	O Sistema apresenta uma lista professores. <br>
c)	A Secretária seleciona o professor. <br>
d)	O Sistema apresenta os detalhes do professor no formulário de professores. <br>

Pós-condições: Um professor foi inserido ou removido, seus dados foram alterados ou apresentados na tela.

### Gerenciar Treinos dos Alunos (CSU02)
Sumário: O Professor realiza a gestão (criação, alteração, exclusão e consulta) dos treinos dos alunos matriculados na academia.

Ator Primário: Professor
Ator Secundário: Aluno

Pré-condições:
O Professor deve estar autenticado no sistema.
O aluno deve estar previamente cadastrado.

Fluxo Principal:
O Professor acessa o sistema e seleciona a opção de gerenciamento de treinos.
O Sistema apresenta as operações disponíveis: criação, alteração, exclusão e consulta de treinos.
O Professor seleciona a operação desejada ou opta por encerrar.
O Sistema executa a operação escolhida.
Caso o Professor deseje continuar, o fluxo retorna ao passo 2; caso contrário, o caso de uso é encerrado.
Fluxo Alternativo (3): Criação de Treino

a) O Professor seleciona a opção de criar um treino.

b) O Sistema solicita os dados do treino (exercícios, séries, repetições, carga, observações).
c) O Professor informa os dados.

d) O Sistema valida as informações.

e) Se válidas, o treino é cadastrado para o aluno; caso contrário, o sistema solicita correção.

Fluxo Alternativo (1): Alteração de Treino

a) O Professor seleciona um treino existente.

b) O Sistema apresenta os dados do treino.

c) O Professor altera as informações desejadas.

d) O Sistema valida e salva as alterações.

Fluxo Alternativo (2): Exclusão de Treino

a) O Professor seleciona um treino.

b) O Professor solicita a exclusão.

c) O Sistema verifica se o treino pode ser removido.

d) Se possível, remove o treino; caso contrário, informa erro.

Fluxo Alternativo (3): Consulta de Treino

a) O Professor busca treinos por aluno.

b) O Sistema apresenta a lista de treinos.

c) O Professor seleciona um treino.

d) O Sistema exibe os detalhes.

Pós-condições:
O treino do aluno foi criado, alterado, removido ou consultado com sucesso.

### Gerenciar Pagamentos (CSU03)
Sumário: O setor financeiro realiza o controle de pagamentos dos alunos, incluindo registro, consulta e verificação de inadimplência.

Ator Primário: Funcionário do Financeiro
Ator Secundário: Aluno

Pré-condições:
O funcionário deve estar autenticado no sistema.
O aluno deve estar cadastrado.

Fluxo Principal:
O Funcionário acessa o módulo financeiro.
O Sistema apresenta as opções: registrar pagamento, consultar pagamentos, verificar inadimplência.
O Funcionário seleciona uma opção ou encerra o caso de uso.
O Sistema executa a operação.
O fluxo retorna ao menu inicial ou é encerrado.

Fluxo Alternativo (1): Registrar Pagamento

a) O Funcionário seleciona um aluno.

b) O Sistema apresenta os débitos pendentes.

c) O Funcionário informa o pagamento (valor, data, forma de pagamento).

d) O Sistema valida os dados.

e) Se válidos, registra o pagamento e atualiza o status.

Fluxo Alternativo (2): Consultar Pagamentos

a) O Funcionário busca pagamentos por aluno ou período.

b) O Sistema apresenta a lista de pagamentos.

c) O Funcionário seleciona um registro.

d) O Sistema exibe os detalhes.

Fluxo Alternativo (3): Verificar Inadimplência

a) O Funcionário solicita a lista de alunos inadimplentes.

b) O Sistema gera a lista com base nos pagamentos em atraso.

c) O Funcionário visualiza os alunos com pendências.

Pós-condições:
Os pagamentos foram registrados, consultados ou analisados corretamente.

### 3.4.3 Diagrama de Classes 

A Figura 2 mostra o diagrama de classes do sistema. A Matrícula deve conter a identificação do funcionário responsável pelo registro, bem com os dados do aluno e turmas. Para uma disciplina podemos ter diversas turmas, mas apenas um professor responsável por ela.

#### Figura 2: Diagrama de Classes do Sistema.
 
![image](https://github.com/user-attachments/assets/abc7591a-b46f-4ea2-b8f0-c116b60eb24e)


### 3.4.4 Descrições das Classes 

| # | Nome | Descrição |
|--------------------|------------------------------------|----------------------------------------|
| 1	|	Aluno |	Cadastro de informações relativas aos alunos. |
| 2	| Curso |	Cadastro geral de cursos de aperfeiçoamento. |
| 3 |	Matrícula |	Cadastro de Matrículas de alunos nos cursos. |
| 4 |	Turma |	Cadastro de turmas.
| 5	|	Professor |	Cadastro geral de professores que ministram as disciplinas. |
| ... |	... |	... |

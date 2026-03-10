# modelagem-desenvolvimento-daniel
projeto Biblioteca universitária

1. Identificação do projeto

Nome do projeto:

Biblioteca universitária

Grupo (nomes):

Beatriz Gasparini Menezes RA: 3026103855

Jailton Sousa de Lima   	 RA: 3023104935 

Leandro de Sá Costa   	 RA: 3024202588

Matheus Osmédio Araujo 	 RA: 3024102070

Matheus Souza Araujo	 RA: 3023101715

Nicolas Masayoshi Urata 	 RA: 3026102723

Versão/data:

2.4 - 09/03/2026

3. Visão geral da empresa

Em uma universidade há uma biblioteca da qual efetua mais de 70 empréstimos de livros todos os dias funcionais, mas devido a alta demanda acaba gerando problemas nesse serviço, onde por ser feito de maneira manual acaba tendo a perda de informações e confusão no controle de empréstimo.
Após muita insistência dos administradores da biblioteca, os donos da universidade decidiram fazer algo sobre isso e foram em busca de modernizar a biblioteca trazendo computadores e contratando pessoas para desenvolver um sistema do qual ficaria responsável de atender as demandas da biblioteca.

4. Problema atual (dor) e consequências

Perda e inconsistência de dados: Registros de empréstimos são frequentemente esquecidos, rasurados ou perdidos, resultando em livros não devolvidos e prejuízo financeiro/cultural para o acervo. 

Lentidão e retrabalho no atendimento: Em dias de pico, procurar a ficha de um cliente ou verificar manualmente nas estantes se um livro está disponível gera filas e frustração para os leitores.

Falta de controle de estoque: Não há visibilidade sobre a quantidade real de livros, quais títulos são mais procurados ou quais exemplares estão danificados e precisam de reposição.

4. Objetivo da solução 
   
Objetivo principal

Desenvolver um sistema digital simples para modernizar o atendimento e centralizar o controle de estoque e empréstimos da biblioteca.

Benefícios esperados 

Agilidade nos processos de cadastro, empréstimo e devolução.
Controle rigoroso e em tempo real da disponibilidade e do estado dos livros (gerenciamento de dados).
Melhoria na experiência de atendimento ao público, com respostas rápidas sobre o acervo.

6. Stakeholders e perfis de usuário
Atendentes: Responsáveis pela operação diária. Necessitam de uma interface extremamente amigável e intuitiva. Realizam empréstimos, devoluções, consultas básicas de disponibilidade e cadastros de novos usuários.
Bibliotecário: Responsável pela gestão e suporte do sistema. Além das permissões de atendente, pode cadastrar novos livros no acervo, inativar exemplares perdidos/danificados e acessar relatórios de gestão (como livros em atraso).

7. Escopo do sistema (IN / OUT)

Dentro do escopo (IN):

1 - Cadastro de livros

2 - Cadastro de usuário

3 - Empréstimo de livros 

4- Catálogo de livros

5 - Devolução de livros

6 - Reservas de livros

7 - Cadastro de administradores

8 - Sistema de bloqueio temporário de empréstimo por atraso de livros


 Fora do escopo (OUT): 
 
1 - Envio de emails

2 - Reserva Online

3 - Vendas de livros

4 - Sistema de multas monetária  por atraso na devolução

5 - Sistema de renovação de livro


7. Requisitos Funcionais (RF)

1 - Cadastrar clientes com campos obrigatórios (Id, nome, telefone, matricula, email, logradouro)

2 - Cadastro de livros

3 - Empréstimo de livros

4 - Devolução de livros

5 - Reservas de livros

6 - Sistema de bloqueio temporário de empréstimo por atraso de livros


9. Regras de Negócio (RN)

1 - Não pode ter empréstimo da mesma cópia do livro para pessoas distintas


2 - A pessoa não pode pegar ou reservar mais de uma cópia do mesmo livro


3 - Limitar empréstimo de 5 livros por pessoa

4 - Limitar reserva a 2 livros por pessoa  

5 - Realizar empréstimos apenas para pessoas cadastradas

6 - A mesma pessoa não pode ter mais de um cadastro

7 - Limitar o tempo do empréstimo do livro a 10 dias



10. Requisitos Não Funcionais (RNF) e restrições técnicas

1 - Interface simples e consistente (computador)

2 - banco de dados local

3 - mostrar status dos livros

4 - Cadastro máximo de 20000 livros

5 - Cadastro máximo de 5000 clientes


10. Obstáculos, riscos e restrições do mundo real

Restrições: prazo curto, equipe pequena

Obstáculos culturais: baixa maturidade digital

Riscos: sobrecarga do sistema, treinamento, erro no backup

11. Dados principais (entidades) e relacionamentos esperados

1 - Reserva(id, id_livro, id_cliente, data_hora)

2 - Livro(id, título, autor ,gênero, quantidade)	

3 - Empréstimo(id, id_livro, id_cliente, id_funcionario, data_retirada, data_devolucao_esperada)

4 - Cliente(Id, nome, telefone, matricula, email, logradouro)

5 - Funcionário(Id, nome, telefone, email, senha)

6 - Devolução(id, id_livro, id_cliente, id_funcionario, data_devolucao)

12. Casos de uso (lista + breve descrição)

Empréstimo realizado - O Lourival foi pegar um livro sobre aviação, fez seu cadastro com sucesso e conseguiu pegar seu livro.

Reserva realizada - O Leandro queria realizar um empréstimo de um livro, porém o mesmo estava emprestado então ele efetuou a reserva do livro.

Empréstimo negado - O Lourival esqueceu que tinha pegado um livro sobre aviação, voltou a biblioteca e tentou pegar o mesmo livro, mas ele já tinha uma cópia do mesmo livro.

Livro Não encontrado - Adalberto foi procurar um livro que não tem no catálogo da biblioteca.

Empréstimo bloqueado - Roberta Carla estava com uma pendência de um livro e tentou efetuar um empréstimo, mas o sistema bloqueou pelo atraso de um outro livro.

13. Cenários de uso 

Cenário 1: Fluxo principal

1 - Cliente chega
    
2 - Verifica se o cadastro já existe

Se o cadastro já existe pule para etapa 8

Se não tiver cadastro continua as etapas seguintes

3 - Cadastrar cliente

4 - Verificar a matrícula no sistema da universidade

Se não, mostrar erro de matrícula inválida

5 - Verifica o email no regex

Se não, mostrar erro de email invalido

6 - Verifica o telefone no regex

Se não, mostrar erro de telefone invalido

7 - Cadastrado com sucesso

8 - Continue com o empréstimo/reserva 


Cenário 2: Empréstimo/reserva

1 - Cliente pede um livro 

2 - Verifica se o livro está disponível no catálogo para empréstimo

Se tiver no catálogo siga para próxima etapa

Se não, mostrar livro indisponível

3 - Pede cadastro do cliente

4 - Efetue o empréstimo do livro

Se há pendências negar empréstimo

Se não, realizar empréstimo



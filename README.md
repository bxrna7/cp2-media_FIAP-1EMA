# CP2-media_FIAP-1EMA

Desafio FIAP: Cálculo da Média Final
Este notebook Python tem como objetivo calcular a média final de um aluno da FIAP, seguindo as regras específicas de avaliação da instituição. Ele abrange o cálculo das médias dos Checkpoints (CPs), Sprints (SPs), Global Solutions (GSs) para ambos os semestres, a média semestral e, por fim, a média final, com a consideração de exame caso necessário.

Estrutura do Notebook
O notebook está dividido nas seguintes seções:

Cálculo da Média dos Checkpoints (MCP)
Cálculo da Média das Sprints (MSP)
Cálculo da Média da Global Solution (GS) e Média Semestral (MS)
Repetição dos Cálculos para o Segundo Semestre
Cálculo da Média Final (MF)
Função Unificada para Cálculo da Média Final
1. Cálculo da Média dos Checkpoints (MCP)
Objetivo: Calcular a média dos checkpoints, eliminando a menor nota dentre três CPs e considerando as duas maiores.
Variáveis: CP1, CP2, CP3 (notas dos checkpoints).
Lógica: As três notas são inseridas, convertidas para float, armazenadas em uma lista, ordenadas, e a média é calculada com as duas notas mais altas.
2. Cálculo da Média das Sprints (MSP)
Objetivo: Calcular a média das duas notas de Sprint.
Variáveis: SP1, SP2 (notas das sprints).
Lógica: As duas notas são inseridas, convertidas para float, e sua média é calculada.
3. Cálculo da Média da Global Solution (GS) e Média Semestral (MS) - Primeiro Semestre
Objetivo: Determinar a nota da Global Solution (considerando a SUB se a GS for 0) e calcular a média semestral.
Variáveis: GS1 (nota da Global Solution), SUB (nota da Substitutiva).
Lógica:
Primeiramente, é calculada uma md_parcial1 (0.2 * MSP1 + 0.2 * MCP1) para verificar se o aluno já possui média suficiente para aprovação sem a GS, ou qual nota mínima precisa na GS.
O usuário insere a nota da GS. Se a nota for 0, é solicitado que insira a nota da SUB, que substituirá a GS.
A Média Semestral (MS1) é calculada usando a fórmula: 0.6 * GS1 + 0.2 * MSP1 + 0.2 * MCP1.
4. Repetição dos Cálculos para o Segundo Semestre
Objetivo: Os mesmos cálculos realizados para o primeiro semestre (MCP, MSP, GS, MS) são repetidos para as notas do segundo semestre, utilizando variáveis com sufixo 2 (ex: MCP2, MSP2, GS2, MS2).
Lógica: Segue exatamente a mesma metodologia dos itens 1, 2 e 3.
5. Cálculo da Média Final (MF)
Objetivo: Calcular a média final do curso e determinar o status do aluno (Aprovado, Exame, Reprovado).
Variáveis: MF (Média Final), exame (nota do exame, se aplicável), MF_nova (Média Final após exame).
Lógica:
A MF é calculada como: 0.4 * MS1 + 0.6 * MS2.
Condições de Status:
MF >= 6.0: Aprovado
MF < 4.0: Reprovado
MF >= 4.0 e MF < 6.0: Exame. Neste caso, é solicitada a nota do exame e a MF_nova é calculada como (exame + MF) / 2. O status final é determinado novamente com base na MF_nova.
6. Função Unificada para Cálculo da Média Final (calculate_fiap_final_grade)
Objetivo: Consolidar toda a lógica de cálculo em uma única função Python, permitindo a fácil reutilização e teste com diferentes conjuntos de notas.
Parâmetros: A função aceita todas as notas de CP, SP, GS (e SUB, se houver) para ambos os semestres como argumentos. Também possui um parâmetro opcional exame_input.
Retorno: A função retorna a média final (mf) e o status final do aluno (final_status).
Benefícios: Facilita a automação, o teste de cenários e a integração em sistemas maiores, tornando o código mais modular e legível.

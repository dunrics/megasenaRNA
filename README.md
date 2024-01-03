# megasenaRNA
Esse código foi criado para gerar uma sequência de SUGESTÕES de números da MegaSena.

Funcionamento

O código está em execução via CRONTAB todos os dias em um servidor na nuvem (Oracle Cloud)

Esse código foi adaptado do artigo: https://medium.com/@polanitzer/how-to-guess-accurately-3-lottery-numbers-out-of-6-using-lstm-model-e148d1c632d6

Utiliza-se como entrada todos os Mil ultimos jogos da MegaSena, analisa esses dados utilizando rede neural e tenta predizer o próximo sorteio da MegaSena. O código possui 5 etapas:

Ordem de execução

(geraDados.py) Extraí da internet o último resultado da MegaSena;

(geraNum1.py) Gera os 5 números mais frequentes dos ultimas 100 concursos e salva a informação em um arquivo (outputMega_Metodo1). Também pega os 5 números que menos saíram e salva em um arquivo CSV (outputMega_Metodo1_menos_frequentes);

(lstmCode1.py) Análise e predição dos números;

(normalizaLSTM.py) Extrai os dados da saída da RNA, abre os números mais sorteados dos últimos 100 concursos. Retira os números zeros e números repetidos encontrados no arquivo de saída da RNA. Substitui por números obtidos do arquivo de mais sorteados

(gitUpload.py) Envia o resultado obtido automaticamente para essa página GIT.

Dependências necessárias -python 3.10.11 ou 3.10.12 -pip install requests -pip install numpy -pip install pandas -pip install scikit-learn -pip install keras -pip install tensorflow -pip install PyGithub

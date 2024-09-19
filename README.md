# OTM - Alteração de Data de Entrega de produtos
Repositório para o projeto interno 05 - Alteração de data de entrega de produtos

Objetivo do projeto: Alterar a data de entrega de vários produtos de uma única vez.

## Usabilidade 

As telas se encontram no menu comercial:

***Comercial/Classificação de itens/Data de entrega de produtos*** -> Tela utilizada para alteração de dados em massa.

***Comercial/Classificação de itens/Rel. alt. dias de entrega*** -> Tela utilizada para consultar as alterações/motivos e dias.

## Tela de alteração de datas de entrega.

Ao abrir a tela, ficará disponível 6 campos para preenchimento.

![image](https://github.com/user-attachments/assets/26892612-d88a-43cf-b98d-fd0946b1276b)

Campos: 

1. Grupo de classificação 1: Esse campo contém a primeira ramificação de classificação de produtos, é permitido e obrigatório selecionar apenas um item da lista.
	* Itens selecionáveis:
 		* 0 - Nenhum
   		* 10 - MATERIAL COMPRADO
     	* 20 - PRODUTOS FABRICADOS
     	* 30 - PRODUTO PRONTO
     	* 99 - GENERICO 	 		  				
2. Grupo de Classificação 2: Esse campo é dinâmico baseado na escolha anterior, será permitido selecionar apenas um item de acordo com a primeira ramificação.
	* Exemplo: Se no primeiro grupo for selecionado a classificação 30, nesse campo será possível selecionar apenas uma classificação abaixo do grupo 30 -> (30.100, 30.200, 30.300...).

![image](https://github.com/user-attachments/assets/fe22107e-603e-4170-9cf8-24be95541653)

3. Grupo de Classificação 2: Esse campo é dinâmico baseado na escolha anterior, será permitido selecionar apenas um item de acordo com a segunda ramificação. 	
	* Exemplo: Se no segundo grupo for selecionado a classificação 30.100, nesse campo será possível selecionar apenas uma classificação abaixo do grupo 30.100 -> (30.100.001, 30.100.002, 30.100.003).

![image](https://github.com/user-attachments/assets/eb167510-511f-4eea-b1a2-876f0631f8ec)

4. Grupo de Classificação 4: Esse campo é dinâmico baseado na escolha anterior, nesse campo fica a critério do usuário selecionar os campos para alteração, podendo selecionar a quantidade necessária!
	* Exemplo: Se no terceiro grupo for selecionado a classificação 30.100.001, nesse campo será possível selecionar mais de uma e qualquer classificação abaixo do grupo 30.100.001 -> (30.100.001.0001, 30.100.001.0002, 30.100.001.0003, 30.100.001.0004, 30.100.001.0005).

![image](https://github.com/user-attachments/assets/2ea2c3ce-5a93-4d56-abe5-95c4c3a5cf68)

5. Dias de Entrega: Esse campo é obrigatório e deve ser preenchido um número que corresponde a quantidade de dias que submetem a entrega do(s) produto(s) selecionado(s).
	* Tipo: Numérico - Valores(0-999)
6. Motivo: Campo para registrar o motivo de alteração da quantidade de dias de entrega. Campo obrigatório!  
	* Tipo: Caracteres - Tamanho(50 Caracteres)

### Validações que ocorrem na tela.

* Campo 1, 2 e 3 devem ser diferente do item ( 0 - Nenhum) - Caso um desses campos esteve com esse valor não permite abrir a próxima ramificação e também não realiza a alteração, apontando um erro em tela!
* Campo 5 não pode ser zerado e não deve ser vazio - Caso as condições citadas forem realizadas será apontado um erro em tela!
* Campo 6 não pode ser vazio - Caso a condição seja aplicada será apontado um erro em tela!

### Fluxo do processo

1. Abrir a tela de alterações
2. Selecionar os campos de acordo com a necessidade e respeitar as validações inseridas.
3. Executar o processo.
4. Ao finalizar será gerado um relatório em tela com os itens/grupos alterados com a quantidade de dias alterados
5. Fim do Processo.

## Tela de Relatórios

Necessário selecionar apenas uma data de início de uma data de fim para buscar as informações de alteração!

Exemplo do relatório: 

![image](https://github.com/user-attachments/assets/7516644a-b056-47e9-9c9b-765c4cfed65c)


## Arquivos da pasta Raiz
	OTMTECH\
	\HELP
	
	\FILES
	
	\IMAGES\CLIENTE\ICONE
		* All images
	OPTIONS\
		OTM_COMERCIAL.MYO
	QUERIES\CLI\COMERCIAL
	    projeto_class_DB\ -- Arquivos a serem executados no banco de dados ( Owner - OTIMIZA)
			P_05_PROCEDURE_P_ALTERA_DIAS_ENTREGA.SQL
			P_05_SEQUENCE_MOT_DIAS_ENTR.SQL
			P_05_TABLE_TMORIVOS_DIAS_ENTREGAS.SQL
		alt_dat_prod.mkq
		rel_alt_prod.mkq
	

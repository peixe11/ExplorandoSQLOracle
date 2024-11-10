Tabela: cultura
Campo	Tipo	Obrigatório	Descrição
id	NUMBER	Sim	Identificador único da cultura
nome	VARCHAR2(100)	Sim	Nome da cultura
Chave Primária: pk_cultura - campo id
Restrição Única: un_cultura_nome - campo nome
Tabela: estado
Campo	Tipo	Obrigatório	Descrição
id	NUMBER	Sim	Identificador único do estado
nome	VARCHAR2(100)	Sim	Nome do estado
Chave Primária: pk_estado - campo id
Restrição Única: un_estado_nome - campo nome
Tabela: safra
Campo	Tipo	Obrigatório	Descrição
id	NUMBER	Sim	Identificador único da safra
estado_id	NUMBER	Sim	Identificador do estado (FK para estado)
cultura_id	NUMBER	Sim	Identificador da cultura (FK para cultura)
ano	NUMBER(4)	Sim	Ano da safra
Chave Primária: pk_safra - campo id
Chave Estrangeira:
fk_safra_estado - estado_id referencia estado(id)
fk_safra_cultura - cultura_id referencia cultura(id)
Tabela: producao
Campo	Tipo	Obrigatório	Descrição
id	NUMBER	Sim	Identificador único da produção
safra_id	NUMBER	Sim	Identificador da safra (FK para safra)
produtividade	NUMBER	Não	Produtividade da safra
area_plantada	NUMBER	Não	Área plantada (em hectares, por exemplo)
producao_total	NUMBER	Não	Total produzido na safra (em toneladas, por exemplo)
Chave Primária: pk_producao - campo id
Chave Estrangeira: fk_producao_safra - safra_id referencia safra(id)
Resumo dos Relacionamentos
cultura possui uma relação 1
com safra via cultura_id.
estado possui uma relação 1
com safra via estado_id.
safra possui uma relação 1
com producao via safra_id.

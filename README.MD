# Executando o projeto

A primeira coisa a se saber para a execução do projeto é que ele foi totalmente desenvolvido no **Databricks**, utilizando a versão gratuita que substituiu a Community Edition. Para mais informações sobre como acessar essa versão, segue o link:

* [Databricks Free Edition](https://www.databricks.com/learn/free-edition)

Procurei deixar o código completamente comentado e de fácil modificação para facilitar a reprodução. Caso surja alguma dificuldade na execução, **entre em contato comigo** para solucionarmos o problema. O contato pode ser feito por e-mail: brunoraphaell99@gmail.com ou pelo WhatsApp informado no momento da inscrição da vaga.

## 1. Conectando o GitHub ao Databricks

Para conectar sua conta do GitHub ao Databricks, você pode seguir o tutorial disponível no link: [Configurar as credenciais do Git & conectar um repositório remoto ao Databricks](https://docs.databricks.com/gcp/pt/repos/get-access-tokens-from-git-provider).

## 2. Colocando o projeto no Databricks

Para colocar o repositório do GitHub dentro do Databricks e podermos trabalhar nele, siga o passo a passo abaixo:

![](https://i.imgur.com/OciYZhv.png)

![](https://i.imgur.com/6n3gnzM.png)

No item **1**, insira o link do repositório. As demais informações serão preenchidas automaticamente.


## 3. Upload dos arquivos

Após a criação da conta no Databricks Free Edition e com o login efetuado, será necessário fazer o upload dos arquivos que serão utilizados no projeto. Abaixo está um passo a passo para realizar o upload no formato de volumes:

![](https://i.imgur.com/f6Fa1gz.png)

![](https://i.imgur.com/KkCJjBZ.png)

![](https://i.imgur.com/HDmjYGg.png)

Selecione onde você deseja salvar as bases de dados:  
![](https://i.imgur.com/IMfEN6A.png)

Após o upload dos arquivos, insira os respectivos *paths* nos notebooks.

## 4. Modificando os notebooks

Os notebooks possuem uma célula destinada à inserção do caminho das bases de dados salvas e também do local onde você deseja armazenar a base de dados processada ao final da execução. Modifique essa célula com os seus *paths* para evitar erros.  

Por exemplo, no notebook `1_data_processing`, a configuração está da seguinte forma:

```python
# Modificar conforme o caminho de onde foi feito o upload dos arquivos
PATH_OFFERS_BRUTO = "/Volumes/workspace/raw/dados_brutos/offers.json"
PATH_PROFILE_BRUTO = "/Volumes/workspace/raw/dados_brutos/profile.json"
PATH_TRANSACOES_BRUTO = "/Volumes/workspace/raw/dados_brutos/transactions.json"
PATH_BASE_PROCESSADA = "workspace.processed.base_processada"
```

Outro exemplo de modificação necessária para definir o caminho na sua estrutura é na função `otimizar_e_registrar_modelo` do notebook `2_modeling`, além do local onde são definidas as constantes:

```
# Mude aqui para registrar o modelo no seu caminho!!!
local_salvo = f"workspace.modelos_ml.{nome_modelo}"
```

Caso seja de seu interesse executar o projeto localmente, basta utilizar o comando:


```
git clone https://github.com/BrunoRaphaell/bruno-raphaell-case.git
```

Aqui deixei também o arquivo `requirements.txt` para instalar as depências no ambiente virtual com o comando:

```
pip install -r requirements.txt
```

No entanto, como o projeto foi desenvolvido especificamente para ser executado no Databricks, não é possível prever o comportamento da execução em ambiente local. Por isso, sugiro utilizar a versão gratuita do Databricks Free Edition.

## 5. Dashboard

Para este projeto, foi desenvolvido um painel no Power BI, disponível na pasta `Dashboard/Analises dos clientes e ofertas.pbix`. Caso você não tenha o Power BI instalado, é possível baixá-lo no seguinte link: [Download Power BI](https://www.microsoft.com/pt-br/power-platform/products/power-bi/downloads).


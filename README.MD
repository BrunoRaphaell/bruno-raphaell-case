# Executando o projeto

A primeira coisa a se saber para a execução do projeto é que ele foi totalmente desenvolvido no **Databricks**, utilizando a versão gratuita que substituiu a Community Edition. Para mais informações sobre como acessar essa versão, segue o link:

* [Databricks Free Edition](https://www.databricks.com/learn/free-edition)

Procurei deixar o código completamente comentado e de fácil modificação para facilitar a reprodução. Caso surja alguma dificuldade na execução, **entre em contato comigo** para solucionarmos o problema. O contato pode ser feito por e-mail: brunoraphaell99@gmail.com ou pelo WhatsApp informado no momento da inscrição da vaga.

## 1. Upload dos arquivos

Após a criação da conta no Databricks Free Edition e com o login efetuado, será necessário fazer o upload dos arquivos que serão utilizados no projeto. Abaixo está um passo a passo para realizar o upload no formato de volumes:

![](https://i.imgur.com/f6Fa1gz.png)

![](https://i.imgur.com/KkCJjBZ.png)

![](https://i.imgur.com/HDmjYGg.png)

Selecione onde você deseja salvar as bases de dados:  
![](https://i.imgur.com/IMfEN6A.png)

Após o upload dos arquivos, insira os respectivos *paths* nos notebooks.

## 2. Modificando os notebooks

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

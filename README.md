# Projeto Taurus

## Como executar localmente?

### Dependências
Para executar o projeto localmente, é necessário fazer a instalação das seguintes dependências:
- Python 3.x.x+ 
- Pip
- JMEter 5.x.x+
Para o JMEter, é necessário colocar no caminho C:/Users/<user>/.bzt/jmeter-taurus/<pasta_com_versao_jmeter>

### Instalação de dependências
Digitar o seguinte comando no terminal:
```
pip install btz
```

### Execução
Digitar o seguinte comando no terminal:
```
bzt example.yml
```

## Como executar com Docker?
Digitar o seguinte comando no terminal:
```
docker run --rm -v c//<path_to_your_scripts_directory>:/bzt-configs -v <path_to_your_artifacts_directory>:/tmp/artifacts blazemeter/taurus <script_name>.yml
```

## Como executar com Jenkins + Docker in Docker?

# Modelagem_BancoDeDados

Por: Vinicius dos Reis Savian

Ateliê 13

## Descrição do Projeto
&nbsp;&nbsp;&nbsp;&nbsp;Buscando soluncionar os desafios que a Dell possui no processo de treinamento dos funcionários, nós estamos desenvolvendo a aplicação web Dell Aware. Nesta aplicação, os engenheiros poderão direcionar os materias para os trabalhadores, mostrando para ele quais manuais são obrigatórios a leitura, além disso será possivel os engenheiros realizarem um acompanhamento do desempenho dos montadores.

## Modelo Relacional de Banco de Dados
&nbsp;&nbsp;&nbsp;&nbsp;Pensando em como seria possível desenvolver a solução, foi desenvolvido um modelo relacional de banco de dados no SQL Designer, uma plataforma web para o desenvolvimento de tabelas de bancos de dados, melhorando visualização da relação de cada componente dentro de um BdD.

&nbsp;&nbsp;&nbsp;&nbsp;E este foi o resultado:

<div align='center'>
<img src="/assets/image.png" alt='Modelo Relacional de Banco de Dados'>

<sub>Fonte: Material produzido pelo autor /(2024)</sub>
</div>

## Tabelas
O banco de dados possui 5 tabelas, e cada uma delas foi criada com um objetivo, segue a explicação dividida por tabela:

### Workers
É a tabela de cadastro dos montadores, onde você possui as principais informações sobre cada montador. A principal informação que será importante na delegação dos manuais é o id do funcionário, e será muito importante para o engenheiro identificar qual linha aquele montador faz parte.

### Engineers
É a tabela de cadastro dos engenheiros, onde você possui as principais informações sobre cada engenheiro, que será o responsável por realizar a delegação dos manuais.

### Manuals
É a tabela onde você possui as informações sobre cada manual, como a descrição e as categorias dele, ela está ligada diretamente com a tabela files que é onde iremos ter o update dos arquivos.

### Files
É a tabela que realizamos o update dos arquivos que serão disponibilizados em cada manual, podendo ter manuais com mais de um arquivo.

### Delegations
É a tabela principal, que possui um relacionamento terciário, fazendo conexão entre as tabelas de Workers, Engineers e Manuals. É ela a responsável pela realização das delegações dos manuais, assim você consegue ter o engenheiro X que delega para o funcionário Y o manual Z.

## Relações das Tabelas

Devemos identificar a relação entre cada tabela para saber como elas funcionam. A relação entre a tabela Workers e Delegations possui uma relação de muitos trabalhadores para uma delegação, ou seja é uma relação N-1.

A relação da tabela Engineers e Delegations segue o mesmo padrão da anterior, é uma relação de muitos engenheiros para uma delegação (N-1).

A relação entre Files e Manuals é de vários arquivos para um manual, sendo também uma relação de N-1.

Já a relação entre Manuals e Delegations é uma relação de vários manuais para várias delegações, ou seja é uma relação N-N.

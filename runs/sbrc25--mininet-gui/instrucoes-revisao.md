Seu objetivo como um revisor de artefato consiste em garantir que a qualidade do artefato corresponda com o conteúdo do artigo e os requisitos mínimos esperados para a obtenção de cada selo.
Para realizar esta atividade com excelência, antes de avaliar os artefatos **(i)** leia o artigo; e **(ii)** defina as principais contribuições do trabalho. Estas duas etapas tornam o processo de avaliação de cada selo mais simples.

> **Note**
> Observe que o período de revisão é relativamente curto. Recomendamos iniciar suas revisões assim que receber sua tarefa.

O processo de revisão pode ser realizado em um ambiente de sua preferência, desde que bata os requisitos mínimos do ambiente de execução esperado para o artefato. Recomendamos a execução dos artefatos (quando aplicável) em um ambiente virtual por trazer praticidade para os revisores e garantir que componentes presentes na sua máquina local não prejudiquem o processo de avaliação (um clean install em um ambiente novo pode reduzir imprevistos).

Caso recursos adicionais sejam necessários (infraestrutura de nuvem, chaves SSH, etc.) estas informações devem estar presentes no Apêndice do artefato.

Os artefatos em avaliação já são artigos aceitos pelo comitê técnico do SBRC'25. Desta forma, não há necessidade de avaliar sua solidez científica. No entanto, caso você encontre algum problema, relate entrando em contato com os coordenadores de avaliação de artefatos.

> **Note**
> Lembre-se de que todos os artefatos, análises e discussões são confidenciais

O processo de revisão está dividido em duas etapas. **Primeiramente**, você como revisor deve selecionar os trabalhos que possuem afeição/familiaridade com o assunto para o posterior processo de revisão. Faça a escolha de trabalhos o quanto antes para que o comitê tenha conhecimento das revisões de cada membro. Cada membro do CTA irá escolher 3 ou mais trabalhos para avaliar (número a ser confirmado pelos coordenadores posteriormente).

Após ter selecionado seus trabalhos, você já pode começar a realizar as revisões. Para orientar esta **segunda etapa**, um conjunto de instruções com pontos chaves do processo de avaliação de artefato foi definido pelo comitê, conforme consta nas definições de requisitos para a obtenção de cada selo.
Para que o artefato esteja apto a receber um selo, os respectivos requisitos devem ser satisfeitos.

Para que o trabalho/artefato seja apto a receber o selo, os respectivos requisitos devem ser alcançados:

É esperado que o código e/ou dados estejam **disponíveis em um repositório estável** (como GitHub e GitLab). Neste repositório é esperado encontrar um [README.md](https://github.com/matiassingers/awesome-readme) com os **requisitos mínimos do README.md**. Os requisitos mínimos do README.md sendo:

```

# Título projeto

Resumo descrevendo o objetivo do artefato, com o respectivo título e resumo do artigo.

# Estrutura do readme.md

Apresenta a estrutura do readme.md, descrevendo como o repositório está organizado.

# Selos Considerados

Os autores devem descrever quais selos devem ser considerados no processo de avaliação. Como por exemplo: ``Os selos considerados são: Disponíveis e Funcionais.''

# Informações básicas

Esta seção deve apresentar informações básicas de todos os componentes necessários para a execução e replicação dos experimentos.
Descrevendo todo o ambiente de execução, com requisitos de hardware e software.

# Dependências

Informações relacionadas a benchmarks utilizados e dependências para a execução devem ser descritas nesta seção.
Busque deixar o mais claro possível, apresentando informações como versões de dependências e processos para acessar recursos de terceiros caso necessário.

# Preocupações com segurança

Caso a execução do artefato ofereça algum tipo de risco para os avaliadores. Este risco deve ser descrito e o processo adequado para garantir a segurança dos revisores deve ser apresentado.

# Instalação

O processo de baixar e instalar a aplicação deve ser descrito nesta seção. Ao final deste processo já é esperado que a aplicação/benchmark/ferramenta consiga ser executada.

# Teste mínimo

Esta seção deve apresentar um passo a passo para a execução de um teste mínimo.
Um teste mínimo de execução permite que os revisores consigam observar algumas funcionalidades do artefato.
Este teste é útil para a identificação de problemas durante o processo de instalação.

# Experimentos

Esta seção deve descrever um passo a passo para a execução e obtenção dos resultados do artigo. Permitindo que os revisores consigam alcançar as reivindicações apresentadas no artigo.
Cada reivindicações deve ser apresentada em uma subseção, com detalhes de arquivos de configurações a serem alterados, comandos a serem executados, flags a serem utilizadas, tempo esperado de execução, expectativa de recursos a serem utilizados como 1GB RAM/Disk e resultado esperado.

Caso o processo para a reprodução de todos os experimento não seja possível em tempo viável. Os autores devem escolher as principais reivindicações apresentadas no artigo e apresentar o respectivo processo para reprodução.

## Reivindicações #X

## Reivindicações #Y

# LICENSE

Apresente a licença.
```

É esperado que o código e/ou artefato possa ser **executado** e o revisor consiga observar algumas de suas **funcionalidades**. Para adquirir este artefato, é importante que informações adicionais estejam presentes no README.md do repositório, como

1. lista de dependências;
2. lista de versões das dependências/linguagens/ambiente;
3. descrição do ambiente de execução;
4. instruções de instalação e execução;
5. um exemplo de execução mínima.

É esperado que o código e/ou **artefato esteja modularizado, organizado, inteligível e de fácil compreensão**. Para obter o selo é interessante que:

1. exista uma documentação mínima do código (descrevendo arquivos, funções,..);
2. legibilidade mínima de código;
3. permita que os avaliadores consigam identificar as principais reivindicações do artigo no artefato.

É esperado que o **revisor consiga reproduzir as principais reivindicações apresentadas no artigo**. Para obter este selo é esperado:

1. instrução para executar as principais reivindicações (e.g., resultados dos principais gráficos/tabelas);
2. descrição de um processo de como foram executados os experimentos para chegar até o resultado do artigo;

Para cada artefato, você deve produzir uma breve revisão justificando a razão por atribuir ou negar um selo ao artefato. Esta avaliação só deve ser completada após o processo de avaliação tenha sido realizado.

Para facilitar o processo de avaliação, um exemplos está disponível junto ao formulário de submissão.
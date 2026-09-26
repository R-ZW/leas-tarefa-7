# Avaliação de selos F e R para Mininet-GUI

**Data:** 26/09/2026  
**Provedor:** OpenAI  
**Modelo:** GPT-5.6 Sol (esforço médio)  
**Interface:** Codex Desktop  

## Usuário — Prompt 1: avaliação analítica

Atue como revisor de um artefato científico do SBRC 2025. Avalie somente os selos F e R, seguindo exatamente as instruções oficiais da edição.

**Artefato:** Mininet-GUI: Uma Abordagem Visual e Interativa para Experimentação em Redes SDN  
**Repositório:** https://github.com/latarc/mininet-gui  
**Instruções oficiais usadas:** `runs/sbrc25--mininet-gui/instrucoes-revisao.md`

Faça apenas uma avaliação analítica. Não execute comandos e não afirme que algo funcionou sem evidência de execução. Para cada selo:

1. liste os critérios oficiais aplicáveis;
2. indique Atribuir, Não atribuir ou Indeterminado;
3. apresente evidências verificáveis;
4. separe documentação de evidência de execução;
5. liste ausências, ambiguidades e limitações;
6. informe a confiança.

## Assistente — Avaliação analítica

### Materiais examinados

- `README.md`;
- `Dockerfile` e scripts de inicialização;
- `mininet-gui-backend/`, incluindo `requirements.txt` e os módulos Python;
- `mininet-gui-frontend/`, incluindo `package.json`, `package-lock.json` e componentes Vue;
- exemplos em `examples/`;
- licença BSD 3-Clause;
- instruções oficiais do SBRC 2025.

### Selo F — decisão analítica: Indeterminado

O README oferece três rotas de instalação (Docker, código-fonte e VM), descreve o ambiente principal e contém um teste mínimo de nove passos. O roteiro cobre inicialização, criação de controlador, geração de topologia, Pingall, WebShell e exportação.

Evidências favoráveis:

- `README.md > Requirements`: VirtualBox 7.1.6 e 8 GB de RAM para a VM;
- `README.md > Installation`: comandos para Docker, instalação nativa e importação da OVA;
- `README.md > Minimal test`: roteiro detalhado com resultado observável;
- código separado em frontend Vue e backend Python.

Limitações:

- o funcionamento real da VM, da GUI, do Mininet, do Open vSwitch e do Pingall depende de execução;
- `requirements.txt` não fixa versões;
- há divergência de RAM: 8 GB em Requirements e 2 GB em Experiments;
- a rota Docker depende de Linux, privilégios elevados, rede do host e Open vSwitch.

Como o requisito central do selo F exige execução e observação de funcionalidades, a documentação sozinha não permite concluir.

**Confiança:** média.

### Selo R — decisão analítica: Não atribuir

O README documenta apenas duas reivindicações:

- geração automática de topologias;
- terminal integrado via WebShell.

O artigo e a própria descrição do artefato incluem outras contribuições, como gerenciamento de regras OpenFlow, análise de pacotes, monitoramento e interação por IA. Não há procedimento experimental completo para reproduzir essas contribuições nem associação com resultados, tabelas ou métricas do artigo. As reivindicações documentadas também não informam claramente tempo esperado, consumo de recursos e resultado de referência.

**Confiança:** média.

## Usuário — Prompt 2: plano de execução

Forneça um plano fiel às instruções dos autores para testar o selo F e reproduzir as principais reivindicações do selo R. Identifique diretório, comando ou ação, resultado esperado, evidência a guardar, sucesso, falha, inconclusivo, dependências e pontos de interrupção. Não improvise correções não documentadas.

## Assistente — Plano de execução

### Teste mínimo — F

1. Preferir a VM disponibilizada pelos autores.
2. Importar `Mininet-GUI-VM.ova` no VirtualBox 7.1.6.
3. Alocar 8 GB de RAM conforme Requirements.
4. Iniciar a VM e autenticar com `mininet/mininet`.
5. Executar `mininet_gui` ou `/home/mininet/mininet-gui/scripts/run.sh`.
6. Abrir a URL exibida.
7. Criar controlador padrão `c1`.
8. Gerar topologia Single com dois hosts.
9. Executar Pingall e guardar captura dos resultados.
10. Exportar a topologia em JSON e como script Python.

### Reivindicações — R

1. Gerar topologias Single, Linear e Tree e registrar as estruturas apresentadas.
2. Abrir o WebShell de um nó e executar `ip a`.
3. Opcionalmente, executar `iperf -s` em `h1` e `iperf -c 10.0.0.1` em `h2`.
4. Registrar que as demais contribuições não possuem protocolo de reprodução completo no README.

## Usuário — Prompt 3: execução prática

Execute o que for viável no ambiente disponível. Não invente saídas e diferencie falha do artefato de limitação do ambiente.

## Assistente — Registro factual da execução

### Ambiente

- Windows, sem Docker, Mininet, Open vSwitch ou VirtualBox acessível;
- Node.js 24.19.0;
- npm 11.16.0;
- Python 3.14.6;
- repositório obtido do GitHub como arquivo ZIP da branch principal.

### Resultados observados

1. Inventário do repositório concluído: README, Dockerfile, scripts, frontend, backend, exemplos e licença estavam presentes.
2. `python -m compileall -q mininet-gui-backend`: concluído com código 0 (`PY_COMPILE_OK`).
3. `npm ci` no frontend: concluído; 143 pacotes instalados.
4. A auditoria do npm informou 18 vulnerabilidades: 8 moderadas, 8 altas e 2 críticas.
5. `npm run build`: chegou ao Vite, mas falhou porque o processo tentou ler diretórios fora da área autorizada do ambiente. O erro foi classificado como bloqueio do sandbox, não como falha comprovada do código.
6. A rota Docker não pôde ser executada porque o comando `docker` não está disponível.
7. O teste mínimo com GUI, Pingall, WebShell e exportação não pôde ser executado sem Linux/VM, Mininet e Open vSwitch.
8. As reivindicações do selo R não puderam ser reproduzidas integralmente.

## Assistente — Decisão após execução

### Selo F: Indeterminado

A execução confirmou que o backend é sintaticamente válido e que as dependências do frontend podem ser instaladas. Entretanto, não confirmou a funcionalidade central: inicialização da aplicação, criação de topologia, Pingall, WebShell e exportação. O bloqueio decorreu principalmente da ausência da infraestrutura exigida.

### Selo R: Não atribuir

A execução parcial não altera a conclusão analítica. Além de não ter sido possível rodar Mininet, o README continua sem um protocolo suficiente para reproduzir todas as principais contribuições e resultados do artigo.

## Resumo

| Selo | Analítica | Após execução | Relação |
|---|---|---|---|
| F | Indeterminado | Indeterminado | Confirma parcialmente; houve validação técnica parcial, mas não do teste mínimo |
| R | Não atribuir | Não atribuir | Confirma |

## Evidências principais

- `README.md`: Installation, Minimal test e Experiments;
- `mininet-gui-backend/requirements.txt`;
- `mininet-gui-frontend/package.json` e `package-lock.json`;
- saída de `python -m compileall`;
- saída de `npm ci` e `npm run build`;
- indisponibilidade de Docker/Mininet/VirtualBox no ambiente.

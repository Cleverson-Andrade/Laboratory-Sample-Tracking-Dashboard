# Laboratory Sample Tracking Intelligence 🧪

> Dashboard analítico para acompanhamento de recebimento de amostras laboratoriais, desenvolvido durante estágio na área de **Dados / SPR** de uma empresa global do agronegócio.

---

## O Problema

A área precisava acompanhar o recebimento de amostras laboratoriais a partir de informações distribuídas entre banco de dados corporativo e arquivos de referência mantidos em ambiente interno.

O processo de consulta e consolidação era dependente de extrações manuais, validações repetitivas e cruzamentos entre diferentes fontes. Isso dificultava a visualização rápida de volumes recebidos, status das amostras, responsáveis pelo recebimento e evolução temporal dos registros.

A ausência de uma camada analítica centralizada reduzia a agilidade no acompanhamento operacional e aumentava o risco de inconsistências nas análises.

---

## A Solução

Foi desenvolvido um dashboard analítico em **Streamlit** para centralizar a consulta, filtragem e visualização dos registros de recebimento de amostras.

A solução integra dados de banco PostgreSQL corporativo e arquivos de referência armazenados em ambiente colaborativo interno. A camada de processamento em Python realiza padronização de campos, tratamento de datas, criação de dimensões temporais e preparação dos dados para análise.

O projeto foi estruturado para permitir navegação interativa, uso de cache para otimizar performance e organização modular da camada de acesso aos dados.

---

## Visão Geral da Arquitetura

A solução segue uma arquitetura analítica simples e modular:

- fonte principal em banco de dados corporativo;
- fonte complementar em repositório interno de arquivos;
- camada de acesso aos dados;
- camada de tratamento e preparação;
- camada de cache para otimização;
- dashboard interativo para análise operacional.

O diagrama de arquitetura será mantido em arquivo separado na pasta `docs/`.

---

## Estrutura Conceitual do Projeto

| Camada | Responsabilidade |
|---|---|
| Data Access Layer | Centraliza consultas controladas ao banco de dados corporativo |
| External File Connector | Permite integração com arquivos de referência em ambiente interno |
| Data Processing Layer | Aplica tratamento de datas, limpeza de campos e criação de variáveis analíticas |
| Cache Layer | Reduz consultas repetidas durante a navegação no dashboard |
| Dashboard Layer | Disponibiliza filtros, indicadores, tabelas e visualizações interativas |
| Governance Layer | Mantém credenciais, dados reais e detalhes internos fora do repositório público |

---

## Stack Tecnológica

| Camada | Tecnologia |
|---|---|
| Interface | Streamlit |
| Processamento de dados | Python, pandas |
| Banco de dados | PostgreSQL |
| Conexão com banco | psycopg2 / SQLAlchemy |
| Integração com arquivos corporativos | Microsoft 365 / SharePoint connector |
| Autenticação e configuração | Variáveis de ambiente |
| Performance | Streamlit cache |
| Deploy | Ambiente interno corporativo |
| Versionamento | Git / GitHub |

---

## Funcionalidades

### Pipeline de Dados

- Consulta estruturada a registros de recebimento de amostras.
- Leitura de dados ativos e válidos a partir da fonte principal.
- Conversão de campos de data para tipos analíticos.
- Criação automática de dimensões temporais, como ano, mês e ano-mês.
- Padronização de campos textuais relevantes.
- Integração com arquivos corporativos de apoio.
- Uso de cache para reduzir consultas repetidas ao banco.
- Preparação de uma base analítica para consumo no dashboard.

---

## Dashboard Analítico

O dashboard foi pensado para apoiar o acompanhamento operacional e analítico do fluxo de recebimento de amostras.

| Área de Análise | Descrição |
|---|---|
| Visão Geral | Acompanhamento consolidado dos registros de recebimento |
| Volume Temporal | Evolução de amostras recebidas por período |
| Status dos Registros | Monitoramento de registros ativos e situação operacional |
| Responsáveis | Análise por responsável pelo recebimento |
| Detalhamento | Consulta tabular dos registros tratados |
| Filtros Dinâmicos | Segmentação por data, status e atributos operacionais |
| Exportação Analítica | Apoio à extração de dados tratados para análise complementar |

---

## Recursos de Análise

- Filtros por período.
- Filtros por status.
- Filtros por responsável.
- Análise de volume por mês.
- Visão tabular dos registros.
- Indicadores operacionais de acompanhamento.
- Cache para melhorar tempo de resposta.
- Preparação dos dados para análise exploratória e acompanhamento recorrente.

---

## Qualidade e Governança dos Dados

O projeto considera práticas de qualidade e governança importantes para ambientes corporativos:

- leitura controlada apenas de registros válidos;
- exclusão lógica respeitada na consulta;
- tratamento de campos de data;
- padronização de campos textuais;
- separação entre configuração, credenciais e lógica analítica;
- uso de variáveis de ambiente para dados sensíveis;
- não exposição de dados reais no repositório público;
- não versionamento de senhas, hosts internos ou caminhos corporativos.

Essas práticas reduzem riscos de inconsistência, melhoram a rastreabilidade das análises e preservam a segurança das informações corporativas.

---

## Impacto

- Centralizou o acompanhamento de recebimento de amostras em uma interface analítica.
- Reduziu a necessidade de consultas manuais ao banco de dados.
- Facilitou análises por período, status e responsável.
- Melhorou a visibilidade operacional do fluxo de amostras.
- Acelerou a preparação de dados para acompanhamento recorrente.
- Aplicou boas práticas de cache, modularização e separação de configurações.
- Contribuiu para maior padronização no monitoramento de dados laboratoriais.

---

## Organização do Repositório

Este repositório é documental e foi organizado para apresentar o projeto de forma pública, segura e profissional.

Arquivos planejados:

- `README.md`: visão geral do projeto;
- `requirements.txt`: bibliotecas utilizadas no ambiente original;
- `docs/architecture.md`: explicação da arquitetura e diagrama do projeto.

---

## Segurança e Privacidade

Este projeto foi desenvolvido em contexto corporativo. Por isso, o repositório público contém apenas documentação, arquitetura conceitual e descrição técnica em alto nível.

Não estão incluídos:

- código-fonte produtivo;
- credenciais;
- senhas;
- tokens;
- tenant IDs;
- hosts internos;
- nomes reais de servidores;
- caminhos internos de SharePoint;
- dados reais;
- arquivos CSV corporativos;
- tabelas internas;
- queries produtivas;
- prints de sistemas corporativos.

---

## Nota

> **Nota:** Este repositório contém apenas documentação e estrutura conceitual do projeto.  
> O código-fonte, dados, consultas produtivas e credenciais são proprietários e não estão incluídos.

---

## Autor

**Cleverson Moura**  
Estagiário em Data Science - SPR  

[linkedin.com/in/cleversonmandrade](https://www.linkedin.com/in/cleversonmandrade/)

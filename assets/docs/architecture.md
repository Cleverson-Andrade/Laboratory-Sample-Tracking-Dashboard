# Arquitetura do Projeto

Este documento apresenta a arquitetura conceitual do projeto **Laboratory Sample Tracking Intelligence**, desenvolvido para acompanhar o fluxo de amostras laboratoriais desde o planejamento até o recebimento e execução das análises.

A solução integra uma base de planejamento mantida em ambiente corporativo com registros operacionais do laboratório armazenados em banco de dados. O dashboard permite comparar o que estava planejado com o que foi recebido e quais análises já foram executadas, como ardido, umidade e PMS/peneira.

---

## Descrição do Diagrama

O fluxo começa no **planejamento das amostras**, mantido em uma base corporativa no SharePoint. Essa base contém identificadores e atributos operacionais das amostras esperadas, como código externo, barcode, número de repetição e cidade.

Quando as amostras chegam fisicamente ao laboratório, é realizado o registro de recebimento. Esse registro operacional é armazenado em banco de dados, permitindo identificar quais amostras planejadas já chegaram de fato ao laboratório.

Após o recebimento, as amostras passam pelas análises laboratoriais necessárias, como **ardido**, **umidade** e **PMS/peneira**. Os resultados ou status dessas análises também são armazenados em banco de dados.

A camada de integração cruza as informações de planejamento, recebimento e análises laboratoriais. O objetivo é construir uma visão única que mostre, para cada amostra, sua situação dentro do fluxo: planejada, recebida, pendente ou analisada.

Por fim, o dashboard em Streamlit apresenta essa visão de forma organizada, com indicadores, filtros e tabelas para acompanhamento operacional.

---

## Fluxo de Negócio Representado

1. A equipe mantém uma lista de amostras planejadas em ambiente corporativo.
2. Cada amostra planejada possui identificadores como barcode, external ID, repetição e cidade.
3. As amostras chegam fisicamente ao laboratório.
4. O laboratório registra a entrada das amostras recebidas.
5. Os registros de recebimento são armazenados em banco de dados.
6. As análises laboratoriais são executadas, incluindo ardido, umidade e PMS/peneira.
7. Os resultados e status das análises são registrados no banco.
8. A aplicação cruza o planejado com o recebido e com o que já foi analisado.
9. O dashboard mostra a situação consolidada das amostras para acompanhamento da equipe.

---

## Camadas da Solução

| Camada | Responsabilidade |
|---|---|
| Planejamento de Amostras | Mantém a lista de amostras esperadas, com identificadores e atributos operacionais |
| Recebimento no Laboratório | Registra a chegada física das amostras ao laboratório |
| Banco de Dados Operacional | Armazena registros de recebimento e status/resultados das análises laboratoriais |
| Análises Laboratoriais | Representa etapas como ardido, umidade e PMS/peneira |
| Integração e Tratamento | Cruza dados planejados, recebidos e analisados para criar uma visão consolidada |
| Base Analítica Unificada | Organiza a situação de cada amostra em uma base pronta para análise |
| Dashboard Streamlit | Disponibiliza KPIs, filtros, tabelas e acompanhamento visual do processo |
| Configuração Segura | Mantém credenciais, hosts, caminhos internos e informações sensíveis fora do GitHub |

---

## Principais Perguntas Respondidas pelo Dashboard

- Quais amostras estavam planejadas?
- Quais amostras já chegaram ao laboratório?
- Quais amostras ainda estão pendentes de recebimento?
- Quais amostras já possuem análise de ardido?
- Quais amostras já possuem análise de umidade?
- Quais amostras já possuem PMS/peneira registrado?
- Quais cidades, repetições ou grupos possuem maior volume de pendências?
- Qual é a evolução do recebimento e processamento das amostras ao longo do tempo?

---

## Indicadores Possíveis

| Indicador | Descrição |
|---|---|
| Amostras Planejadas | Total de amostras esperadas conforme base de planejamento |
| Amostras Recebidas | Total de amostras que deram entrada no laboratório |
| Pendentes de Recebimento | Amostras planejadas que ainda não possuem registro de entrada |
| Análises de Ardido Realizadas | Amostras recebidas com análise de ardido registrada |
| Análises de Umidade Realizadas | Amostras recebidas com análise de umidade registrada |
| PMS/Peneira Realizado | Amostras recebidas com avaliação de PMS/peneira registrada |
| Pendências Analíticas | Amostras recebidas que ainda não possuem todas as análises esperadas |
| Taxa de Conclusão | Percentual de amostras planejadas/recebidas que avançaram no fluxo analítico |

---

## Escopo Público do Diagrama

Este diagrama é uma representação conceitual e segura da arquitetura. Ele não expõe informações internas sensíveis.

Não são exibidos:

- nomes reais de servidores;
- hosts internos;
- credenciais;
- senhas;
- tokens;
- tenant IDs;
- caminhos reais de SharePoint;
- nomes reais de tabelas;
- queries produtivas;
- dados corporativos;
- arquivos internos.

O objetivo é demonstrar o fluxo analítico do projeto de forma profissional, mostrando como o dashboard conecta planejamento, recebimento e análises laboratoriais sem expor informações proprietárias.

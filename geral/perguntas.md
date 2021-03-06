# Perguntas

## Aula 1

1 - A entrega contínua visa diminuir o risco na hora do deploy do software. Para tal, a publicação do software deve ser:
- Na nuvem
- Conteinerizada
- __Granular__
> Alternativa correta! O tamanho importa. Deploys menores têm menos risco e são mais fáceis de entender quando dá algum problema.
- __Frequente__
> Alternativa correta! Implantações podem ser muito complexas e difíceis, e justamente por isso devemos repetí-las, para deixar o processo seguro e confiável. Isso também é conhecido como [Frequência reduz a dificuldade](https://martinfowler.com/bliki/FrequencyReducesDifficulty.html).
- __Automatizada__
> Alternativa correta! É essencial automatizar o máximo possível, desde a criação dos ambientes, instalação do software, configuração e execução dos testes.

2 - Qual é a diferença entre entrega contínua e deploy contínuo?
- A entrega contínua é totalmente automatizada, sem nenhuma aprovação humana, e o deploy contínuo depende de uma aprovação humana
- __No deploy contínuo, todas alterações entram em produção, sem nenhuma aprovação humana. A entrega contínua depende de uma aprovação humana__
> Alternativa correta! O importante é que, na entrega contínua, as alterações não entrem em produção automaticamente, pois existe um motivo de negócio (marketing, por exemplo). Tecnicamente, não existe nenhuma razão para reter alterações.
- Nenhuma, ambos são especializações da integração contínua

## Aula 2

1 - Das técnicas abaixo, quais representam a base da entrega contínua?
- Deploy contínuo
- __Testes contínuos__
> Alternativa correta! É essencial ter testes de vários níveis e totalmente automatizados, que executam a cada commit.
- Refatoração contínua
- __Integração contínua__
> Alternativa correta! Lembra-se da regra de ouro: sempre deve ter um master/trunk estável e os desenvolvedores devem comitar uma vez por dia no master/trunk.

2 - Na entrega contínua, quem é responsável pela entrega do software?
- A equipe de operações que cuida do monitoramento do sistema
- __Todos os envolvidos na criação e entrega de software__
> Alternativa correta! Todos os envolvidos, do analista e desenvolvedor até o DBA e operações, todos devem fazer parte da equipe de entrega, o delivery time.
- A responsabilidade está com o líder técnico da equipe
- O desenvolvedor que fez a alteração no código

## Aula 3

1 - Quais são as vantagens de usar deployment pipeline?
- Entrega otimizada através de ferramentas típicas do mundo DevOps
- Entrega versionada
- __Entrega confiável__
> Alternativa correta! As etapas são testes do nosso sistema, começando com testes simples e rápidos, até chegar aos testes mais sofisticado.
- __Feedback rápido__
> Alternativa correta! Cada etapa dá feedback para a equipe sobre a qualidade do software.

2 - Em que momento o pipeline começa a trabalhar?
- __A cada commit__
> Alternativa correta! Para cada commit novo devemos construir e testar o software!
- Só quando um desenvolvedor notifica o pipeline
- Normalmente à noite, quando poucos desenvolvedores estão ativos
- Normalmente a cada hora

3 - Os ambientes da pipeline devem ser:
- Reaproveitados
> 
- Containerizados
> 
- __Temporários__
> Alternativa correta! Idealmente, criamos todo o ambiente do zero, para não levar nenhuma "sujeira" de instalações e testes anteriores.
- __Iguais ou semelhantes ao ambiente de produção__
> Alternativa correta! Quanto mais semelhante o ambiente, mais garantias temos que o deploy vai funcionar e os testes vão dar feedback real.

4 - Qual é a ordem aconselhada das etapas de um pipeline de implantação?
- Unit Test --> Aceitação Automatizada --> Produção --> Homologação
- __Unit Test --> Aceitação Automatizada --> Homologação --> Produção__
> Alternativa correta! O importante é que os testes rápidos fique à esquerda, e que cada ambiente à direita se aproxime do ambiente de produção.
- Unit Test --> Homologação --> Aceitação Automatizada --> Produção
- Aceitação Automatizada --> Unit Test --> Homologação --> Produção

## Aula 4

1 - O que é executado no Commit Stage?
- __Testes unitários__
> Alternativa correta! Logo após o build, devemos executar os testes de unidade, pois são os mais rápidos (feedback!).
- __Análise de qualidade de código__
> Alternativa correta! Os relatórios de qualidade são gerados nessa etapa. Podem ser executados em paralelo aos testes de unidade.
- Teste de integração 
- __Build__
> Alternativa correta! O primeiro passo é buildar a aplicação.

2 - Assumindo que o build e os testes passaram, qual é o resultado do commit stage?
- __Plano de teste__
> Alternativa correta! Um plano de teste é relacionado com a equipe de Quality Assurance (QA) e não é um resultado do pipeline.
- __Relatórios de qualidade__
> Alternativa correta! O pipeline (servidor de construção) deve publicar os relatórios da análise de código junto com os testes de unidade.
- Pipeline como script
- __Um artefato de build__
> Alternativa correta! Isso pode ser um JAR, DLL, imagem Docker, GEM ou ZIP, dependendo da sua plataforma.

3 - O que é verdade sobre o stage de testes de aceitação automatizada?
- __Essa etapa é iniciado quando o commit stage foi executado com sucesso.__
> Alternativa correta! Quando executamos a primeira etapa com sucesso, automaticamente é chamado a etapa dos testes de aceitação automatizados.
- O ambiente pode ser totalmente diferente do ambiente de produção.
- Precisa de aprovação humana, normalmente alguém da equipe QA.
- __Nessa etapa é testado o sistema todo.__
> Alternativa correta! São testes baseados em requisitos, de alto nível (black box tests) e por isso muito valiosos.

## Aula 5

1 - Qual é o objetivo do ambiente de homologação?
- Executar testes de integração
- __Testar o deploy no ambiente igual ao de produção__
> Alternativa correta! Como o ambiente de homologação é igual (ou muito parecido) com o de produção, temos mais garantias que o deploy vai funcionar.
- __Dar feedback para a equipe sobre a aceitação e usabilidade do software__
> Alternativa correta! A equipe deve participar e aprender com o usuário.
- __Validar se o software atende as expectativas__
> Alternativa correta! Idealmente, o usuário final testa e valida o software.

2 - Qual boa prática identificamos quando abordamos os testes de carga?
- __Deve ter uma meta clara__
> Alternativa correta! É preciso saber qual métrica que estamos avaliando e aonde queremos chegar.
- Deve rodar em ambiente mais leve do que o de produção
- Deve ser executado pelos desenvolvedores

## Aula 6

1 - Quais atributos arquiteturais do software influenciam a entrega contínua?
- Usabilidade
- __Testabilidade__
> Alternativa correta! Todo pipeline é relacionado com testes e o feedback deles. Um software que é difícil de testar, ou não possui testes, já não atende a integração contínua, menos ainda a entrega contínua.
- __Deployabilidade__
> Alternativa correta! Esse atributo define a facilidade de implantar o software. Microsserviços, por exemplo, possuem vantagens aqui.
- Escalabilidade

2 - Por que separar o deploy do release?
- Para fazer A/B testing
- __Para diminuir o risco da entrega__
> Alternativa correta! São duas etapas diferentes que podem dar errado.
- __Para separar a decisão técnica (deploy) da decisão de negócio (release)__
> Alternativa correta! Podemos testar o deploy sempre, mas quando o negócio definir a publicação.

3 - Qual é a diferença entre Blue-Green Deploy e Canary Release?
- O Blue-Green sempre usa Feature Toggles, e o Canary não.
- No Blue-Green, apenas uma parte dos usuários usa o ambiente novo. No Canary todos os usuários usam o ambiente novo.
- __No Canary, apenas uma parte dos usuários usa o novo ambiente. No Blue-Green todos os usuários usam o ambiente novo.__
> Alternativa correta! No Canary Release, apenas uma parte dos usuários são direcionados para o novo ambiente. No Blue-Green todos os usuários vão ser direcionados para o ambiente novo.

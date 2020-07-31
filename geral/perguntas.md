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

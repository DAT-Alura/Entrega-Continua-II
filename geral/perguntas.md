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

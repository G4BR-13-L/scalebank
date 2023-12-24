# Documentação básica

## Meus objetivos
- Criar um mini banco
- Testar minhas habilidades com:
  - arquitetura
  - infraestrutura
  - Docker
  - RabbitMQ
  - Modelagem
  - Gradle
  - Spring
  - Postgres
- Tratar os dados com carinho
  - Scripts
  - Relatórios
  - Não perder dados
  - Gerar um data wharehouse
- Testes:
  - Implementar testes unitários
  - Criar pipelines do github 
  - Criar uma aplicação apra testes, injeção de dados, e estresse no ssistema

## Requisitos 

### ScaleBankV1
- Criar contas de usuário
- Cada Usuário possui uma conta
- Cada Conta guarda um saldo e uma lista de transações chamada "Extrato" ( List<Transacao> extrato )
- Cada conta possui um UUID, conhecido como chave PIX aleatória
- Todas as transações acontecem pelo tipo de transferência PIX
- As transações são assincronas. São gerados pedidos de transação com o estatus "PENDENTE" ( EstadoTransacaoEnum )
- Deve haver uma fila com um worker que processe as transações e altere seu estado para ( CONCLUIDO )
- Em caso de algum problema, deve ser atribuido um status de ( FALHO ), e deve ser preenchido um campo com a descrição da falha, para auditiorias.
- As transferencias por PIX podem ser agendadas
- 
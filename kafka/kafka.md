# Apache Kafka - Open Source

- Processar stream - dados/eventos

- Mensageria - receber stream, produz e na outra ponta consume.. fila de processamento

- First in - First out

- Assincrona

- Venda -> registra
  - publica stream -> topico (esteira que vai receber esses eventos) -> microservice realizar cobranca

- ferramentas do kafka
  - ksqlb - analise de vendas
  - kafka connect -> sincronizacao de dados, transferencia entre bancos de dados

- dois conceitos PUB/SUB
  - producer - sistema --- topico (esteira)
  - consumer - sistema

  - topico (esteira) com mais de um consumidor
    - particao
      - producer #1 consumer1
      - producer #2 consumer2
    - offset -> vai chegando msg 1 2 3 4 5 --from-beginning

# Exemplo

```
TOPICO - pagamento
producer     # 0 cancelamento -------- pagamento -------- consumer1
             # 1 -------- cancelamento -------- consumer2
             # 2 -------- pagamento -------- consumer3
             # 3 -------- pagamento -------- consumer4
```

- usar conceito de #key para ordenacao

  - producer - evento - pagamento - key: compra

  - producer - evento - cancelamento - key: compra

- consumer config
  - latest ---- #offset
  - earliest -- mais antigo
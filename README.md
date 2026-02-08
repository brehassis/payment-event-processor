# Payment Event Processor

Este projeto implementa um **processador de eventos de pagamento e transações**, com foco em **processamento assíncrono**, **idempotência**, **ordenação de eventos** e **resiliência a falhas**.

O sistema simula cenários comuns em plataformas financeiras e distribuídas, onde eventos relacionados a pagamentos chegam de forma **assíncrona**, **fora de ordem** ou **duplicados**, exigindo controle rigoroso de estado e consistência.

O objetivo principal é modelar e resolver problemas reais de engenharia enfrentados em sistemas orientados a eventos.

---

## Problema que o sistema resolve

Em sistemas financeiros modernos, pagamentos não são processados de forma linear ou síncrona. Eventos podem:

- chegar duplicados  
- chegar fora de ordem  
- falhar parcialmente  
- ser reprocessados  
- ser consumidos por múltiplos serviços  

Este projeto trata explicitamente esses desafios, garantindo que **cada transação seja processada de forma segura, consistente e previsível**, mesmo sob condições adversas.

---

## Principais desafios abordados

- Idempotência no consumo de eventos
- Garantia de processamento único (at-least-once vs exactly-once)
- Ordenação lógica de eventos relacionados à mesma transação
- Tratamento de falhas temporárias e reprocessamento
- Controle de concorrência e consistência de estado
- Observabilidade do fluxo de eventos

---

## O que este projeto é

- Um **processador de eventos financeiros** orientado a domínio
- Um estudo prático de **arquitetura orientada a eventos**
- Um exercício de **engenharia de sistemas distribuídos**
- Um exemplo de **tratamento explícito de falhas e concorrência**

---

## O que este projeto não é

- Um gateway de pagamento real
- Uma implementação específica de Kafka, RabbitMQ ou cloud provider
- Um sistema focado em interface gráfica ou UI

---

## Principais características

- Consumo assíncrono de eventos de pagamento
- Deduplicação de eventos baseada em identificadores únicos
- Processamento idempotente e seguro
- Controle explícito de estado das transações
- Simulação de falhas e retries controlados
- Separação clara entre domínio, aplicação e infraestrutura
- Testes focados em comportamento e cenários extremos

---

## Decisões arquiteturais

- Arquitetura orientada a eventos
- Processamento assíncrono como regra
- Idempotência como requisito fundamental
- Estado da transação tratado como entidade de domínio
- Infraestrutura desacoplada da lógica de negócio
- Código priorizando clareza, previsibilidade e auditabilidade

---

## Eventos modelados (exemplos)

- `PaymentRequested`
- `PaymentAuthorized`
- `PaymentConfirmed`
- `PaymentFailed`
- `PaymentRefunded`

Cada evento é tratado de forma independente, respeitando invariantes do domínio e o estado atual da transação.

---

## Público-alvo

Este projeto é voltado para:

- Engenheiros de software interessados em sistemas distribuídos
- Profissionais que trabalham com mensageria e eventos
- Times que lidam com pagamentos, antifraude ou billing
- Recrutadores técnicos que avaliam maturidade em arquitetura

---

## Status do projeto

🚧 **Em desenvolvimento contínuo**

O projeto evolui de forma incremental, priorizando robustez, testes e clareza de decisões técnicas.

---

## Consideração final

> Em sistemas distribuídos, falhas não são exceção — são parte do fluxo normal.  
> Este projeto existe para tratar falhas como cidadãs de primeira classe.

---

## Próximos passos

- Definir o modelo de domínio das transações
- Implementar fluxo básico de eventos
- Introduzir falhas simuladas e reprocessamento
- Evoluir para cenários concorrentes mais complexos

Este projeto faz parte de uma estratégia de portfólio focada em **engenharia real de sistemas críticos**, não em exemplos artificiais.

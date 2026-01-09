# Sistema de Automação de Atendimento 24/7 com n8n

Este projeto demonstra a implementação de um **sistema automatizado de atendimento ao cliente**, focado em reduzir custos operacionais e tempo de resposta, mantendo escalabilidade e possibilidade de intervenção humana quando necessário.

O fluxo foi projetado para empresas que recebem alto volume de mensagens e precisam **coletar dados, registrar clientes, classificar demandas e responder automaticamente**, operando 24/7.

---

## Problema Resolvido

Empresas que realizam atendimento manual via WhatsApp enfrentam:
- Alto custo operacional
- Respostas lentas fora do horário comercial
- Falta de padronização no atendimento
- Perda de dados fornecidos pelo cliente
- Dificuldade de escalar o atendimento

---

## Solução Proposta

Foi desenvolvido um **sistema de automação de atendimento**, utilizando **n8n como orquestrador**, capaz de:

- Receber mensagens via WhatsApp
- Filtrar e interpretar entradas do usuário (texto e áudio)
- Coletar e validar dados do cliente
- Armazenar informações em banco de dados
- Classificar o tipo de atendimento (urgente ou comum)
- Responder automaticamente ao cliente
- Escalar para atendimento humano quando necessário

---

## Funcionamento do Fluxo

1. **Recebimento da mensagem**
   - Mensagens são recebidas via Webhook conectado à Evolution API (WhatsApp).

2. **Filtragem e pré-processamento**
   - Identificação do tipo de mensagem (texto, áudio).
   - Conversão de áudio em texto quando necessário.

3. **Coleta e persistência de dados**
   - Informações fornecidas pelo cliente são armazenadas em banco de dados.
   - Caso o cliente ainda não exista, o cadastro é criado automaticamente.

4. **Gerenciamento de estado**
   - Redis é utilizado para controle de contexto, pausas e estados de conversa.
   - Evita respostas duplicadas e garante fluxo contínuo.

5. **Classificação do atendimento**
   - Diferencia atendimentos urgentes de demandas comuns.
   - Encaminha para humano quando necessário.

6. **Resposta automatizada**
   - Respostas são geradas e enviadas automaticamente ao cliente via WhatsApp.

---

## Arquitetura e Componentes

- **n8n**  
  Orquestração dos fluxos, decisões lógicas e integração entre serviços.

- **Evolution API**  
  Comunicação com WhatsApp (envio e recebimento de mensagens).

- **Redis**  
  Controle de estado da conversa, pausas e gerenciamento de contexto.

- **PostgreSQL**  
  Persistência de dados de clientes e histórico de atendimento.

- **Cloudflare**  
  Segurança, proxy e estabilidade da comunicação via Webhook.

---

## Tecnologias Utilizadas

- n8n  
- APIs REST  
- Evolution API  
- Redis  
- PostgreSQL  
- Cloudflare  
- Webhooks  
- JSON  

---

## Demonstração

Imagens do fluxo e do painel de integração:

- Workflow completo no n8n  
- Integração ativa com Evolution API  
- Processamento e resposta automática ao cliente  

![Fluxo geral do atendimento](images/workflown8n.png)

![Integração WhatsApp](images/whatsapp.png)

---

## Objetivo do Projeto

Este projeto foi desenvolvido para demonstrar:
- Capacidade de **automação de processos reais**
- Integração entre múltiplos serviços e APIs
- Pensamento arquitetural voltado à escalabilidade
- Organização de fluxo de atendimento corporativo
- Uso de ferramentas low-code de forma profissional

---

## Próximos Passos (Evolução)

- Integração com serviços externos via API intermediária em Python
- Normalização e validação avançada de dados
- Métricas de atendimento e logging
- Painel administrativo para acompanhamento

---

*Projeto desenvolvido como demonstração prática de automação de atendimento e integração de sistemas.*

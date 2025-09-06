# CP_NLP_ChatBot
ChatBot da Tchau provedora de internet

# 🤖 Chatbot de Suporte de Internet (Dialogflow ES)

**Disciplina:** Inteligência Artificial – CP1  
**Tema escolhido:** Suporte de Internet (Provedor Tchau)  
**Integrantes:**  
- Mizael Vieira - RM555796
- Lucas Ichiama - RM555077
- Santiago Bernardes - RM557447
- Jose Tavares - RM554471
- Cristiano Dias - RM555992
- Marcia Rosano - RM557464


---

## 🎯 Objetivo
Desenvolver um chatbot de atendimento no **Dialogflow ES** com, no mínimo, 5 fluxos distintos, utilizando intents, entities, parâmetros obrigatórios, fallback e encerramento adequado.  

---

## 📌 Fluxos implementados

### 1. Saudação e Identificação do Cliente  
- **Intent:** `saudacao_identificacao` / `Default Welcome Intent`  
- **Training Phrases:** oi, olá, bom dia, boa tarde, quero começar, etc.  
- **Entity usada:** `@sys.given-name` (nome do usuário).  
- **Resposta:**  
  - “Olá, $nome! Eu sou o assistente virtual do Provedor Tchau. Posso abrir um chamado, consultar o status, responder dúvidas rápidas ou transferir você para um atendente humano. Como posso te ajudar hoje?”  
- **Contextos:** cria `contexto_cliente` para armazenar o nome.  

---

### 2. Abrir Chamado  
- **Intent:** `abrir_chamado`  
- **Training Phrases:** estou sem internet, conexão lenta, problemas de sinal, etc.  
- **Entities usadas:**  
  - `@problema_internet` (personalizada)  
  - `@sys.address` (endereço do usuário).  
- **Resposta:**  
  - “Obrigado, $nome. Abrimos seu chamado nº 123 para o problema de $problema no endereço $endereco. Nossa equipe entrará em contato em breve.”  
- **Contextos:** gera `chamado_aberto` (guarda problema e endereço).  

---

### 3. Consultar Status  
- **Intent:** `consultar_status`  
- **Training Phrases:** status, consultar protocolo, qual a previsão do chamado, quero acompanhar, etc.  
- **Entity usada:** `@sys.number` (protocolo).  
- **Resposta:**  
  - “$nome, o chamado $protocolo está em andamento. Previsão de resolução em até 24 horas.”  
- **Contextos:** herda `contexto_cliente` e pode acessar `chamado_aberto` se disponível.  

---

### 4. FAQ / Informações rápidas  
- **Intent:** `faq_informacoes`  
- **Training Phrases:** qual horário de atendimento, atendem aos finais de semana, quero contratar um plano, instalação nova, etc.  
- **Resposta única estruturada:**  <br>

Para mais informações e serviços, entre em contato com nosso atendimento humano pelo telefone +55 11 1234-5678.

👉 Para contratação de novos planos, digite a opção 1.<br>
👉 Para suporte técnico e acompanhamento de chamados, digite a opção 2.<br>
👉 Para cancelamento de planos, digite a opção 3.<br>


---

---

### 5. Encerramento Simples  
- **Intent:** `encerramento_simples`  
- **Training Phrases:** obrigado, valeu, encerrar, finalizar, tchau, até mais.  
- **Resposta:**  
- “Atendimento encerrado com sucesso, $nome. Obrigado pelo contato e até a próxima!”  

---

### 6. Encaminhar Humano  
- **Intent:** `encaminhar_humano`  
- **Training Phrases:** quero falar com atendente, humano, transferir, falar com alguém de verdade.  
- **Resposta:**  
- “Certo, $nome, vou transferir você para um de nossos atendentes humanos. Aguarde um instante.”  

---

### 7. Cancelar Chamado *(fluxo extra, opcional)*  
- **Intent:** `cancelar_chamado`  
- **Training Phrases:** cancelar chamado, cancelar protocolo 123, encerrar atendimento, não preciso mais de suporte.  
- **Entity usada:** `@sys.number` (protocolo).  
- **Resposta:**  
- “$nome, o chamado $protocolo foi cancelado com sucesso. Se precisar, pode abrir um novo chamado a qualquer momento.”  

---

### 8. Fallback  
- **Intent:** `Default Fallback Intent`  
- **Resposta:**  
- “Desculpe, não entendi o que você quis dizer. Posso abrir um chamado, consultar status ou responder dúvidas rápidas.”  

---

## 📎 Links de entrega
- **Web Demo (Dialogflow):** [https://bot.dialogflow.com/9a8a5f5d-c8d1-41d3-95bb-302689396d5a](https://console.dialogflow.com/api-client/demo/embedded/9a8a5f5d-c8d1-41d3-95bb-302689396d5a)
- **Telegram:** https://t.me/assistentetchaubot  


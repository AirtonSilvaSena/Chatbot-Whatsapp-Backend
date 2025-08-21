# 📌 WhatsApp Chatbot - Backend

Backend do Chatbot para WhatsApp, responsável por gerenciar interações automáticas com usuários, armazenar estado da conversa e integrar-se aos endpoints de consultas já existentes.

---

## 🔎 Sobre o Projeto

Este chatbot ajuda clínicas a automatizar a comunicação com pacientes via WhatsApp.  
Ele controla o **estado da conversa** para saber se o paciente está confirmando, reagendando ou cancelando uma consulta.  

Toda a lógica é baseada em **fluxos de estados**, garantindo uma experiência conversacional fluida e contextualizada.

---

## ✨ Funcionalidades

- **Integração oficial com WhatsApp (API Meta)**  
- **Gerenciamento de Estado da Conversa** (menu, aguardando confirmação, reagendamento, cancelamento)  
- **Conexão com Endpoints de Consultas existentes** (listar, confirmar, reagendar, cancelar)  
- **Persistência em banco** (usuário + conversa)  
- **Mensagens dinâmicas** conforme o contexto do paciente  

---

## ⚙️ Tecnologias

- **Node.js 18+** (com `fetch` nativo)  
- **Express.js** – Servidor HTTP  
- **PostgreSQL / MySQL** – Banco relacional  
- **Sequelize ou Prisma** – ORM  
- **dotenv** – Variáveis de ambiente  

---

## 📂 Estrutura do Projeto
```text
/src
 ├─ config/              
 │   └─ db.js              # Conexão com banco
 │   └─ whatsapp.js        # Config API Meta
 │
 ├─ controllers/         
 │   └─ whatsapp.controller.js   # Webhook de entrada
 │
 ├─ models/              
 │   └─ usuario.js
 │   └─ conversa.js        # Estado da conversa
 │
 ├─ services/            
 │   └─ whatsapp.service.js      # Envio de mensagens p/ API Meta
 │   └─ consulta.service.js      # Consome endpoints de consulta
 │   └─ conversa.service.js      # Persistência do estado
 │   └─ fluxo.service.js         # Lógica da conversa
 │
 ├─ utils/               
 │   └─ messageBuilder.js        # Helpers p/ montar mensagens
 │
 ├─ routes/              
 │   └─ whatsapp.routes.js
 │
 ├─ app.js
 └─ server.js

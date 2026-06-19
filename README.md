# 📌 AnsioTrack - Monitoramento de Ansiedade

## 🎯 Objetivo
Permitir que os usuários registrem crises de ansiedade, acompanhem padrões de comportamento e gerem relatórios para acompanhamento psicológico.

---

## 🧠 Problema
Muitas pessoas chegam à consulta psicológica sem conseguir responder perguntas como:

- Quantas crises tiveram?
- Em quais horários ocorrem?
- Qual a intensidade?
- Quais sintomas sentiram?
- O que desencadeou a crise?

O AnsioTrack centraliza essas informações para facilitar o acompanhamento.

---

## 👥 Público-alvo
- Pessoas com ansiedade  
- Pacientes em terapia  
- Psicólogos (através de relatórios)  
- Pessoas que desejam monitorar sua saúde emocional  

---

## 🚀 MVP (Versão Inicial)

### 🔐 Tela 1 - Login
**Campos:**
- E-mail  
- Senha  

**Botões:**
- Entrar  
- Criar conta  

---

### 📊 Tela 2 - Dashboard
**Informações exibidas:**
- Crises registradas hoje  
- Média semanal  
- Nível emocional atual  
- Última crise registrada  

**Botões:**
- ➕ Registrar crise  
- 😊 Registrar humor  
- 📄 Gerar relatório  

---

### ➕ Tela 3 - Registrar Crise

**Campos:**
- Data/Hora (automático)  
- Nível da ansiedade (0 a 10)  

**Sintomas:**
- Coração acelerado  
- Tremores  
- Falta de ar  
- Náusea  
- Tontura  
- Dor no peito  
- Choro  
- Insônia  

**Emoções:**
- Medo  
- Tristeza  
- Raiva  
- Angústia  
- Culpa  
- Insegurança  

**Outros campos:**
- Gatilho (o que aconteceu antes da crise)  
- Duração (minutos)  
- Observações  

---

### 😊 Tela 4 - Registro de Humor

**Pergunta:** Como você está se sentindo agora?

- 😄 Excelente  
- 🙂 Bem  
- 😐 Neutro  
- 😔 Triste  
- 😣 Muito mal  

**Campos adicionais:**
- Nível de energia (0 a 10)  
- Nível de estresse (0 a 10)  

---

## 📄 Relatórios

### 📊 Relatório Semanal
- Quantidade de crises  
- Média de intensidade  
- Sintomas mais frequentes  
- Horários críticos  
- Principais gatilhos  

---

### 📊 Relatório Mensal
Exemplo:
- Janeiro: 15 crises  
- Intensidade média: 7,2  
- Horário mais comum: 19h às 21h  
- Principais gatilhos: trabalho  

---

## 🗄️ Banco de Dados

### 👤 Tabela usuários
```sql
CREATE TABLE usuarios (
  id INT PRIMARY KEY AUTO_INCREMENT,
  nome VARCHAR(100),
  email VARCHAR(150),
  senha VARCHAR(255),
  dados_cadastro DATETIME
);

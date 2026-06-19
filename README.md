AnsioTrack - Monitoramento de Ansiedade
Objetivo
Permitir que usuários registrem crises de ansiedade, acompanhem padrões de comportamento e gerem relatórios para acompanhamento psicológico.
Problema
Muitas pessoas chegam à consulta psicológica sem conseguir responder perguntas como:
Quantas crises tiveram?
Em quais horários?
Qual a intensidade?
Quais sintomas sentiram?
O que desencadeou a crise?
O AnsioTrack centraliza essas informações para facilitar o acompanhamento.
Público-alvo
Pessoas com ansiedade
Pacientes em terapia
Psicólogos (através dos relatórios)
Pessoas que desejam monitorar sua saúde emocional

MVP (Versão Inicial)
Tela 1 - Login
Campos:
E-mail
Senha
Botões:
Entrar
Criar conta

Tela 2 - Dashboard
Informações exibidas:
📊 Crises registradas hoje
📊 Média semanal
📊 Nível emocional atual
📊 Última crise registrada
Botões:
➕ Registrar crise
😊 Registrar humor
📄 Gerar relatório
Tela 3 - Registrar Crise
Campos
Data/Hora
 (preenchido automaticamente)
Nível da ansiedade
Escala:
0 = Nenhuma ansiedade
10 = Crise extrema
Sintomas:
☐ Coração acelerado
☐ Tremores
☐ Falta de ar
☐ Náusea
☐ Tontura
☐ Dor no peito
☐ Choro
☐ Insônia
Emoções:
☐ Medo
☐ Tristeza
☐ Raiva
☐ Angústia
☐ Culpa
☐ Insegurança
Gatilho
Campo texto:
"O que aconteceu antes da crise?"
Duração
Minutos
Observações
Campo livre
Botão:
Salvar
Tela 4 - Registro de Humor
Pergunta:
"Como você está se sentindo agora?"
Escala:
😄 Excelente
🙂 Bem
😐 Neutro
😔 Triste
😣 Muito mal
Pergunta:
"Nível de energia?"
0 a 10
Pergunta:
"Nível de estresse?"
0 a 10

Relatórios
Relatório Semanal
Exibir:
Quantidade de crises
Média de intensidade
Sintomas mais frequentes
Horários críticos
Principais gatilhos
Relatório Mensal
Exemplo:
Janeiro:
15 crises
Intensidade média 7,2
Horário mais comum: 19h às 21h
Principal gatilho: Trabalho
Banco de Dados
Tabela usuários
CREATE TABLE usuarios (
   id INT PRIMARY KEY AUTO_INCREMENT,
   nome VARCHAR(100),
   email VARCHAR(150),
   senha VARCHAR(255),
   data_cadastro DATETIME
);
Tabela crises
CREATE TABLE crises (
   id INT PRIMARY KEY AUTO_INCREMENT,
   usuario_id INT,
   data_hora DATETIME,
   intensidade INT,
   gatilho TEXT,
   duracao_minutos INT,
   observacoes TEXT,
   FOREIGN KEY(usuario_id)
   REFERENCES usuarios(id)
);
Tabela sintomas
CREATE TABLE sintomas (
   id INT PRIMARY KEY AUTO_INCREMENT,
   nome VARCHAR(100)
);
Tabela crise_sintomas
CREATE TABLE crise_sintomas (
   crise_id INT,
   sintoma_id INT,
   FOREIGN KEY(crise_id)
   REFERENCES crises(id),
   FOREIGN KEY(sintoma_id)
   REFERENCES sintomas(id)
);

Tabela humor
CREATE TABLE humor (
   id INT PRIMARY KEY AUTO_INCREMENT,
   usuario_id INT,
   data_hora DATETIME,
   humor VARCHAR(50),
   energia INT,
   estresse INT,
   observacao TEXT,
   FOREIGN KEY(usuario_id)
   REFERENCES usuarios(id)
);
Casos de Uso
UC01 - Registrar Crise
Ator:
 Usuário
Fluxo:
Acessa sistema
Clica em Registrar Crise
Preenche formulário
Salva registro
Sistema grava dados
Resultado:
 Crise registrada com sucesso.
UC02 - Registrar Humor
Ator:
 Usuário
Fluxo:
Acessar tela de humor
Informa estado emocional
Salva
Resultado:
 Humor registrado.
UC03 - Gerar Relatório
Ator:
 Usuário
Fluxo:
Seleciona período
Clica em gerar relatório
Sistema calcula métricas
PDF é gerado
Resultado:
 Relatório disponível para download.
Casos de Teste QA
CT001 - Registrar crise válida
Pré-condição:
 Usuário logado
Passos:
Abrir formulário
Preencher todos os campos
Salvar
Resultado esperado:
 Registro salvo com sucesso.
CT002 - Intensidade inválida
Passos:
Informar intensidade 15
Resultado esperado:
 Sistema impede salvamento.
CT003 - Gerar relatório
Passos:
Selecionar mês
Gerar PDF
Resultado esperado:
 PDF criado sem erros.
Tecnologias
Front-end
HTML
CSS
JavaScript
React
Back-end
Node.js
Express
Banco
MySQL
Versionamento
Git
GitHub



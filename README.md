# Teste Prático - Backend Node.js (Logs de Acesso)

## Objetivo

Criar uma API para gerenciar logs de acesso ao sistema. Esta API será usada para registrar, listar e filtrar logs de usuários.

---

## Funcionalidades

1. **Registrar Log de Acesso**:
   - Endpoint: `POST /logs`
   - Receber os campos `user` e `action` no corpo da requisição.
   - Salvar o log no mysql.

2. **Listar Logs de Acesso**:
   - Endpoint: `GET /logs`
   - Retornar todos os logs armazenados.

3. **Filtrar Logs por Data e Usuário** (Opcional):
   - Endpoint: `GET /logs?user=<user>&date=<date>`
   - Retornar apenas os logs filtrados.

---

## Configuração

1. Clone este repositório:
   ```bash
   git clone https://github.com/GeekBoyBiel/backend-test.git
   cd backend-test

   Mude para a sua branch de trabalho:
   git checkout Seu_Nome_Completo

2. Configure o acesso ao BD
   Usuário: Seu_Nome_Completo
   Seu_Nome_123


### Banco de Dados: `Test`

### Tabelas Necessárias:

1. **Tabela `users`**:
   - Armazena informações dos usuários do sistema.
   ```sql
   CREATE TABLE users (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(255) NOT NULL,
     email VARCHAR(255) NOT NULL UNIQUE,
     status TINYINT(1) DEFAULT 1,
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );

2. **Tabela `actions`**:
   - Armazena os tipos de ações realizadas no sistema.
   ```sql
   CREATE TABLE actions (
   id INT AUTO_INCREMENT PRIMARY KEY,
   name VARCHAR(255) NOT NULL UNIQUE,
   created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );

3. **Tabela  `logs`**:
   - Registra os logs de acesso, associando usuários e ações.
   ```sql
   CREATE TABLE logs (
  id INT AUTO_INCREMENT PRIMARY KEY,
  user_id INT NOT NULL,
  action_id INT NOT NULL,
  ip_address VARCHAR(45),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
  FOREIGN KEY (action_id) REFERENCES actions(id) ON DELETE CASCADE
   );



### Observações:

 - Você tem 45 minutos para concluir o teste.

### Critérios de Avaliação:
- Os endpoints devem funcionar corretamente de acordo com o solicitado.
- Organização do Código:
- Utilização do padrão MVC (Models, Controllers e Routes).
- Código limpo e bem estruturado.
- Mensagens claras para erros (ex.: dados faltantes, usuário não encontrado).
- Uso de códigos HTTP apropriados.
- Verifique se os campos obrigatórios estão preenchidos (user, action).
- Valide dados de entrada (ex.: formato do email ou ID do usuário).
- Clareza nos nomes de variáveis e funções.
- Comentários claros, se necessário.
- Evitar duplicação de código.
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

## Documentação Resumida da API para Aplicativo de Triagem Médica por IA (Estilo Banco)

**Entidades:**

* **Paciente:**
    * Nome
    * Data de Nascimento
    * Sexo
    * Histórico Médico (opcional)
    * Sintomas Atuais
    * Sinais Vitais

**Rotas:**

**1. Contas de Pacientes (Geral)**

* **GET /pacientes:**
    * Retorna lista de pacientes
* **POST /pacientes:**
    * Cria um novo paciente
    * **Corpo da requisição:**
        * Nome
        * Data de Nascimento
        * Sexo
* **PUT /pacientes/{id}:**
    * Atualiza um paciente existente
    * **Corpo da requisição:**
        * Nome (opcional)
        * Data de Nascimento (opcional)
        * Sexo (opcional)
* **DELETE /pacientes/{id}:**
    * Remove um paciente

**2. Dados do Paciente (Histórico e Sintomas)**

* **GET /pacientes/{id}/dados:**
    * Obtém os dados de um paciente específico
* **POST /pacientes/{id}/dados:**
    * Cria novos dados para um paciente
    * **Corpo da requisição:**
        * Histórico Médico (opcional)
        * Sintomas Atuais
        * Sinais Vitais

**3. Triagem e Recomendações**

* **POST /pacientes/{id}/triagem:**
    * Realiza a triagem de um paciente e retorna as recomendações
    * **Corpo da requisição:**
        * Sintomas Atuais
        * Sinais Vitais
    * **Retorno:**
        * Recomendação (consulta presencial, online, encaminhamento)
        * Nível de Gravidade
        * Motivo da Triagem
        * Dados Adicionais
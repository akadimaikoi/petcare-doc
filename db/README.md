# Sistema de agendamento de alimentação de gatos.

## Base de Dados

### Tabelas da Base de Dados:

1. **Usuários**:
   - `id` (Chave Primária)
   - `nome`
   - `email`
   - `senha` (hash)
   - Outros campos relevantes para autenticação e perfil do usuário

2. **Gatos**:
   - `id` (Chave Primária)
   - `nome`
   - `idade`
   - `preferencias_alimentares`
   - `foto` (armazenar o caminho para a foto do gato)
   - `id_responsavel` (Chave Estrangeira para a tabela de Usuários)

3. **Horários de Alimentação**:
   - `id` (Chave Primária)
   - `data` e `hora` (ou um único campo datetime, dependendo da preferência)
   - `id_gato` (Chave Estrangeira para a tabela de Gatos)
   - `id_responsavel` (Chave Estrangeira para a tabela de Usuários)


### Relacionamentos:

- Um usuário pode ser responsável por zero ou mais gatos.
- Um gato pertence a um único usuário.
- Um gato pode ter zero ou mais horários de alimentação agendados.
- Um horário de alimentação está associado a um único gato e um único usuário responsável.


### Diagrama de Relacionamento de Entidades (ERD):

```
Usuários
---------
id (PK)
nome
email
senha
...

Gatos
---------
id (PK)
nome
idade
preferencias_alimentares
foto
id_responsavel (FK Usuários)

Horários_Alimentação
---------
id (PK)
data_hora
id_gato (FK Gatos)
id_responsavel (FK Usuários)
```

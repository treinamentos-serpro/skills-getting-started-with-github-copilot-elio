# API de Atividades da Mergington High School

Uma aplicação FastAPI bem simples que permite às pessoas estudantes visualizar e se inscrever em atividades extracurriculares.

## Funcionalidades

- Visualizar todas as atividades extracurriculares disponíveis
- Inscrever-se em atividades

## Primeiros passos

1. Crie e ative um ambiente virtual:

   ```
   python -m venv .venv
   source .venv/bin/activate
   ```

2. Instale as dependências no ambiente ativo:

   ```
   python -m pip install -r requirements.txt
   ```

3. Execute a aplicação:

   ```
   python app.py
   ```

3. Abra seu navegador e acesse:
   - Documentação da API: http://localhost:8000/docs
   - Documentação alternativa: http://localhost:8000/redoc

## Endpoints da API

| Método | Endpoint                                                          | Descrição                                                              |
| ------ | ----------------------------------------------------------------- | ---------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Retorna todas as atividades com seus detalhes e o número atual de participantes |
| POST   | `/activities/{activity_name}/signup?email=student@mergington.edu` | Inscreve em uma atividade                                              |
| DELETE | `/activities/{activity_name}/signup?email=student@mergington.edu` | Cancela a inscrição em uma atividade                                   |

## Modelo de dados

A aplicação usa um modelo de dados simples, com identificadores significativos:

1. **Activities** — usa o nome da atividade como identificador:

   - Descrição
   - Horário
   - Número máximo de participantes permitido
   - Lista de e-mails das pessoas estudantes inscritas

2. **Students** — usa o e-mail como identificador:
   - Nome
   - Ano escolar

Todos os dados são armazenados em memória, o que significa que serão reiniciados quando o servidor for reiniciado.

## Testes

Com o ambiente virtual ativado, execute a suíte de testes de backend a partir da raiz do repositório:

```bash
python -m pytest -q
```

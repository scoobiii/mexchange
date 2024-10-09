mexchange/create_mexchange.sh
#!/bin/bash

# Nome do Arquivo: create_mexchange.sh
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

# Cria as pastas
mkdir -p mexchange/mexchange_api/migrations/versions
mkdir -p mexchange/mexchange_api/tests
mkdir -p mexchange/mexchange_api/api
mkdir -p mexchange/mexchange_front/src/components
mkdir -p mexchange/mexchange_front/public

# Cria os arquivos
touch mexchange/mexchange_api/models.py
touch mexchange/mexchange_api/config.py
touch mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
touch mexchange/mexchange_api/migrations/alembic.ini
touch mexchange/mexchange_api/tests/test_schemas.py
touch mexchange/mexchange_api/api/schemas.py
touch mexchange/mexchange_api/main.py
touch mexchange/mexchange_front/public/index.html
touch mexchange/mexchange_front/src/components/MintForm.js
touch mexchange/mexchange_front/src/components/MintCost.js
touch mexchange/mexchange_front/src/App.js
touch mexchange/mexchange_front/src/index.js
touch mexchange/mexchange_front/src/App.css
touch mexchange/mexchange_front/package.json
touch mexchange/mexchange_front/.env
touch mexchange/create_mexchange.sh
touch mexchange/requirements.txt
touch mexchange/docker-compose.yml

# Adiciona cabeçalhos aos arquivos

# mexchange/mexchange_api/models.py
echo "# Nome do Arquivo: models.py" >> mexchange/mexchange_api/models.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/models.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/models.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/models.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/models.py

# mexchange/mexchange_api/config.py
echo "# Nome do Arquivo: config.py" >> mexchange/mexchange_api/config.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/config.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/config.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/config.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/config.py

# mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Nome do Arquivo: 000000000000_create_tables.py" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py

# mexchange/mexchange_api/migrations/alembic.ini
echo "# Nome do Arquivo: alembic.ini" >> mexchange/mexchange_api/migrations/alembic.ini
echo "# Versão: 1.0" >> mexchange/mexchange_api/migrations/alembic.ini
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/migrations/alembic.ini
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/migrations/alembic.ini
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/migrations/alembic.ini

# mexchange/mexchange_api/tests/test_schemas.py
echo "# Nome do Arquivo: test_schemas.py" >> mexchange/mexchange_api/tests/test_schemas.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/tests/test_schemas.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/tests/test_schemas.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/tests/test_schemas.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/tests/test_schemas.py

# mexchange/mexchange_api/api/schemas.py
echo "# Nome do Arquivo: schemas.py" >> mexchange/mexchange_api/api/schemas.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/api/schemas.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/api/schemas.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/api/schemas.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/api/schemas.py

# mexchange/mexchange_api/main.py
echo "# Nome do Arquivo: main.py" >> mexchange/mexchange_api/main.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/main.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/main.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/main.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/main.py

# mexchange/mexchange_front/public/index.html
echo "# Nome do Arquivo: index.html" >> mexchange/mexchange_front/public/index.html
echo "# Versão: 1.0" >> mexchange/mexchange_front/public/index.html
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/public/index.html
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/public/index.html
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/public/index.html

# mexchange/mexchange_front/src/components/MintForm.js
echo "# Nome do Arquivo: MintForm.js" >> mexchange/mexchange_front/src/components/MintForm.js
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/components/MintForm.js
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/components/MintForm.js
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/components/MintForm.js
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/components/MintForm.js

# mexchange/mexchange_front/src/components/MintCost.js
echo "# Nome do Arquivo: MintCost.js" >> mexchange/mexchange_front/src/components/MintCost.js
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/components/MintCost.js
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/components/MintCost.js
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/components/MintCost.js
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/components/MintCost.js

# mexchange/mexchange_front/src/App.js
echo "# Nome do Arquivo: App.js" >> mexchange/mexchange_front/src/App.js
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/App.js
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/App.js
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/App.js
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/App.js

# mexchange/mexchange_front/src/index.js
echo "# Nome do Arquivo: index.js" >> mexchange/mexchange_front/src/index.js
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/index.js
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/index.js
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/index.js
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/index.js

# mexchange/mexchange_front/src/App.css
echo "# Nome do Arquivo: App.css" >> mexchange/mexchange_front/src/App.css
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/App.css
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/App.css
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/App.css
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/App.css

# mexchange/mexchange_front/package.json
echo "# Nome do Arquivo: package.json" >> mexchange/mexchange_front/package.json
echo "# Versão: 1.0" >> mexchange/mexchange_front/package.json
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/package.json
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/package.json
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/package.json

# mexchange/mexchange_front/.env
echo "# Nome do Arquivo: .env" >> mexchange/mexchange_front/.env
echo "# Versão: 1.0" >> mexchange/mexchange_front/.env
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/.env
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/.env
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/.env

# mexchange/create_mexchange.sh
echo "# Nome do Arquivo: create_mexchange.sh" >> mexchange/create_mexchange.sh
echo "# Versão: 1.0" >> mexchange/create_mexchange.sh
echo "# Contrato: API Mexchange" >> mexchange/create_mexchange.sh
echo "# Data: 09/10/2024" >> mexchange/create_mexchange.sh
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/create_mexchange.sh

# mexchange/requirements.txt
echo "# Nome do Arquivo: requirements.txt" >> mexchange/requirements.txt
echo "# Versão: 1.0" >> mexchange/requirements.txt
echo "# Contrato: API Mexchange" >> mexchange/requirements.txt
echo "# Data: 09/10/2024" >> mexchange/requirements.txt
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/requirements.txt

# mexchange/docker-compose.yml
echo "# Nome do Arquivo: docker-compose.yml" >> mexchange/docker-compose.yml
echo "# Versão: 1.0" >> mexchange/docker-compose.yml
echo "# Contrato: API Mexchange" >> mexchange/docker-compose.yml
echo "# Data: 09/10/2024" >> mexchange/docker-compose.yml
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/docker-compose.yml

echo " " >> mexchange/create_mexchange.sh
content_copy
Use code with caution.
Bash
mexchange/requirements.txt
# Nome do Arquivo: requirements.txt
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

fastapi
uvicorn
graphene
graphene-sqlalchemy
sqlalchemy
alembic
psycopg2-binary
python-dotenv
requests
web3
solcx
pytest
content_copy
Use code with caution.
mexchange/docker-compose.yml
# Nome do Arquivo: docker-compose.yml
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

version: "3.8"
services:
  mexchange_api:
    build: .
    ports:
      - "8000:8000"
    volumes:
      - .:/app
    environment:
      - DATABASE_URL=postgresql://postgres:postgres@postgres:5432/mexchange
    depends_on:
      - postgres
  postgres:
    image: postgres:14
    environment:
      - POSTGRES_DB=mexchange
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=postgres
content_copy
Use code with caution.
Yaml
mexchange/create_mexchange.sh
#!/bin/bash

# Nome do Arquivo: create_mexchange.sh
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

# Cria as pastas
mkdir -p mexchange/mexchange_api/migrations/versions
mkdir -p mexchange/mexchange_api/tests
mkdir -p mexchange/mexchange_api/api
mkdir -p mexchange/mexchange_front/src/components
mkdir -p mexchange/mexchange_front/public

# Cria os arquivos
touch mexchange/mexchange_api/models.py
touch mexchange/mexchange_api/config.py
touch mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
touch mexchange/mexchange_api/migrations/alembic.ini
touch mexchange/mexchange_api/tests/test_schemas.py
touch mexchange/mexchange_api/api/schemas.py
touch mexchange/mexchange_api/main.py
touch mexchange/mexchange_front/public/index.html
touch mexchange/mexchange_front/src/components/MintForm.js
touch mexchange/mexchange_front/src/components/MintCost.js
touch mexchange/mexchange_front/src/App.js
touch mexchange/mexchange_front/src/index.js
touch mexchange/mexchange_front/src/App.css
touch mexchange/mexchange_front/package.json
touch mexchange/mexchange_front/.env
touch mexchange/create_mexchange.sh
touch mexchange/requirements.txt
touch mexchange/docker-compose.yml

# Adiciona cabeçalhos aos arquivos

# mexchange/mexchange_api/models.py
echo "# Nome do Arquivo: models.py" >> mexchange/mexchange_api/models.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/models.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/models.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/models.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/models.py

# mexchange/mexchange_api/config.py
echo "# Nome do Arquivo: config.py" >> mexchange/mexchange_api/config.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/config.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/config.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/config.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/config.py

# mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Nome do Arquivo: 000000000000_create_tables.py" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py

# mexchange/mexchange_api/migrations/alembic.ini
echo "# Nome do Arquivo: alembic.ini" >> mexchange/mexchange_api/migrations/alembic.ini
echo "# Versão: 1.0" >> mexchange/mexchange_api/migrations/alembic.ini
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/migrations/alembic.ini
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/migrations/alembic.ini
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/migrations/alembic.ini

# mexchange/mexchange_api/tests/test_schemas.py
echo "# Nome do Arquivo: test_schemas.py" >> mexchange/mexchange_api/tests/test_schemas.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/tests/test_schemas.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/tests/test_schemas.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/tests/test_schemas.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/tests/test_schemas.py

# mexchange/mexchange_api/api/schemas.py
echo "# Nome do Arquivo: schemas.py" >> mexchange/mexchange_api/api/schemas.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/api/schemas.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/api/schemas.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/api/schemas.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/api/schemas.py

# mexchange/mexchange_api/main.py
echo "# Nome do Arquivo: main.py" >> mexchange/mexchange_api/main.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/main.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/main.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/main.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/main.py

# mexchange/mexchange_front/public/index.html
echo "# Nome do Arquivo: index.html" >> mexchange/mexchange_front/public/index.html
echo "# Versão: 1.0" >> mexchange/mexchange_front/public/index.html
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/public/index.html
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/public/index.html
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/public/index.html

# mexchange/mexchange_front/src/components/MintForm.js
echo "# Nome do Arquivo: MintForm.js" >> mexchange/mexchange_front/src/components/MintForm.js
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/components/MintForm.js
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/components/MintForm.js
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/components/MintForm.js
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/components/MintForm.js

# mexchange/mexchange_front/src/components/MintCost.js
echo "# Nome do Arquivo: MintCost.js" >> mexchange/mexchange_front/src/components/MintCost.js
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/components/MintCost.js
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/components/MintCost.js
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/components/MintCost.js
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/components/MintCost.js

# mexchange/mexchange_front/src/App.js
echo "# Nome do Arquivo: App.js" >> mexchange/mexchange_front/src/App.js
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/App.js
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/App.js
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/App.js
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/App.js

# mexchange/mexchange_front/src/index.js
echo "# Nome do Arquivo: index.js" >> mexchange/mexchange_front/src/index.js
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/index.js
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/index.js
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/index.js
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/index.js

# mexchange/mexchange_front/src/App.css
echo "# Nome do Arquivo: App.css" >> mexchange/mexchange_front/src/App.css
echo "# Versão: 1.0" >> mexchange/mexchange_front/src/App.css
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/src/App.css
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/src/App.css
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/src/App.css

# mexchange/mexchange_front/package.json
echo "# Nome do Arquivo: package.json" >> mexchange/mexchange_front/package.json
echo "# Versão: 1.0" >> mexchange/mexchange_front/package.json
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/package.json
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/package.json
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/package.json

# mexchange/mexchange_front/.env
echo "# Nome do Arquivo: .env" >> mexchange/mexchange_front/.env
echo "# Versão: 1.0" >> mexchange/mexchange_front/.env
echo "# Contrato: Front-end Mexchange" >> mexchange/mexchange_front/.env
echo "# Data: 09/10/2024" >> mexchange/mexchange_front/.env
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_front/.env

# mexchange/create_mexchange.sh
echo "# Nome do Arquivo: create_mexchange.sh" >> mexchange/create_mexchange.sh
echo "# Versão: 1.0" >> mexchange/create_mexchange.sh
echo "# Contrato: API Mexchange" >> mexchange/create_mexchange.sh
echo "# Data: 09/10/2024" >> mexchange/create_mexchange.sh
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/create_mexchange.sh

# mexchange/requirements.txt
echo "# Nome do Arquivo: requirements.txt" >> mexchange/requirements.txt
echo "# Versão: 1.0" >> mexchange/requirements.txt
echo "# Contrato: API Mexchange" >> mexchange/requirements.txt
echo "# Data: 09/10/2024" >> mexchange/requirements.txt
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/requirements.txt

# mexchange/docker-compose.yml
echo "# Nome do Arquivo: docker-compose.yml" >> mexchange/docker-compose.yml
echo "# Versão: 1.0" >> mexchange/docker-compose.yml
echo "# Contrato: API Mexchange" >> mexchange/docker-compose.yml
echo "# Data: 09/10/2024" >> mexchange/docker-compose.yml
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/docker-compose.yml

echo " " >> mexchange/create_mexchange.sh
content_copy
Use code with caution.
Bash
mexchange/requirements.txt
# Nome do Arquivo: requirements.txt
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

fastapi
uvicorn
graphene
graphene-sqlalchemy
sqlalchemy
alembic
psycopg2-binary
python-dotenv
requests
web3
solcx
pytest
content_copy
Use code with caution.
mexchange/docker-compose.yml
# Nome do Arquivo: docker-compose.yml
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

version: "3.8"
services:
  mexchange_api:
    build: .
    ports:
      - "8000:8000"
    volumes:
      - .:/app
    environment:
      - DATABASE_URL=postgresql://postgres:postgres@postgres:5432/mexchange
    depends_on:
      - postgres
  postgres:
    image: postgres:14
    environment:
      - POSTGRES_DB=mexchange
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=postgres
content_copy
Use code with caution.
Yaml
mexchange/create_mexchange.sh
#!/bin/bash

# Nome do Arquivo: create_mexchange.sh
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

# Cria as pastas
mkdir -p mexchange/mexchange_api/migrations/versions
mkdir -p mexchange/mexchange_api/tests
mkdir -p mexchange/mexchange_api/api
mkdir -p mexchange/mexchange_front/src/components
mkdir -p mexchange/mexchange_front/public

# Cria os arquivos
touch mexchange/mexchange_api/models.py
touch mexchange/mexchange_api/config.py
touch mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
touch mexchange/mexchange_api/migrations/alembic.ini
touch mexchange/mexchange_api/tests/test_schemas.py
touch mexchange/mexchange_api/api/schemas.py
touch mexchange/mexchange_api/main.py
touch mexchange/mexchange_front/public/index.html
touch mexchange/mexchange_front/src/components/MintForm.js
touch mexchange/mexchange_front/src/components/MintCost.js
touch mexchange/mexchange_front/src/App.js
touch mexchange/mexchange_front/src/index.js
touch mexchange/mexchange_front/src/App.css
touch mexchange/mexchange_front/package.json
touch mexchange/mexchange_front/.env
touch mexchange/create_mexchange.sh
touch mexchange/requirements.txt
touch mexchange/docker-compose.yml

# Adiciona cabeçalhos aos arquivos

# mexchange/mexchange_api/models.py
echo "# Nome do Arquivo: models.py" >> mexchange/mexchange_api/models.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/models.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/models.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/models.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/models.py

# mexchange/mexchange_api/config.py
echo "# Nome do Arquivo: config.py" >> mexchange/mexchange_api/config.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/config.py
echo "# Contrato: API Mexchange" >> mexchange/mexchange_api/config.py
echo "# Data: 09/10/2024" >> mexchange/mexchange_api/config.py
echo "# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)" >> mexchange/mexchange_api/config.py

# mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Nome do Arquivo: 000000000000_create_tables.py" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py
echo "# Versão: 1.0" >> mexchange/mexchange_api/migrations/versions/000000000000_create_tables
content_copy
Use code with caution.
Bash

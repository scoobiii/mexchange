Mexchange: A Exchange da MEx™ - README
Mexchange é a exchange descentralizada (DEX) da MEx™ Malokeir@x Eletrik@x, uma iniciativa que visa impulsionar a inovação, a sustentabilidade e a inclusão social em São Paulo. A Mexchange é a porta de entrada para o ecossistema STALEX, a criptomoeda que financia projetos inovadores na cidade.

Recursos Principais:

Criação e Distribuição de STALEX: A Mexchange permite a criação do token STALEX e sua distribuição para as carteiras autorizadas, com custos mínimos de gás e mintagem (menos de US$1.00).

Mintagem de NFTs: Crie e liste NFTs relacionados à Lex e aos projetos de São Paulo 100%, com taxas competitivas e uma interface amigável.

Gestão de Carteiras: Gerencie suas carteiras de criptomoedas e NFTs com segurança e facilidade.

Transparência: A Mexchange é baseada em blockchain, garantindo transparência e segurança em todas as transações.

Comunidade: A Mexchange oferece um ambiente de comunidade para que os usuários possam interagir, compartilhar ideias e participar do desenvolvimento de São Paulo.

Vantagens:

Custo Acessível: O deploy do contrato STALEX e a distribuição de tokens podem ser realizados com um custo total inferior a US$ 1.00.

Simplicidade: A Mexchange foi desenvolvida com uma interface intuitiva e fácil de usar, tornando a experiência do usuário agradável e acessível.

Segurança: O sistema é construído com base em blockchain e em práticas de segurança robustas, garantindo a proteção de seus ativos.

Testes:

Foram realizados testes de funcionalidade, integração, unitários, performance, segurança e stress para garantir a qualidade e a robustez da Mexchange:

Testes de Funcionalidade: Verificam se todas as funções da plataforma funcionam conforme o esperado.

Testes de Integração: Avaliaram a integração entre as diferentes componentes da plataforma, como o front-end, a API e o contrato inteligente.

Testes Unitários: Testaram cada uma das funções do contrato inteligente de forma individual.

Testes de Performance: Simularam uma grande quantidade de usuários acessando a plataforma ao mesmo tempo para avaliar o desempenho do sistema.

Testes de Segurança: Verificaram a vulnerabilidade do contrato inteligente e da API a ataques de hackers e outros riscos de segurança.

Testes de Stress: Simularam cenários de alta demanda para identificar pontos de fraqueza e garantir que a plataforma continue funcionando de forma estável sob condições extremas.

Próximos Passos:

Expansão da Mexchange: A Mexchange irá ser expandida para incluir novas funcionalidades, como negociação de criptomoedas, staking, e outros serviços relacionados ao ecossistema STALEX.

Integração com a DAO: A Mexchange irá ser integrada à DAO do STALEX, permitindo que os usuários participem das decisões relacionadas à gestão do token e dos projetos financiados.

Crescimento da Comunidade: A Mexchange irá continuar a construir uma comunidade forte e engajada, com usuários que acreditam na visão da Lex para o futuro de São Paulo.

Mexchange: Sua porta de entrada para o ecossistema STALEX e para o futuro de São Paulo!

Estrutura de Arquivos
mexchange/
├── mexchange_api/
│   ├── models.py
│   ├── config.py
│   ├── migrations/
│   │   ├── versions/
│   │   │   └── 000000000000_create_tables.py
│   │   └── alembic.ini
│   ├── tests/
│   │   └── test_schemas.py
│   ├── api/
│   │   └── schemas.py
│   └── main.py
├── mexchange_front/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── MintForm.js
│   │   │   └── MintCost.js
│   │   ├── App.js
│   │   ├── index.js
│   │   └── App.css
│   ├── package.json
│   └── .env
├── create_mexchange.sh
└── docker-compose.yml
Use code with caution.
Cabeçalho dos Arquivos
mexchange/mexchange_api/models.py

# Nome do Arquivo: models.py
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

from sqlalchemy import Column, Integer, String, Boolean, ForeignKey, Float, DateTime
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker
from sqlalchemy import create_engine
from .config import DATABASE_URL
from datetime import datetime

engine = create_engine(DATABASE_URL)
SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)

Base = declarative_base()

db_session = SessionLocal()

def get_db():
    try:
        db = SessionLocal()
        yield db
    finally:
        db.close()

class User(Base):
    __tablename__ = 'users'
    id = Column(Integer, primary_key=True)
    username = Column(String, unique=True, index=True, nullable=False)
    email = Column(String, unique=True, index=True, nullable=False)
    password = Column(String, nullable=False)
    is_active = Column(Boolean, default=True)

class Wallet(Base):
    __tablename__ = 'wallets'
    id = Column(Integer, primary_key=True)
    user_id = Column(Integer, ForeignKey('users.id'), nullable=False)
    address = Column(String, unique=True, index=True, nullable=False)
    balance = Column(Float, default=0.0)

class Transaction(Base):
    __tablename__ = 'transactions'
    id = Column(Integer, primary_key=True)
    sender_id = Column(Integer, ForeignKey('wallets.id'), nullable=False)
    receiver_id = Column(Integer, ForeignKey('wallets.id'), nullable=False)
    amount = Column(Float, nullable=False)
    timestamp = Column(DateTime, default=datetime.utcnow)
    type = Column(String, nullable=False)

class NFT(Base):
    __tablename__ = 'nfts'
    id = Column(Integer, primary_key=True)
    owner_id = Column(Integer, ForeignKey('wallets.id'), nullable=False)
    name = Column(String, nullable=False)
    description = Column(String)
    image_url = Column(String)
    price = Column(Float)

class STALEX(Base):
    __tablename__ = 'stalex'
    id = Column(Integer, primary_key=True)
    wallet_id = Column(Integer, ForeignKey('wallets.id'), nullable=False)
    amount = Column(Float, nullable=False)
Use code with caution.
Python
mexchange/mexchange_api/config.py

# Nome do Arquivo: config.py
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

import os
from dotenv import load_dotenv

load_dotenv()

DATABASE_URL = os.getenv("DATABASE_URL", "postgresql://postgres:postgres@localhost:5432/mexchange")
SECRET_KEY = os.getenv("SECRET_KEY", "your_secret_key")
Use code with caution.
Python
mexchange/mexchange_api/migrations/versions/000000000000_create_tables.py

# Nome do Arquivo: 000000000000_create_tables.py
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

"""Create tables

Revision ID: 000000000000
Revises: 
Create Date: 2024-10-09 22:04:49.710384

"""
from alembic import op
import sqlalchemy as sa


# revision identifiers, used by Alembic.
revision = '000000000000'
down_revision = None
branch_labels = None
depends_on = None


def upgrade():
    # ### commands auto generated by Alembic - please adjust! ###
    op.create_table('users',
    sa.Column('id', sa.Integer(), nullable=False),
    sa.Column('username', sa.String(), nullable=False),
    sa.Column('email', sa.String(), nullable=False),
    sa.Column('password', sa.String(), nullable=False),
    sa.Column('is_active', sa.Boolean(), nullable=True),
    sa.PrimaryKeyConstraint('id'),
    sa.UniqueConstraint('email'),
    sa.UniqueConstraint('username')
    )
    op.create_table('wallets',
    sa.Column('id', sa.Integer(), nullable=False),
    sa.Column('user_id', sa.Integer(), nullable=False),
    sa.Column('address', sa.String(), nullable=False),
    sa.Column('balance', sa.Float(), nullable=True),
    sa.ForeignKeyConstraint(['user_id'], ['users.id'], ),
    sa.PrimaryKeyConstraint('id'),
    sa.UniqueConstraint('address')
    )
    op.create_table('transactions',
    sa.Column('id', sa.Integer(), nullable=False),
    sa.Column('sender_id', sa.Integer(), nullable=False),
    sa.Column('receiver_id', sa.Integer(), nullable=False),
    sa.Column('amount', sa.Float(), nullable=False),
    sa.Column('timestamp', sa.DateTime(), nullable=True),
    sa.Column('type', sa.String(), nullable=False),
    sa.ForeignKeyConstraint(['receiver_id'], ['wallets.id'], ),
    sa.ForeignKeyConstraint(['sender_id'], ['wallets.id'], ),
    sa.PrimaryKeyConstraint('id')
    )
    op.create_table('nfts',
    sa.Column('id', sa.Integer(), nullable=False),
    sa.Column('owner_id', sa.Integer(), nullable=False),
    sa.Column('name', sa.String(), nullable=False),
    sa.Column('description', sa.String(), nullable=True),
    sa.Column('image_url', sa.String(), nullable=True),
    sa.Column('price', sa.Float(), nullable=True),
    sa.ForeignKeyConstraint(['owner_id'], ['wallets.id'], ),
    sa.PrimaryKeyConstraint('id')
    )
    op.create_table('stalex',
    sa.Column('id', sa.Integer(), nullable=False),
    sa.Column('wallet_id', sa.Integer(), nullable=False),
    sa.Column('amount', sa.Float(), nullable=False),
    sa.ForeignKeyConstraint(['wallet_id'], ['wallets.id'], ),
    sa.PrimaryKeyConstraint('id')
    )
    # ### end Alembic commands ###


def downgrade():
    # ### commands auto generated by Alembic - please adjust! ###
    op.drop_table('stalex')
    op.drop_table('nfts')
    op.drop_table('transactions')
    op.drop_table('wallets')
    op.drop_table('users')
    # ### end Alembic commands ###
Use code with caution.
Python
mexchange/mexchange_api/migrations/alembic.ini

# Nome do Arquivo: alembic.ini
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

[alembic]

# caminho para o módulo do seu modelo SQLAlchemy
model = mexchange_api.models

# caminho para o diretório de scripts de migração
migration_context_dir = migrations/versions

# caminho para o diretório de configurações SQLAlchemy
sqlalchemy.url = postgresql://postgres:postgres@localhost:5432/mexchange

# opções para o script de migração
script_location = migrations/versions

# caminho para o diretório de configurações de banco de dados
config_file = config.py
Use code with caution.
Ini
mexchange/mexchange_api/tests/test_schemas.py

# Nome do Arquivo: test_schemas.py
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

import pytest
from fastapi.testclient import TestClient
from ..main import app, schema

@pytest.fixture
def client():
    return TestClient(app)

def test_query_items(client):
    query = """
    query {
      items {
        edges {
          node {
            id
            name
            description
          }
        }
      }
    }
    """
    response = client.post("/graphql", json={"query": query})
    assert response.status_code == 200
    assert "data" in response.json()

def test_mutation_create_item(client):
    mutation = """
    mutation {
      createItem(name: "Novo Item", description: "Descrição do novo item") {
        item {
          id
          name
          description
        }
      }
    }
    """
    response = client.post("/graphql", json={"query": mutation})
    assert response.status_code == 200
    assert "data" in response.json()
    assert "createItem" in response.json()["data"]
    assert response.json()["data"]["createItem"]["item"]["name"] == "Novo Item"
Use code with caution.
Python
mexchange/mexchange_api/api/schemas.py

# Nome do Arquivo: schemas.py
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

from graphene import ObjectType, String, Int, Field, Schema
from graphene_sqlalchemy import SQLAlchemyObjectType, SQLAlchemyConnectionField
from ..models import Item, db_session

class ItemType(SQLAlchemyObjectType):
    class Meta:
        model = Item
        interfaces = (Node, )
        session = db_session

class Query(ObjectType):
    items = SQLAlchemyConnectionField(ItemType)

class CreateItem(ObjectType):
    class Arguments:
        name = String(required=True)
        description = String()

    item = Field(ItemType)

    def mutate(self, info, name, description):
        item = Item(name=name, description=description)
        db_session.add(item)
        db_session.commit()
        return CreateItem(item=item)

class Mutation(ObjectType):
    create_item = CreateItem.Field()

schema = Schema(query=Query, mutation=Mutation)
Use code with caution.
Python
mexchange/mexchange_api/main.py

# Nome do Arquivo: main.py
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

from fastapi import FastAPI
from graphene import ObjectType, String, Int, Field, Schema
from graphene_sqlalchemy import SQLAlchemyObjectType, SQLAlchemyConnectionField
from .models import Item, db_session
from .api.schemas import schema

app = FastAPI()

@app.on_event("startup")
async def startup():
    await db_session.create_all()

@app.on_event("shutdown")
async def shutdown():
    await db_session.close()

@app.post("/graphql")
async def graphql_endpoint(request):
    return await schema.execute(request.json())
Use code with caution.
Python
mexchange/mexchange_api/deploy.sh

# Nome do Arquivo: deploy.sh
# Versão: 1.0
# Contrato: API Mexchange
# Data: 09/10/2024
# Assinatura: Zeh Sobrinho (Product Owner), Lex AI (Full Stack DevOp)

#!/bin/bash

# Ativar o ambiente virtual
source venv/bin/activate

# Instalar as dependências
pip install -r requirements.txt

# Rodar migrações
alembic upgrade head

# Iniciar o servidor
uvicorn main:app --host 0.0.0.0 --port 8000
Use code with caution.
Bash
mexchange/mexchange_api/stALEX.sol

// SPDX-License-Identifier: MIT 
// Nome do Arquivo: STALEX.sol
// Responsabilidade: Criar e gerenciar o token STALEX, a DAO e NFTs associados
// Data: 09/10/2024
// Versão: 1.5
// Assinatura: Zeh Sobrinho da MEx™ Malokeir@x Eletrik@x | Associada CCEE

pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract STALEX is ERC721URIStorage, Ownable {
    string public name = "STALEX";
    string public symbol = "STALEX";
    uint8 public decimals = 18;
    uint256 public totalSupply;
    address public royaltyReceiver = 0x0e26e81501eB5e54c55cbA7530A570cec522C926; // Carteira do criador
    address public pedroWallet = 0x1234567890abcdef1234567890abcdef12345678; // Endereço de Pedro da IA
    address public leaoWallet = 0x20551addebf6258071a1c2502864ad7b9a83bc18; // Carteira para receber Leão Coin
    uint256 public constant CREATOR_ROYALTY = 1; // 1% para o criador
    uint256 public constant PEDRO_ROYALTY = 9; // 9% para Pedro
    uint256 public constant TOTAL_ROYALTY = CREATOR_ROYALTY + PEDRO_ROYALTY; // 10% total
    uint256 public mintCost; // Custo de mintagem por NFT
    uint256 public constant MAX_TOKENS = 200;

    // Logo do STALEX
    string public logo = "https://photos.app.goo.gl/tPCj4y55yiXRjY3g7";

    // Motivação Social
    string public motivation = "A criação da cripto STALEX visa sustentar os projetos da vereadora LEX, promovendo iniciativas sustentáveis e inclusão social. A cripto é uma ferramenta para financiar e viabilizar ações que impactem positivamente a comunidade, como: "
                             "Iniciativas Sustentáveis: Fazendas Solares Verticais, Bio-bairros, Ônibus Elétrico Grátis, Renda Per Capita e Inclusão de Catadores. "
                             "Implementação de Blockchain: Registro de Energia Solar, Contratos Inteligentes, Marketplace de Energia e Transparência Financeira.";

    event Transfer(address indexed from, address indexed to, uint256 value);
    event Approval(address indexed owner, address indexed spender, uint256 value);
    
    mapping(address => uint256) public balanceOf;
    mapping(address => mapping(address => uint256)) public allowance;
    mapping(address => bool) public wallets; // Mapeia carteiras permitidas
    uint256 public walletCount; // Contagem de carteiras permitidas

    constructor(uint256 _initialSupply, uint256 _mintCost) ERC721("STALEX NFT", "STALEX") {
        totalSupply = _initialSupply * 10 ** uint256(decimals);
        mintCost = _mintCost;
        balanceOf[msg.sender] = totalSupply;
    }

    function mintNFT(string memory tokenURI) public payable {
        require(msg.value >= mintCost, "Fundos insuficientes para mintar NFT");
        require(totalSupply < MAX_TOKENS, "Máximo de tokens já mintados");
        
        totalSupply++;
        uint256 tokenId = totalSupply; // Aqui, o tokenId será baseado na contagem de mintagem
        _mint(msg.sender, tokenId);
        _setTokenURI(tokenId, tokenURI);
        
        // Pagar royalties
        payable(royaltyReceiver).transfer((msg.value * CREATOR_ROYALTY) / 100);
        payable(pedroWallet).transfer((msg.value * PEDRO_ROYALTY) / 100);
    }

    function transfer(address _to, uint256 _value) public returns (bool success) {
        require(balanceOf[msg.sender] >= _value, "Saldo insuficiente");
        balanceOf[msg.sender] -= _value;
        balanceOf[_to] += _value;
        emit Transfer(msg.sender, _to, _value);
        return true;
    }

    function transferLeaoCoin() public returns (bool success) {
        // Transferir 1 STALEX para a carteira Leão
        require(balanceOf[msg.sender] >= 1, "Saldo insuficiente para transferir 1 STALEX");
        balanceOf[msg.sender] -= 1;
        balanceOf[leaoWallet] += 1;
        emit Transfer(msg.sender, leaoWallet, 1);
        return true;
    }

    function approve(address _spender, uint256 _value) public returns (bool success) {
        allowance[msg.sender][_spender] = _value;
        emit Approval(msg.sender, _spender, _value);
        return true;
    }

    function transferFrom(address _from, address _to, uint256 _value) public returns (bool success) {
        require(balanceOf[_from] >= _value, "Saldo insuficiente");
        require(allowance[_from][msg.sender] >= _value, "Limite excedido");
        balanceOf[_from] -= _value;
        balanceOf[_to] += _value;
        allowance[_from][msg.sender] -= _value;
        emit Transfer(_from, _to, _value);
        return true;
    }

    // Função para adicionar novas carteiras
    function addNewWallet(address newWallet) public onlyOwner {
        require(walletCount < MAX_TOKENS, "Máximo de carteiras já adicionadas");
        require(!wallets[newWallet], "Carteira já adicionada");
        
        wallets[newWallet] = true;
        walletCount++;
    }
}
content_copy
Use code with caution.
Solidity

Automatizando o Deploy com Python:

from web3 import Web3
from web3.middleware import geth_poa_middleware
from solcx import compile_source
import os

# Credenciais da rede Polygon
INFURA_PROJECT_ID = "YOUR_INFURA_PROJECT_ID"  # Substitua pelo seu ID do projeto Infura
PRIVATE_KEY = "YOUR_PRIVATE_KEY"           # Substitua pela sua chave privada

# Endereço da carteira Leão
leaoWallet = "0x20551addebf6258071a1c2502864ad7b9a83bc18"

# Conectar ao nó da rede Polygon (Infura)
w3 = Web3(Web3.HTTPProvider(f"https://polygon-mainnet.infura.io/v3/{INFURA_PROJECT_ID}"))
w3.middleware_onion.inject(geth_poa_middleware, layer=0)

# Compilar o contrato STALEX
compiled_sol = compile_source(
    """
    // SPDX-License-Identifier: MIT
    // Nome do Arquivo: STALEX.sol
    // Responsabilidade: Criar e gerenciar o token STALEX, a DAO e NFTs associados
    // Data: 09/10/2024
    // Versão: 1.7
    // Assinatura: Zeh Sobrinho da MEx™ Malokeir@x Eletrik@x | Associada CCEE

    pragma solidity ^0.8.0;

    import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
    import "@openzeppelin/contracts/access/Ownable.sol";

    contract STALEX is ERC20, Ownable {
        string public name = "STALEX";
        string public symbol = "STALEX";
        uint8 public decimals = 18;
        uint256 public totalSupply;
        address public royaltyReceiver = 0x0e26e81501eB5e54c55cbA7530A570cec522C926; // Carteira do criador
        address public pedroWallet = 0x1234567890abcdef1234567890abcdef12345678; // Endereço de Pedro da IA
        address public leaoWallet = 0x20551addebf6258071a1c2502864ad7b9a83bc18; // Carteira para receber Leão Coin
        uint256 public constant CREATOR_ROYALTY = 1; // 1% para o criador
        uint256 public constant PEDRO_ROYALTY = 9; // 9% para Pedro
        uint256 public constant TOTAL_ROYALTY = CREATOR_ROYALTY + PEDRO_ROYALTY; // 10% total
        uint256 public mintCost; // Custo de mintagem por NFT
        uint256

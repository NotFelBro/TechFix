# 🛠️ TechFix — Sistema de Gestão de Assistência Técnica

## 📌 Sobre o projeto

O **TechFix** é um projeto de banco de dados relacional desenvolvido para representar o gerenciamento de uma assistência técnica de equipamentos eletrônicos.

O banco foi desenvolvido utilizando **SQLite**, com modelagem de dados, relacionamentos, regras de integridade e mecanismos de rastreabilidade das operações.

O objetivo é organizar informações relacionadas a clientes, funcionários, equipamentos, ordens de serviço, serviços técnicos e controle de estoque.

## 🛠️ Tecnologias utilizadas

- **SQLite** — Banco de dados relacional.
- **DBeaver** — Desenvolvimento, administração e validação do banco.
- **Visual Studio Code** — Organização dos arquivos do projeto.
- **Git e GitHub** — Versionamento e disponibilização do projeto.

## 📂 Estrutura do repositório

```text
TechFix/
├── db/
│   └── techfix.sqlite
├── docs/
│   └── TechFix_Dicionario_de_Dados.xlsx
├── modelo/
└── README.md
```

- **db/** — Contém o banco SQLite.
- **docs/** — Contém o Dicionário de Dados atualizado.
- **modelo/** — Arquivos complementares de modelagem.
- **README.md** — Documentação de apresentação do projeto.

## 🗃️ Estrutura do banco de dados

O banco TechFix possui:

| Elemento | Quantidade |
|---|---:|
| Tabelas | 17 |
| Triggers | 34 |
| Índices | 10 |
| Views | 1 |

### Principais funcionalidades modeladas

- Cadastro e gerenciamento de funcionários e clientes.
- Organização de equipamentos, marcas, modelos e tipos.
- Registro de ordens de serviço.
- Associação de serviços e peças às ordens.
- Controle de entradas e saídas de estoque.
- Histórico de movimentações.
- Rastreabilidade das mudanças de situação das ordens de serviço.

## 🔐 Integridade e regras de negócio

O banco utiliza mecanismos do SQLite para garantir a consistência dos dados:

- **PRIMARY KEY:** identificação dos registros.
- **FOREIGN KEY:** relacionamentos entre tabelas.
- **NOT NULL:** obrigatoriedade de preenchimento.
- **UNIQUE:** restrições de unicidade.
- **CHECK:** validação de valores e condições.
- **DEFAULT:** definição de valores padrão.
- **TRIGGERS:** execução automática de regras de integridade e rastreabilidade.

### Histórico das ordens de serviço

O histórico é armazenado na tabela `ordem_situacao`, com mecanismos para:

- Validar transições de situação.
- Atualizar automaticamente a situação da ordem.
- Impedir alterações diretas sem histórico válido.
- Bloquear alterações e exclusões de registros históricos.
- Proteger o vínculo entre a ordem e sua última movimentação.

## 🚀 Como abrir o banco no DBeaver

1. Clone o repositório ou baixe seus arquivos pelo GitHub.
2. Abra o **DBeaver**.
3. Crie uma nova conexão.
4. Selecione **SQLite** como tipo de banco.
5. Localize o arquivo `db/techfix.sqlite`.
6. Finalize a conexão.
7. Expanda as tabelas, índices, views e triggers para analisar a estrutura.

## ✅ Testes e validações

Durante o desenvolvimento foram realizadas verificações de integridade e consistência.

| Verificação | Resultado |
|---|---|
| `PRAGMA integrity_check` | `ok` |
| `PRAGMA foreign_key_check` | 0 violações |
| Auditoria dos vínculos históricos | 5 ordens verificadas |
| Conferência das triggers migradas | 8 de 8 |

As validações foram realizadas na versão do banco auditada em novembro de 2026.

## 📚 Documentação

O Dicionário de Dados está disponível em:

`docs/TechFix_Dicionario_de_Dados.xlsx`

O documento apresenta os campos, tipos de dados, chaves, relacionamentos e definições estruturais do banco.

## 🎓 Contexto acadêmico

Projeto desenvolvido para aplicação prática de conhecimentos em modelagem de banco de dados relacional, SQL, integridade referencial e regras de negócio.

## 📄 Licença

Projeto de finalidade acadêmica. Nenhuma licença de uso foi definida neste repositório.

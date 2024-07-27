# Comandos Structured Query Language

## Data definition language ( DDL ) comands

- Cria um banco de dados
```
CREATE DATABASE
```

Exemplo:
```sql
CREATE DATABASE my_database;
```

- Cria um esquema de banco de dados
```
CREATE SCHEMA AUTHORIZATION
```

Exemplo:
```sql
CREATE SCHEMA AUTHORIZATION anderson_reiner;
```

- Cria uma nova tabela no esquema de BD do usuário
```
CREATE TABLE
```
Exemplo:

```sql
CREATE TABLE alunos(
    id INT,
    nome VARCHAR(50),
);
```
- Assegura que uma coluna não contenha valores nulos

```
NOT NULL
```

Exemplo:
```sql
CREATE TABLE alunos(
    id INT NOT NULL,
    nome VARCHAR(50) NOT NULL,
);
```

- Assegura que uma coluna não contenha valores duplicados
```
UNIQUE
```

Exemplo:
```sql
CREATE TABLE alunos(
    id INT NOT NULL UNIQUE,
    nome VARCHAR(50) NOT NULL,
);
```

- Define a chave primária de uma tabela
```
PRIMARY KEY
```

Exemplo:
```sql
CREATE TABLE alunos(
    id INT NOT NULL UNIQUE,
    nome VARCHAR(50) NOT NULL,
    PRIMARY KEY (id)
);

```

- Define a chave estrangeira de uma tabela
```
FOREIGN KEY
```

Exemplo:
```sql
CREATE TABLE cursos(
	id SERIAL,
	nome VARCHAR(50),
	PRIMARY KEY (id)
);

CREATE TABLE alunos(
    id INT NOT NULL UNIQUE,
    nome VARCHAR(50) NOT NULL,
    id_curso INT NOT NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (id_curso) REFERENCES cursos(id)
);
```

- Define um valor padrão de uma coluna (quando não informado)
```
DEFAULT
```

Exemplo:
```sql
CREATE TABLE alunos(
    id INT NOT NULL UNIQUE,
    nome VARCHAR(50) NOT NULL,
    semestre INT DEFAULT 1,
    PRIMARY KEY (id)
);
```

- Valida os dados de um atributo
```
CHECK
```

Exemplo:
```sql
CREATE TABLE alunos(
    id INT NOT NULL UNIQUE,
    nome VARCHAR(50) NOT NULL,
    semestre INT DEFAULT 1,
    sexo CHAR(1) NOT NULL,
    PRIMARY KEY (id),
    CHECK(sexo in ('M', 'F'))
);

```

- Modifica uma definição de tabelas (adiciona, modifica ou exclui
atributos ou restrições)
```
ALTER TABLE
```

podendo ser:

```
ALTER TABLE ADD
```

Exemplo:
```sql
ALTER TABLE alunos ADD data_nascimento DATE NOT NULL;
```

OU 

```
ALTER TABLE DROP
```



Exemplo:
```sql
ALTER TABLE alunos DROP data_nascimento;
```

- Exclui uma tabela (e seus dados) de forma permanente
```
DROP TABLE
```

Exemplo:
```sql
DROP TABLE alunos;
```
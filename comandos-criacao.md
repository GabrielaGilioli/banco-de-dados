# Comandos SQL - Referência
<!-- ________________________________________________________________ -->
## Modelagem física

### Criar banco de dados
```sql
CREATE DATABASE vendas CHARACTER SET utf8mb4;

```

<!-- ________________________________________________________________ -->

### Criar a tabela fabricantes

```sql
CREATE TABLE fabricantes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
)

```

<!-- ________________________________________________________________ -->

### Criar a tabela produtos

```sql
CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(1000) NOT NULL,
    preco DECIMAL(6,2) NOT NULL,
    quantidade TINYINT(4) NOT NULL
)

```

<!-- ________________________________________________________________ -->

### Adicionar campo/coluna em uma tabela

```sql

ALTER TABLE produtos ADD fabricante_id INT NOT NULL
AFTER quantidade;

```

<!-- ________________________________________________________________ -->

### Criação da chave estrangeira (relacionamento entre tabelas)

```sql

ALTER TABLE produtos
    # CONSTRAINT é uma restrição definida no relacionamento
    ADD CONSTRAINT fk_produtos_fabricantes

    # A chave estrangeira deve fazer referência a chave primaria
    FOREIGN KEY(fabricante_id) REFERENCES fabricante(id)

```
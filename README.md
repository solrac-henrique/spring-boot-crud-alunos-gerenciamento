# Sistema de Gerenciamento de Alunos

Aplicação web em **Java + Spring Boot**, estruturada no padrão **MVC**, para gerenciamento de alunos com acesso restrito a um administrador autenticado.

## Sobre o projeto

O sistema possui uma única tela de login, destinada ao administrador. Após a autenticação, é possível cadastrar, editar, listar e excluir alunos. Não há cadastro próprio para os alunos — eles são apenas registros gerenciados pelo administrador logado.

A senha do administrador não é armazenada em texto puro: ela passa por **hash com BCrypt** antes de ser salva no banco, seguindo uma prática básica e essencial de segurança no tratamento de credenciais.

## Funcionalidades

- Login do administrador, com senha protegida por hash (BCrypt)
- Cadastro de alunos (nome, matrícula, curso, e-mail, status)
- Edição e exclusão de alunos
- Listagem de todos os alunos cadastrados
- Persistência dos dados em banco H2

## Tecnologias utilizadas

- **Java**
- **Spring Boot**
- **Spring Security** (autenticação e hash de senha com BCrypt)
- **Spring Data JPA**
- **Thymeleaf** (renderização das páginas HTML no servidor)
- **H2 Database** (banco de dados em memória)
- **Maven**

## Arquitetura

O projeto segue o padrão **MVC (Model-View-Controller)**:

- **Model**: entidades persistidas via JPA (ex: `Aluno`, `Administrador`)
- **View**: páginas HTML renderizadas com Thymeleaf
- **Controller**: classes responsáveis por receber requisições e orquestrar a lógica entre a View e o Model

## Como executar o projeto localmente

### Pré-requisitos
- JDK 17 ou superior instalado
- Maven (ou usar o Maven Wrapper já incluso no projeto, `mvnw`)

### Passo a passo

```bash
# Clone o repositório
git clone https://github.com/solrac-henrique/spring-boot-crud-alunos-gerenciamento.git

# Acesse a pasta do projeto
cd spring-boot-crud-alunos-gerenciamento

# Execute com o Maven Wrapper (Linux/Mac)
./mvnw spring-boot:run

# Ou no Windows
mvnw.cmd spring-boot:run
```

A aplicação estará disponível em `http://localhost:8080`.

> Por usar o banco H2 em memória, os dados cadastrados são reiniciados a cada vez que a aplicação é reiniciada — não há necessidade de configurar nenhum banco externo para testar o projeto.

## Próximos passos

Algumas melhorias que pretendo implementar:

- [ ] Validação de campos no formulário de cadastro (ex: e-mail e matrícula únicos)
- [ ] Testes unitários para os Services e Controllers
- [ ] Migrar para um banco persistente (PostgreSQL) como opção de configuração

## Autor

Desenvolvido por [Carlos Henrique Martins](https://github.com/solrac-henrique).

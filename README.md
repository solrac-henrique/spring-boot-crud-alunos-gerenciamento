# Sistema de Gerenciamento de Alunos

Aplicação web em Java + Spring Boot, estruturada no padrão MVC, para gerenciamento de alunos com acesso restrito a um administrador autenticado.

---

## 📋 Sobre o projeto

O sistema possui uma única tela de login, destinada ao administrador. Após a autenticação, é possível cadastrar, editar, listar e excluir alunos. Não há cadastro próprio para os alunos — eles são apenas registros gerenciados pelo administrador logado.

A senha do administrador é armazenada com **hash BCrypt**, garantindo que a credencial nunca fique em texto puro no banco de dados.

---

## ✅ Funcionalidades implementadas

- 🔐 Login do administrador com senha protegida por BCrypt
- 📝 Cadastro de alunos com validação (`@NotBlank`, `@Email`)
- ✏️ Edição e exclusão de alunos com confirmação
- 📋 Listagem de todos os alunos cadastrados
- 💬 Mensagens de feedback estilizadas (sucesso/erro)
- 🛡️ Tratamento de erros (aluno não encontrado, campos inválidos)
- 🔒 Proteção de todas as rotas (só admin logado acessa)

---

## 🛠 Tecnologias utilizadas

| Tecnologia | Descrição |
|---|---|
| **Java 17** | Linguagem de programação |
| **Spring Boot 3** | Framework principal |
| **Spring Security** | Autenticação e hash de senha (BCrypt) |
| **Spring Data JPA** | Persistência e ORM |
| **Thymeleaf** | Renderização de páginas HTML no servidor |
| **H2 Database** | Banco de dados em memória |
| **Bean Validation** | Validação de campos (`@NotBlank`, `@Email`) |
| **Maven** | Gerenciador de dependências |

---

## 🏗 Arquitetura

O projeto segue o padrão **MVC (Model-View-Controller)**:

src/main/java/com/gerenciamento/alunos/
├── model/ → Entidades JPA (Aluno)
├── repository/ → Interfaces JPA (AlunoRepository)
├── controller/ → Controllers (AlunoController)
└── config/ → Configurações (SecurityConfig)

- **Model:** entidades persistidas via JPA
- **View:** páginas HTML renderizadas com Thymeleaf
- **Controller:** orquestra a lógica entre View e Model

---

## 🚀 Como executar localmente

### Pré-requisitos

- JDK 17 ou superior
- Maven (ou use o Maven Wrapper incluso)

### Passo a passo

```bash
# Clone o repositório
git clone https://github.com/solrac-henrique/spring-boot-crud-alunos-gerenciamento.git

# Acesse a pasta
cd spring-boot-crud-alunos-gerenciamento

# Execute (Linux/Mac)
./mvnw spring-boot:run

# Ou no Windows
mvnw.cmd spring-boot:run

Acesse: http://localhost:8080

Credenciais de acesso
Campo	Valor
Usuário	admin
Senha	admin123
⚠️ O banco H2 é em memória. Os dados são perdidos ao reiniciar a aplicação.

🎨 Preview da interface
https://login.png
https://cadastro.png

🔜 Próximos passos
🧪 Testes unitários para Services e Controllers

🐘 Migrar para banco PostgreSQL (opcional)

🐳 Dockerfile e docker-compose

📊 Dashboard com gráficos (alunos por curso/status)

🔄 API REST com Swagger/OpenAPI


👤 Autor
Desenvolvido por Carlos Henrique Martins



📄 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

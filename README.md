<div align="center">

<img src="https://img.shields.io/badge/Java-21-orange?style=flat-square&logo=openjdk" />
<img src="https://img.shields.io/badge/Spring_Boot-3.2.5-6DB33F?style=flat-square&logo=springboot" />
<img src="https://img.shields.io/badge/PostgreSQL-18-4169E1?style=flat-square&logo=postgresql" />
<img src="https://img.shields.io/badge/Deploy-Render.com-46E3B7?style=flat-square" />
<img src="https://img.shields.io/badge/Frontend-Vercel-black?style=flat-square&logo=vercel" />
<img src="https://img.shields.io/badge/Status-Em_Produção-27ae60?style=flat-square" />

# 📚 Biblioteca Ler e Educar

**Sistema B2B de gerenciamento e logística de acervo literário para instituições de ensino fundamental**

[🌐 Acessar Sistema] https://front-integrado.vercel.app/index.html · [📖 Swagger](https://ler-e-educar-api.onrender.com/swagger-ui.html)

</div>

---

## 📋 Sobre o Projeto

O **Ler e Educar** é uma plataforma web full stack desenvolvida como trabalho acadêmico para a disciplina de **Programação Orientada a Objetos** — Ciências da Computação, Faculdade Impacta de Tecnologia (2026).

O sistema gerencia o empréstimo semestral de acervos literários físicos entre a biblioteca e instituições de ensino fundamental (1º ao 5º ano), com controle completo de estoque, logística de envio e renovação trimestral.

### 👥 Equipe

| Integrante | GitHub |
|---|---|
| Beatriz Perez Cizino Miranda | [@beatriz](https://github.com) |
| Guilherme de Oliveira Santos | [@saysxnts](https://github.com/saysxnts) |
| Karine Marques de Andrade | — |
| Thiago Ferreira Marques | — |

**Orientador:** Prof. Cesar Augusto Cardoso Caetano

---

## 🚀 Deploy em Produção

| Serviço | URL | Status |
|---|---|---|
| Frontend | https://front-integrado.vercel.app | ✅ Online |
| Backend API | https://ler-e-educar-api.onrender.com | ✅ Online |
| Banco de Dados | Render PostgreSQL (Render) | ✅ Online |
| Documentação | /swagger-ui.html | ✅ Online |

### 🔑 Credenciais de Demonstração

```
Admin:  admin@lereducar.com.br  /  Admin@2026
```

> Para testar o fluxo do gestor, cadastre uma nova instituição em `/cadastro.html`

---

## 🏗️ Arquitetura

```
┌─────────────────────────────────────────────────────────┐
│                    FRONTEND (Vercel)                     │
│         HTML5 + CSS3 + JavaScript (ES6+)                 │
│         Design System próprio · Chart.js · ViaCEP        │
└──────────────────────────┬──────────────────────────────┘
                           │ HTTPS / REST
┌──────────────────────────▼──────────────────────────────┐
│                   BACKEND (Render.com)                   │
│             Java 21 + Spring Boot 3.2.5                  │
│         JWT Auth · Spring Security · Flyway              │
└──────────────────────────┬──────────────────────────────┘
                           │ JDBC
┌──────────────────────────▼──────────────────────────────┐
│              BANCO DE DADOS (Render PostgreSQL)          │
│                   PostgreSQL 18.x                        │
└─────────────────────────────────────────────────────────┘
```

---

## 🛠️ Stack Tecnológica

### Backend
| Tecnologia | Versão | Uso |
|---|---|---|
| Java | 21 (LTS) | Linguagem principal |
| Spring Boot | 3.2.5 | Framework web e IoC |
| Spring Security | 6.x | Autenticação e autorização |
| JJWT | 0.12.5 | Geração de tokens JWT |
| PostgreSQL | 18.x | Banco de dados relacional |
| Flyway | 9.x | Migrações de banco |
| Lombok | — | Redução de boilerplate |
| SpringDoc OpenAPI | 2.5 | Documentação Swagger |

### Frontend
| Tecnologia | Uso |
|---|---|
| HTML5 / CSS3 | Estrutura e estilização das 18 páginas |
| JavaScript (ES6+) | Integração com API REST |
| Chart.js 4.4 | Gráficos do Dashboard BI |
| Open Library API | Busca de capas por ISBN/título |
| ViaCEP API | Auto-preenchimento de endereço |
| Playfair Display + DM Sans | Tipografia do design system |

---

## 📡 Endpoints da API REST

### Públicos (sem autenticação)
| Método | Endpoint | Descrição |
|---|---|---|
| `POST` | `/api/auth/login` | Autenticação JWT |
| `POST` | `/api/instituicoes` | Cadastro de instituição |
| `GET` | `/api/stats` | Estatísticas públicas |

### Gestor Escolar 🏫
| Método | Endpoint | Descrição |
|---|---|---|
| `GET` | `/api/livros` | Listar catálogo |
| `POST` | `/api/emprestimos` | Solicitar empréstimo |
| `GET` | `/api/emprestimos/meus` | Meus empréstimos |
| `PATCH` | `/api/emprestimos/{id}/confirmar-uso` | Renovar por 90 dias |

### Administrador 🔐
| Método | Endpoint | Descrição |
|---|---|---|
| `GET` | `/api/instituicoes` | Listar instituições |
| `PATCH` | `/api/instituicoes/{id}/aprovar` | Aprovar cadastro |
| `PATCH` | `/api/instituicoes/{id}/bloquear` | Bloquear acesso |
| `PATCH` | `/api/instituicoes/{id}/resetar-senha` | Redefinir senha |
| `DELETE` | `/api/instituicoes/{id}` | Excluir em cascata |
| `POST` | `/api/livros` | Cadastrar livro |
| `PUT` | `/api/livros/{id}` | Editar livro |
| `DELETE` | `/api/livros/{id}` | Excluir livro |
| `GET` | `/api/emprestimos` | Todos os empréstimos |
| `PATCH` | `/api/emprestimos/{id}/aprovar` | Aprovar solicitação |
| `POST` | `/api/emprestimos/devolucao` | Registrar devolução |
| `GET` | `/api/relatorios/popularidade` | Relatório de popularidade |

---

## 🖥️ Telas do Sistema

### Área Pública
| Página | Descrição |
|---|---|
| `index.html` | Landing page com stats reais da API |
| `login.html` | Login com animações e parallax |
| `cadastro.html` | Cadastro multi-etapas + ViaCEP |
| `esqueciS.html` | Recuperação de senha |

### Área do Gestor Escolar
| Página | Descrição |
|---|---|
| `catalogo.html` | Catálogo com filtros, skeleton e reserva |
| `reservas.html` | Tracker de logística 4 etapas |
| `devolutivas.html` | Confirmar uso e histórico |
| `perfil-usuario.html` | Perfil com stats de empréstimos |

### Área Administrativa
| Página | Descrição |
|---|---|
| `dashboard.html` | **Dashboard BI** com 6 gráficos Chart.js |
| `catalogo-admin.html` | Catálogo com edição inline |
| `adicionar-livro.html` | Preview ao vivo + busca por ISBN |
| `emprestimo.html` | Tabs + barra de vencimento colorida |
| `devolucao.html` | Registro de devoluções |
| `controle-estoque.html` | Grid com barras de disponibilidade |
| `controle-usuario.html` | Cards de escolas + reset de senha |
| `meu-perfil-ADM.html` | Painel com atividade e acervo |

---

## 🗄️ Modelagem do Banco

### Diagrama de Entidades

```
TB_USUARIO (abstract)
  ├── TB_ADMINISTRADOR
  └── TB_GESTOR_ESCOLAR ──── TB_INSTITUICAO
                                   └── TB_INSTITUICAO_SERIE

TB_LIVRO ──── TB_LIVRO_SERIE_INDICADA
  └── TB_EXEMPLAR

TB_PROTOCOLO_EMPRESTIMO
  ├── TB_ITEM_EMPRESTIMO ──── TB_EXEMPLAR
  ├── TB_LOGISTICA
  └── TB_RENOVACAO

TB_AVARIA ──── TB_EXEMPLAR
```

### Migrações Flyway
| Versão | Descrição |
|---|---|
| V1 | Schema completo com todas as tabelas e FKs |
| V2 | Seed do usuário administrador padrão |
| V3 | Re-hash BCrypt da senha do admin |

---

## ⚙️ Como Rodar Localmente

### Pré-requisitos
- Java 21+
- Maven 3.8+
- PostgreSQL 14+
- Node.js (opcional, para servir o frontend)

### Backend

```bash
# Clone o repositório
git clone https://github.com/saysxnts/ler-e-educar-backend.git
cd ler-e-educar-backend

# Configure o banco de dados em src/main/resources/application.properties
# spring.datasource.url=jdbc:postgresql://localhost:5432/lereducar_db
# spring.datasource.username=postgres
# spring.datasource.password=sua_senha
# jwt.secret=seu_secret_de_32_caracteres_minimo

# Rode
mvn spring-boot:run
```

A API estará disponível em `http://localhost:8080`
Swagger em `http://localhost:8080/swagger-ui.html`

### Frontend

```bash
git clone https://github.com/saysxnts/front-integrado.git
cd front-integrado

# Abra com Live Server (VS Code) ou sirva estaticamente
# Ou abra index.html direto no browser
```

> **Atenção:** o frontend aponta para a API de produção no Render. Para usar localmente, altere `API_BASE` em `js/api.js`

---

## 🔐 Variáveis de Ambiente (Backend)

| Variável | Descrição |
|---|---|
| `SPRING_DATASOURCE_URL` | URL JDBC do PostgreSQL |
| `SPRING_DATASOURCE_USERNAME` | Usuário do banco |
| `SPRING_DATASOURCE_PASSWORD` | Senha do banco |
| `JWT_SECRET` | Secret para assinar tokens (mín. 32 chars) |
| `SPRING_PROFILES_ACTIVE` | `dev` ou `prod` |

---

## 📊 Dashboard BI

O sistema conta com um **Dashboard Business Intelligence** completo acessível em `/dashboard.html`:

- **5 KPIs animados** com sparklines — Títulos, Instituições, Pendentes, Exemplares, Taxa de Aprovação
- **Gráfico de linha temporal** — evolução de empréstimos nos últimos 14 dias
- **Doughnut** — distribuição de status com métricas inline
- **Barra horizontal** — acervo por categoria
- **Funil de conversão** — Solicitados → Aprovados → Devolvidos
- **Barras de estoque** — criticidade por título
- **Ranking de instituições** — top 5 por volume
- **Alertas inteligentes** — gerados automaticamente pelos dados reais
- **Auto-refresh a cada 60 segundos**

---

## 🔄 Fluxo Principal do Sistema

```
Gestor cadastra instituição
        ↓
Admin aprova o cadastro
        ↓
Gestor acessa o catálogo e solicita empréstimo
        ↓
Admin aprova o protocolo (status: APROVADO)
        ↓
Livros são enviados fisicamente para a escola
        ↓
Gestor confirma uso a cada 90 dias (renovação)
        ↓
Admin registra devolução (BOM / DANIFICADO / PÉSSIMO)
```

---

## 🧪 Regras de Negócio

| Regra | Descrição |
|---|---|
| **RN01** | Máximo 3 exemplares por série por empréstimo |
| **RN02** | Renovação estende vencimento em +90 dias |
| **RN03** | Apenas instituições `ATIVA` podem solicitar |
| **RN04** | Senha mínima de 6 caracteres (BCrypt) |
| **RN05** | Token JWT expira em 8 horas |
| **RN06** | Exclusão de livro remove exemplares e itens em cascata |
| **RN07** | Exclusão de instituição remove gestores e empréstimos |

---

## 📁 Estrutura do Projeto

### Backend
```
src/main/java/com/lereducar/
├── config/           # SecurityConfig, CORS, DataInitializer
├── controller/       # REST Controllers
├── dto/
│   ├── request/      # DTOs de entrada
│   └── response/     # DTOs de saída
├── entity/           # Entidades JPA
├── enums/            # Enumerações (Status, Categoria, Serie...)
├── exception/        # Exceções customizadas
├── repository/       # Interfaces JPA
├── security/         # JWT Filter, TokenService
└── service/          # Lógica de negócio (interfaces + impl)

src/main/resources/
├── db/migration/     # Scripts Flyway (V1, V2, V3)
└── application.properties
```

### Frontend
```
front-integrado/
├── css/
│   ├── design-system.css   # Tokens, animações, keyframes
│   ├── layout.css          # Header, menu lateral, notificações
│   └── login.css           # Estilos da tela de login
├── js/
│   ├── api.js              # Auth, fetch genérico, busca de capas
│   ├── layout.js           # Menu, scroll, initAnimations
│   ├── animations.js       # Tilt 3D, parallax, partículas
│   └── notifications.js    # Sistema de notificações em tempo real
├── img/                    # Assets de imagem
├── index.html              # Landing page
├── login.html
├── cadastro.html
├── dashboard.html          # Dashboard BI
├── catalogo-admin.html
├── emprestimo.html
└── ... (18 páginas no total)
```

---

## 📄 Licença

Projeto acadêmico desenvolvido para fins educacionais — Faculdade Impacta de Tecnologia, 2026.

---

<div align="center">
  Desenvolvido com ❤️ pela turma de POO — Impacta 2026
</div>

# 🎟️ EntradaMaster — Plataforma de Eventos e Venda de Ingressos

Plataforma completa para criação de eventos, venda de ingressos online e emissão de tickets digitais com QR Code.

**🔗 Demo (MVP em produção):** https://development-sigma-beige.vercel.app

> Projeto desenvolvido em equipe como freelancer (fev/2025 – set/2025). Atuei principalmente no **backend**: API, banco de dados, autenticação, integração de pagamentos e geração de ingressos.

---

## ✨ Funcionalidades

- Cadastro e login de usuários (e-mail/senha e OAuth)
- Criação e gerenciamento de eventos
- Fluxo de compra completo: carrinho → checkout → confirmação
- Pagamento via gateway com confirmação automática por **webhooks**
- Emissão de ingressos em **PDF com QR Code**
- Envio automático de **e-mails transacionais**
- Processamento assíncrono com **filas (BullMQ + Redis)** e tarefas agendadas

## 👨‍💻 Minha contribuição

- API tipada com **tRPC** e **Next.js API Routes** para usuários, eventos, pedidos e ingressos
- Validação de dados com **Zod**
- Modelagem do banco **PostgreSQL** com **Prisma ORM**
- Autenticação e controle de acesso com **NextAuth.js** (OAuth + credenciais com bcrypt)
- Integração com o gateway de pagamento **Pagotic**, incluindo tratamento de webhooks
- Geração de ingressos em PDF (**PDFKit**) com QR Code
- E-mails transacionais com **Nodemailer**
- Testes de integração e validação das respostas da API

## 🛠️ Tecnologias

| Camada | Tecnologias |
| --- | --- |
| Linguagem | TypeScript |
| Backend | Next.js (API Routes), tRPC, Zod, NextAuth.js |
| Banco de dados | PostgreSQL (Supabase), Prisma ORM |
| Filas e jobs | BullMQ, Redis, node-cron |
| Ingressos e e-mails | PDFKit, QRCode, Nodemailer |
| Frontend | React, Tailwind CSS, React Hook Form, Zustand |
| Deploy | Vercel |

## 🚀 Como rodar localmente

### Requisitos

- [Node.js](https://nodejs.org/) 22+
- [PostgreSQL](https://www.postgresql.org/) local ou conta no [Supabase](https://supabase.com/)
- [Redis](https://redis.io/) (para as filas)

### Passo a passo

```bash
# Clone o repositório
git clone https://github.com/kauen1999/development-.git
cd development-

# Instale as dependências
npm install

# Configure as variáveis de ambiente (veja abaixo)
cp .env.example .env

# Rode as migrações do Prisma
npx prisma migrate dev

# Inicie o servidor
npm run dev

# (Opcional) Inicie o worker das filas em outro terminal
npm run worker
```

Acesse: http://localhost:3000

### Variáveis de ambiente

Crie um arquivo `.env` na raiz com, no mínimo:

```env
DATABASE_URL=          # conexão PostgreSQL
NEXTAUTH_SECRET=       # chave secreta do NextAuth
NEXTAUTH_URL=http://localhost:3000
REDIS_URL=             # conexão Redis
# + credenciais do gateway de pagamento e do servidor de e-mail (SMTP)
```

## 📬 Contato

**Jocean Ferreira** — Desenvolvedor Backend
[LinkedIn](https://www.linkedin.com/in/jocean-ferreira-544613150/) · jocean.dev@gmail.com

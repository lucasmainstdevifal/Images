# 🚀 Admissão Fácil

<div align="center">

![Next.js](https://img.shields.io/badge/Next.js-14-black?style=for-the-badge&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-blue?style=for-the-badge&logo=typescript)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-blue?style=for-the-badge&logo=postgresql)
![Prisma](https://img.shields.io/badge/Prisma-5.21-2D3748?style=for-the-badge&logo=prisma)
![Clerk](https://img.shields.io/badge/Clerk-Auth-6C47FF?style=for-the-badge)

**Sistema completo de gestão de admissões de funcionários com interface moderna e intuitiva**

[Features](#-features) • [Instalação](#-instalação) • [Documentação](#-documentação) • [Contribuindo](#-contribuindo)

</div>

---

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Features](#-features)
- [Stack Tecnológico](#-stack-tecnológico)
- [Pré-requisitos](#-pré-requisitos)
- [Instalação](#-instalação)
- [Configuração](#-configuração)
- [Uso](#-uso)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Scripts Disponíveis](#-scripts-disponíveis)
- [Banco de Dados](#-banco-de-dados)
- [Segurança](#-segurança)
- [Deploy](#-deploy)
- [Documentação](#-documentação)
- [Contribuindo](#-contribuindo)
- [Licença](#-licença)

---

## 🎯 Sobre o Projeto

O **Admissão Fácil** é uma plataforma SaaS desenvolvida para automatizar e simplificar o processo de admissão de novos funcionários. O sistema oferece uma experiência completa desde o cadastro inicial pelo RH até a finalização do processo admissional pelo colaborador, com coleta automatizada de dados, upload de documentos e acompanhamento em tempo real.

### Problema que Resolve

- ✅ Elimina processos manuais e demorados
- ✅ Centraliza dados e documentos em um único lugar
- ✅ Fornece rastreabilidade completa do processo
- ✅ Facilita coleta de dados completos dos colaboradores
- ✅ Reduz interações entre RH e candidato
- ✅ Padroniza o processo de admissão
- ✅ Suporta múltiplos tipos de contratação (CLT, Estágio, Pró-labore)

### Proposta de Valor

**Para o RH:**
- Redução de 60% no tempo de admissão
- Eliminação de erros manuais
- Visibilidade completa do processo
- Relatórios e analytics

**Para o Colaborador:**
- Processo simples e intuitivo
- Preenchimento no próprio ritmo
- Interface responsiva (mobile-friendly)
- Feedback claro sobre o progresso

---

## ✨ Features

### 🔐 Autenticação e Autorização
- Sistema de autenticação completo com Clerk
- Autenticação de dois fatores (2FA) opcional
- Gerenciamento de perfil de usuário
- Proteção de rotas baseada em autenticação
- Suporte a múltiplos roles (Admin, Gerente, Usuário)
- Localização em português brasileiro

### 👥 Gestão de Funcionários
- Cadastro completo com validação de dados
- Validação automática de CPF, CNPJ, email e telefone
- Geração automática de tokens de acesso
- Suporte a três tipos de contratação:
  - **CLT** - Contrato de trabalho padrão
  - **Estágio** - Contrato de estágio com dados específicos
  - **Pró-labore** - Prestadores de serviço
- Listagem, busca, edição e exclusão de funcionários

### 📝 Processo de Admissão Digital
- Formulário multi-etapas com progresso visual
- Interface tokenizada (acesso via token único e seguro)
- Salvamento automático no localStorage e servidor
- Validação em tempo real de todos os campos
- Coleta de dados pessoais completos:
  - Identificação e informações pessoais
  - Dados de estrangeiro (condicional)
  - Escolaridade e deficiência
  - Documentos pessoais (RG, CNH, Título Eleitoral, etc.)
  - Registro profissional
  - Endereço completo com validação de CEP
  - Contatos de emergência
  - Dependentes (com todos os campos CLT)
- Fluxo condicional para brasileiros e estrangeiros
- Interface totalmente responsiva

### 📁 Gestão de Documentos
- Upload de múltiplos arquivos (PDF, imagens, Word)
- Validação de tipo e tamanho (máximo 10MB)
- Categorização automática por tipo
- Interface drag-and-drop
- **Visualização integrada de PDFs e imagens em modal**
- **Controles de zoom e rotação para imagens**
- Download de documentos
- Detecção de duplicatas via hash SHA-256
- Histórico completo de uploads

### 🔔 Sistema de Notificações
- Notificações em tempo real
- Centro de notificações com histórico
- Contagem de notificações não lidas
- Tipos: funcionário cadastrado, admissão iniciada, documento enviado, admissão concluída

### 📊 Relatórios e Dashboard
- Dashboard administrativo com métricas em tempo real
- **Geração automática de relatórios PDF** por tipo de admissão (CLT, Estágio, Pró-labore)
- **Relatórios completos** com todas as informações da admissão
- **Salvamento automático de relatórios** no banco de dados
- **Geração manual de relatórios** via botão no modal de edição
- Relatórios de admissões por período
- Estatísticas de funcionários cadastrados
- Exportação de dados em CSV
- Filtros avançados por status, departamento e período

### 🏢 Gestão de Organizações
- Cadastro de organizações com busca por CNPJ
- Preenchimento automático de dados via API
- Configuração de email de departamento (emailDp)
- Listagem e edição de organizações

### 📧 Envio de Emails com Anexos
- **Envio automático de emails** após finalização da admissão
- **Anexos automáticos** incluindo:
  - Relatório PDF gerado automaticamente
  - Todos os documentos enviados pelo colaborador
- **Templates de email centralizados** e personalizáveis
- **Botão "Reenviar email DP"** no modal de edição
- Email inclui resumo completo da admissão

### ✅ Validação Avançada de Campos
- **Validação em tempo real** de campos específicos:
  - CNPJ (apenas números)
  - CPF, RG, telefone (apenas números)
  - Email (formato válido)
- **Validação condicional de CNH:**
  - Upload obrigatório quando usuário declara possuir CNH
  - Validação para CLT, Estágio e Pró-labore
- **Validação inteligente de dependentes:**
  - Validação apenas quando "Possui dependentes" = "Sim"

---

## 🛠️ Stack Tecnológico

### Frontend
- **Next.js 14** - Framework React com App Router
- **TypeScript** - Tipagem estática
- **Tailwind CSS** - Framework de estilos utilitários
- **Shadcn/ui** - Componentes de interface moderna
- **Radix UI** - Componentes acessíveis
- **React Hook Form** - Gerenciamento de formulários
- **Zod** - Validação de schemas
- **Sonner** - Sistema de notificações toast
- **date-fns** - Manipulação de datas

### Backend
- **Next.js API Routes** - API RESTful integrada
- **Prisma ORM** - Mapeamento objeto-relacional
- **PostgreSQL** - Banco de dados relacional
- **Server Actions** - Ações do servidor Next.js
- **PDFKit** - Geração de relatórios PDF
- **pdfjs-dist** - Renderização de PDFs no cliente

### Autenticação e Serviços
- **Clerk** - Autenticação e gerenciamento de usuários
- **Resend** - Serviço de email com suporte a anexos
- **PDFKit** - Biblioteca para geração de PDFs

### Infraestrutura
- **Vercel/Railway** - Deploy e hospedagem
- **PostgreSQL** - Banco de dados (Railway)
- **ESLint** - Linting de código
- **Prettier** - Formatação de código
- **Husky** - Git hooks

---

## 📦 Pré-requisitos

Antes de começar, certifique-se de ter instalado:

- **Node.js** 18+ ([Download](https://nodejs.org/))
- **PostgreSQL** 15+ ([Download](https://www.postgresql.org/download/))
- **npm** ou **yarn** ou **pnpm**
- **Git** ([Download](https://git-scm.com/))

### Contas Necessárias

- **Clerk** - Para autenticação ([Criar conta](https://clerk.com/))
- **Resend** - Para envio de emails ([Criar conta](https://resend.com/))

---

## 🚀 Instalação

### 1. Clone o repositório

```bash
git clone <url-do-repositorio>
cd admissao-facil
```

### 2. Instale as dependências

```bash
npm install
# ou
yarn install
# ou
pnpm install
```

### 3. Configure as variáveis de ambiente

Crie um arquivo `.env.local` na raiz do projeto:

```bash
cp .env.example .env.local  # Se existir um arquivo de exemplo
```

Ou crie manualmente o arquivo `.env.local` com o seguinte conteúdo:

```env
# Database
DATABASE_URL="postgresql://usuario:senha@localhost:5432/admissao_facil"

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_...
CLERK_SECRET_KEY=sk_test_...
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/dashboard
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/dashboard

# Email (Resend)
RESEND_API_KEY=re_...
FROM_EMAIL=noreply@suaempresa.com
NOTIFICATION_EMAIL=notificacoes@suaempresa.com

# Webhook Secret (Clerk)
WEBHOOK_SECRET=whsec_...
```

### 4. Configure o banco de dados

```bash
# Gerar o cliente Prisma
npx prisma generate

# Aplicar as migrações
npx prisma migrate dev

# Ou usar db push para desenvolvimento (não recomendado para produção)
npx prisma db push
```

### 5. Execute o projeto em desenvolvimento

```bash
npm run dev
# ou
yarn dev
# ou
pnpm dev
```

### 6. Acesse a aplicação

Abra [http://localhost:3000](http://localhost:3000) no seu navegador.

---

## ⚙️ Configuração

### Configuração do Clerk

1. Acesse [Clerk Dashboard](https://dashboard.clerk.com/)
2. Crie uma nova aplicação
3. Configure as URLs de redirecionamento:
   - Sign-in URL: `http://localhost:3000/sign-in`
   - Sign-up URL: `http://localhost:3000/sign-up`
   - After sign-in URL: `http://localhost:3000/dashboard`
   - After sign-up URL: `http://localhost:3000/dashboard`
4. Copie as chaves de API para o arquivo `.env.local`
5. Configure o webhook para sincronização de usuários (opcional)

### Configuração do Resend

1. Acesse [Resend Dashboard](https://resend.com/)
2. Crie uma conta e verifique seu domínio
3. Gere uma API Key
4. Adicione a chave no arquivo `.env.local`
5. Configure o domínio remetente (`FROM_EMAIL`)

### Configuração do PostgreSQL

1. Instale o PostgreSQL localmente ou use um serviço cloud
2. Crie um banco de dados:
   ```sql
   CREATE DATABASE admissao_facil;
   ```
3. Atualize a `DATABASE_URL` no `.env.local`

---

## 📖 Uso

### Cadastro de Funcionário (RH)

1. Acesse a página de funcionários
2. Clique em "Novo Funcionário"
3. Selecione o tipo de contratação (CLT/Estágio/Pró-labore)
4. Preencha os dados básicos (nome, CPF, email)
5. O sistema gerará automaticamente um token único
6. Copie o link de admissão e envie para o colaborador

### Preenchimento de Admissão (Colaborador)

1. O colaborador acessa o link com token
2. Preenche o formulário multi-etapas com validação em tempo real
3. Os dados são salvos automaticamente a cada etapa
4. Sistema valida campos específicos (CNPJ, números, email)
5. Faz upload dos documentos necessários
6. Sistema valida CNH obrigatória (se declarado "Possui CNH")
7. Finaliza a admissão
8. Sistema gera relatório PDF automaticamente
9. Sistema envia email para RH com anexos (relatório + documentos)
10. O colaborador é redirecionado para página de confirmação

### Acompanhamento (RH)

1. Acesse o dashboard
2. Visualize todas as admissões
3. Filtre por status, período ou tipo
4. Visualize progresso e documentos
5. **Visualize documentos em modal integrado** (PDFs e imagens)
6. **Gere relatório manualmente** via botão no modal de edição
7. **Reenvie email DP** com anexos atualizados
8. Exporte relatórios em CSV

---

## 📁 Estrutura do Projeto

```
admissao-facil/
├── app/                          # App Router do Next.js
│   ├── _actions/                 # Server Actions
│   ├── api/                      # API Routes
│   │   ├── admissions/           # Rotas de admissões
│   │   ├── employees/            # Rotas de funcionários
│   │   ├── organizations/         # Rotas de organizações
│   │   ├── files/                # Rotas de arquivos
│   │   │   └── [id]/view/        # Visualização de arquivos
│   │   ├── admissions/           # Rotas de admissões
│   │   │   ├── [id]/
│   │   │   │   ├── generate-report/  # Geração de relatórios
│   │   │   │   └── resend-email/     # Reenvio de emails
│   │   └── notifications/        # Rotas de notificações
│   ├── admissao/                 # Páginas de admissão
│   │   ├── clt/[token]/          # Formulário CLT
│   │   ├── estagio/[token]/      # Formulário Estágio
│   │   └── prolabore/[token]/    # Formulário Pró-labore
│   ├── admin/                    # Painel administrativo
│   ├── dashboard/                # Dashboard
│   ├── employee/                 # Gestão de funcionários
│   ├── files/                    # Gestão de arquivos
│   └── reports/                  # Relatórios
├── components/                   # Componentes reutilizáveis
│   ├── admin/                    # Componentes administrativos
│   ├── auth/                     # Componentes de autenticação
│   ├── files/                    # Componentes de arquivos
│   ├── notifications/            # Sistema de notificações
│   └── ui/                       # Componentes de interface
│       ├── file-viewer.tsx       # Visualizador de arquivos
│       ├── pdf-viewer-wrapper.tsx # Wrapper para PDFs
│       └── validated-input.tsx   # Input com validação
├── lib/                          # Utilitários e configurações
│   ├── auth.ts                   # Configurações de autenticação
│   ├── prisma.ts                 # Cliente Prisma
│   ├── cnpj-api.ts               # Integração com API de CNPJ
│   ├── email.ts                  # Serviço de email
│   ├── email-templates.ts        # Templates centralizados de email
│   ├── pdf-generator.ts          # Geração de relatórios PDF
│   ├── save-pdf-report.ts        # Salvamento de relatórios no banco
│   ├── validations.ts            # Validações de dados
│   └── utils.ts                  # Funções utilitárias
├── prisma/                       # Schema e migrações
│   ├── schema.prisma             # Modelo de dados
│   └── migrations/               # Migrações do banco
├── hooks/                        # Custom React Hooks
├── docs/                         # Documentação
│   ├── api/                      # Documentação da API
│   │   ├── API.md                # Documentação completa da API
│   │   ├── API_QUICK_START.md    # Guia rápido
│   │   └── openapi.yaml          # Especificação OpenAPI 3.0
│   ├── GUIA_REDIS.md             # Guia de implementação Redis
│   ├── GUIA_RAILWAY_REDIS.md     # Configuração Railway
│   └── ...                       # Outros documentos
├── public/                       # Arquivos estáticos
├── middleware.ts                 # Middleware de autenticação
├── next.config.mjs               # Configuração do Next.js
├── tailwind.config.ts            # Configuração do Tailwind
├── tsconfig.json                 # Configuração do TypeScript
└── package.json                  # Dependências do projeto
```

---

## 🎮 Scripts Disponíveis

```bash
# Desenvolvimento
npm run dev              # Inicia servidor de desenvolvimento

# Produção
npm run build            # Gera build de produção
npm run start            # Inicia servidor de produção

# Qualidade de Código
npm run lint             # Executa ESLint
npm run lint:fix         # Corrige problemas do ESLint

# Testes
npm test                 # Executa testes
npm run test:watch       # Executa testes em modo watch
npm run test:coverage    # Executa testes com coverage

# Banco de Dados
npx prisma generate      # Gera cliente Prisma
npx prisma migrate dev   # Aplica migrações em desenvolvimento
npx prisma migrate deploy # Aplica migrações em produção
npx prisma studio        # Abre Prisma Studio (GUI do banco)
npx prisma db push       # Sincroniza schema com banco (dev apenas)
```

---

## 🗄️ Banco de Dados

### Modelo de Dados

O sistema utiliza PostgreSQL com Prisma ORM. Principais entidades:

- **Organization** - Organizações/Empresas
- **Employee** - Funcionários
- **Admission** - Processos de Admissão
- **AdmissionCLT** - Dados específicos CLT
- **AdmissionEstagio** - Dados específicos Estágio
- **AdmissionProlabore** - Dados específicos Pró-labore
- **EmployeePersonalDataCLT** - Dados pessoais CLT
- **EmployeePersonalDataEstagio** - Dados pessoais Estágio
- **EmployeePersonalDataProlabore** - Dados pessoais Pró-labore
- **DependentCLT** - Dependentes CLT
- **DependentsEstagio** - Dependentes Estágio
- **DependentsProlabore** - Dependentes Pró-labore
- **File** - Documentos e arquivos
- **Notification** - Notificações do sistema

### Migrações

```bash
# Criar nova migração
npx prisma migrate dev --name nome_da_migracao

# Aplicar migrações em produção
npx prisma migrate deploy

# Reverter última migração (dev apenas)
npx prisma migrate reset
```

### Prisma Studio

Visualize e edite dados do banco através de uma interface gráfica:

```bash
npx prisma studio
```

---

## 🔐 Segurança

### Boas Práticas Implementadas

- ✅ Autenticação robusta com Clerk
- ✅ Proteção de rotas via middleware
- ✅ Validação de dados no frontend e backend
- ✅ Sanitização de uploads de arquivos
- ✅ Tokens únicos e seguros para admissões
- ✅ HTTPS em todas as comunicações
- ✅ Validação Zod em rotas de API
- ✅ Proteção CSRF

### Variáveis de Ambiente

⚠️ **Nunca commite arquivos `.env` ou `.env.local` no repositório!**

- Use variáveis de ambiente em produção
- Não inclua chaves, senhas ou tokens reais em documentação
- Use serviços de gerenciamento de secrets (Vercel, Railway, etc.)

### Compliance

- ✅ Conformidade com LGPD (Lei Geral de Proteção de Dados)
- ✅ Logs de auditoria
- ✅ Backup automático de dados
- ✅ Política de retenção de dados

---

## 🚀 Deploy

### Vercel (Recomendado)

1. Conecte seu repositório ao Vercel
2. Configure as variáveis de ambiente
3. Deploy automático a cada push

### Railway

1. Conecte seu repositório ao Railway
2. Configure PostgreSQL como serviço
3. Adicione variáveis de ambiente
4. Deploy automático

### Variáveis de Ambiente para Produção

Certifique-se de configurar todas as variáveis necessárias:

```env
DATABASE_URL=...
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=...
CLERK_SECRET_KEY=...
RESEND_API_KEY=...
FROM_EMAIL=...
NOTIFICATION_EMAIL=...
WEBHOOK_SECRET=...
```

---

## 📚 Documentação

Documentação adicional disponível no repositório:

### Documentação Principal
- **[PRD - Product Requirements Document](./PRD_ADMISSAO_FACIL.md)** - Documento completo de requisitos do produto
- **[Documentação do Banco de Dados](./DOCUMENTACAO_BANCO_DADOS.md)** - Estrutura e relacionamentos do banco
- **[Disaster Recovery e Continuidade](./DISASTER_RECOVERY_CONTINUIDADE.md)** - Plano de recuperação de desastres

### Documentação da API
- **[Documentação Completa da API](./docs/api/API.md)** - Documentação completa da API REST com exemplos
- **[Guia Rápido da API](./docs/api/API_QUICK_START.md)** - Guia rápido para começar a usar a API
- **[Especificação OpenAPI](./docs/api/openapi.yaml)** - Especificação OpenAPI 3.0 da API (Swagger/Redoc)

### Outros Documentos
- **[Guia Redis](./docs/GUIA_REDIS.md)** - Guia de implementação do Redis
- **[Guia Railway e Redis](./docs/GUIA_RAILWAY_REDIS.md)** - Configuração no Railway
- **[Configuração de Email](./docs/README-EMAIL-SETUP.md)** - Setup do Resend
- **[Design Documentation](./docs/DESIGN_DOCUMENTATION.md)** - Documentação de design

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Para contribuir:

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

### Padrões de Código

- Siga os padrões do ESLint e Prettier
- Escreva testes para novas funcionalidades
- Documente mudanças significativas
- Mantenha commits descritivos

---

## 🐛 Troubleshooting

### Problemas Comuns

**Erro ao conectar ao banco de dados:**
- Verifique se o PostgreSQL está rodando
- Confirme a `DATABASE_URL` no `.env.local`
- Teste a conexão: `npx prisma db pull`

**Erro de autenticação Clerk:**
- Verifique as chaves no `.env.local`
- Confirme as URLs de redirecionamento no dashboard do Clerk

**Erro ao enviar emails:**
- Verifique a `RESEND_API_KEY`
- Confirme que o domínio está verificado no Resend
- Verifique os logs do servidor

**Erro ao gerar Prisma Client:**
```bash
npx prisma generate
```

**Resetar banco de dados (dev apenas):**
```bash
npx prisma migrate reset
```

**Erro ao gerar PDF (PDFKit):**
- Verifique se `pdfkit` está instalado: `npm install pdfkit`
- Verifique configuração do Next.js em `next.config.mjs`
- Verifique se fontes do PDFKit estão acessíveis

**Erro ao visualizar PDF no modal:**
- Verifique se `pdfjs-dist` está instalado: `npm install pdfjs-dist`
- Limpe cache do navegador
- Verifique logs do console para erros específicos

---

## 📄 Licença

**Copyright © 2025 Bh Hub Tech. Todos os direitos reservados.**

Este software é propriedade da **Bh Hub Tech** e está protegido por leis de direitos autorais. O uso, distribuição ou modificação deste código sem autorização expressa é estritamente proibido.

### Termos de Uso

- ✅ Uso interno pela organização licenciada
- ✅ Modificações para necessidades específicas do cliente
- ❌ Redistribuição ou revenda sem autorização
- ❌ Uso em projetos concorrentes
- ❌ Engenharia reversa para fins comerciais

---

## 📞 Suporte

Para suporte técnico ou dúvidas:

- **Issues**: Utilize o sistema de issues do repositório
- **Documentação**: 
  - [PRD](./PRD_ADMISSAO_FACIL.md) - Requisitos do produto
  - [Documentação do Banco de Dados](./DOCUMENTACAO_BANCO_DADOS.md) - Estrutura do banco
  - [Documentação da API](./docs/api/API.md) - API REST completa
  - [Disaster Recovery](./DISASTER_RECOVERY_CONTINUIDADE.md) - Plano de recuperação
- **Email**: Utilize os canais internos do projeto

---

## 📝 Changelog

### Versão 2.2.0 (Janeiro 2025)

**🔧 Melhorias:**
- ✅ Exibição de versão do app no sidebar (ao lado do nome "Admissão Fácil")
- ✅ Remoção de link clicável do logo e nome no header do sidebar
- ✅ Criação de helper centralizado para gerenciamento de versão (`lib/version.ts`)
- ✅ Gerenciamento de planos e user aprimorados
- ✅ Melhoria completa da UI e UX da plataforma

### Versão 1.1 (Dezembro 2024)

**✨ Novas Funcionalidades:**
- ✅ Geração automática de relatórios PDF (CLT, Estágio, Pró-labore)
- ✅ Salvamento de relatórios no banco de dados
- ✅ Envio automático de emails com anexos (relatório + documentos)
- ✅ Visualizador integrado de arquivos (PDF e imagens) em modal
- ✅ Botões de "Gerar relatório" e "Reenviar email DP" no modal de edição
- ✅ Validação avançada de campos (CNPJ, números, email)
- ✅ Validação obrigatória de CNH quando declarado
- ✅ Templates de email centralizados

**🔧 Melhorias:**
- Layout otimizado de relatórios PDF com quebra de página inteligente
- Validação aprimorada de campos de entrada
- Interface de visualização de arquivos melhorada
- Processo de finalização otimizado

**🐛 Correções:**
- Correção de bugs no processo de finalização
- Correção de layout de PDFs gerados
- Correção de validação de dependentes
- Correção de espaçamento em componentes de UI

---

## 🙏 Agradecimentos

- [Next.js](https://nextjs.org/) - Framework React
- [Prisma](https://www.prisma.io/) - ORM moderno
- [Clerk](https://clerk.com/) - Autenticação
- [Shadcn/ui](https://ui.shadcn.com/) - Componentes de interface
- [Resend](https://resend.com/) - Serviço de email
- [PDFKit](https://pdfkit.org/) - Geração de PDFs
- [PDF.js](https://mozilla.github.io/pdf.js/) - Renderização de PDFs

---

<div align="center">

**Desenvolvido com ❤️ pela equipe Bh Hub Tech**

[⬆ Voltar ao topo](#-admissão-fácil)

</div>

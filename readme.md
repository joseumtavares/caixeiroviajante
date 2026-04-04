# 📍 VisitaPRO v3.1

Sistema de gestão de visitas em campo com mapa interativo OpenStreetMap.
Interface moderna, responsiva e instalável como PWA — funciona offline e sincroniza com o Supabase quando há conexão.

---

## 🔑 Acesso ao Sistema

| Campo   | Valor                 |
|---------|-----------------------|
| Usuário | `admin`               |
| Senha   | `********` *(oculta)* |
| Sessão  | 8 horas               |

> **🔐 Segurança v3.1:** a senha nunca é armazenada em texto puro. O sistema usa PBKDF2-SHA256 no navegador e bcrypt no servidor (Supabase). Após 5 tentativas incorretas, a conta é bloqueada por 15 minutos automaticamente.

---

## 🚀 Como Implantar

### Vercel (recomendado)
1. Coloque `index.html` e `vercel.json` na raiz do repositório GitHub.
2. Conecte o repositório ao [Vercel](https://vercel.com).
3. Selecione o framework: **Outro**.
4. Faça o deploy — pronto.

### Banco de Dados Supabase
1. Crie um projeto em [supabase.com](https://supabase.com).
2. Execute os arquivos SQL **em ordem** no SQL Editor do Supabase:
   - `new_schema.sql` — schema base (clientes + usuários)
   - `migration_v3_km.sql` — tabela de controle de KM
   - `migration_v31_security.sql` — bcrypt, RLS por usuário, proteção brute-force
3. No VisitaPRO, clique no indicador de status no cabeçalho.
4. Informe a **URL** e a **chave anônima** do seu projeto.
5. Teste a conexão — a migração de dados de KM ocorre automaticamente.

> **⚠️ Regra de migration:** aplique sempre as migrations em ordem. Nunca re-execute o schema completo em banco já existente.

---

## 🛠️ Funcionalidades

### v3.1 — Segurança e Sincronização de KM *(versão atual)*
- 🔐 **Autenticação reforçada** — PBKDF2-SHA256 com 200.000 iterações no browser; bcrypt no servidor via Supabase RPC. A senha nunca aparece no código-fonte.
- 🛡️ **Proteção brute-force** — bloqueio automático de 15 minutos após 5 tentativas incorretas, tanto no browser quanto no banco de dados.
- 🔄 **Suporte dual SHA-256 / bcrypt** — usuários antigos continuam entrando com SHA-256 legado; novos usuários e redefinições de senha usam bcrypt automaticamente. Migração transparente, sem resetar senhas de ninguém.
- 🚗 **Sync de KM com Supabase** — registros salvos e excluídos agora são enviados ao banco em background. Funciona offline; sincroniza quando a conexão é restaurada.
- 🗄️ **Migração automática de KM** — na primeira entrada após conectar o Supabase, todos os registros de KM que estavam apenas no `localStorage` são enviados automaticamente para o banco. Executa somente uma vez.

### v3.0 — Controle de KM
- 🚗 **Controle de KM** — hodômetro inicial/final, valor de combustível, consumo médio, cálculo de custo por km, resumo mensal e histórico completo.
- 🗂️ **Navegação por abas no cadastro** — formulário de cliente organizado em 3 abas: Dados, Localização e Observações.

### Funcionalidades gerais
- 🗺️ Mapa OpenStreetMap com marcadores coloridos por status.
- 🔍 Busca de endereço via geocodificação (Nominatim).
- 🔗 Colar link de localização (Google Maps, WhatsApp, Waze).
- 👤 Campo "Indicado por" no cadastro de clientes.
- 🔄 Sincronização com Supabase (modo local, híbrido ou nuvem).
- 📱 Instalável como PWA (Android, iOS, Desktop).
- 📊 Exportação CSV para relatórios.

---

## 🗂️ Estrutura de Arquivos

```
├── index.html                   ← Aplicação completa (single-file)
├── vercel.json                  ← Configuração de deploy Vercel
├── new_schema.sql               ← Schema inicial do banco de dados
├── migration_v3_km.sql          ← Migration v3: tabela de controle de KM
├── migration_v31_security.sql   ← Migration v3.1: bcrypt, RLS, brute-force
└── readme.md                    ← Este arquivo
```

---

## 🗃️ Histórico de Migrations

| Arquivo                       | Versão | Descrição                                              |
|-------------------------------|--------|--------------------------------------------------------|
| `new_schema.sql`              | v2.0   | Schema base: clientes + usuários                       |
| `migration_v3_km.sql`         | v3.0   | Tabela `visitapro_km` para controle de KM              |
| `migration_v31_security.sql`  | v3.1   | bcrypt, RLS por usuário, brute-force no servidor       |

> Aplique sempre as migrations em ordem. Nunca pule versões.

---

## 🚧 Roadmap — Futuras Implementações

| Prioridade | Funcionalidade | Descrição |
|------------|---------------|-----------|
| 🔴 Alta    | **Registro Offline robusto** | Fila de sincronização ao reconectar |
| 🔴 Alta    | **Localização em Tempo Real** | Acompanhamento da equipe externa |
| 🟡 Média   | **Checklist Personalizável** | Formulários dinâmicos por visita |
| 🟡 Média   | **Relatórios Automatizados** | Filtros por período, colaborador ou cliente |
| 🔵 Baixa   | **Galeria de Fotos Georreferenciadas** | Fotos associadas a coordenadas GPS |
| 🔵 Baixa   | **Roteirização** | Otimização de rota entre clientes no mapa |
| 🔵 Baixa   | **Gestão de Agendas** | Planejamento centralizado de visitas |

---

## 🔗 Links Úteis

- [VisitaPRO no GitHub](https://github.com)
- [Documentação do Supabase](https://supabase.com/docs)
- [Mapas OpenStreetMap](https://www.openstreetmap.org)
- [Leaflet.js](https://leafletjs.com)

# 📍 VisitaPRO v3.0

Sistema de gestão de visitas em campo com mapa interativo OpenStreetMap.
Interface moderna, responsiva e instalável como PWA — funciona offline e sincroniza com o Supabase quando há conexão.

---

## 🔑 Acesso ao Sistema

| Campo   | Valor                        |
|---------|------------------------------|
| Usuário | `admin`                      |
| Senha   | `********` *(oculta)*        |
| Sessão  | 8 horas                      |

---

## 🚀 Como Implantar

### Vercel (recomendado)
1. Coloque `index.html` e `vercel.json` na raiz do repositório GitHub.
2. Conecte o repositório ao [Vercel](https://vercel.com).
3. Selecione o framework: **Outro**.
4. Faça o deploy — pronto.

### Banco de Dados Supabase
1. Crie um projeto em [supabase.com](https://supabase.com).
2. Execute o arquivo `new_schema.sql` no SQL Editor do Supabase.
3. No VisitaPRO, clique no indicador de status no cabeçalho.
4. Informe a **URL** e a **chave anônima** do seu projeto.
5. Teste a conexão e sincronize os dados.

> **⚠️ Regra de migration:** Sempre que uma nova coluna ou tabela for adicionada, um arquivo `migration_vX.sql` separado será gerado. Execute-o no SQL Editor do Supabase — nunca re-execute o schema completo em banco já existente.

---

## 🛠️ Funcionalidades

### v3.0 — Novidades desta versão
- 🚗 **Controle de KM** — Registro de hodômetro inicial/final, valor de combustível, consumo médio, cálculo automático de custo por km, resumo mensal e histórico completo.
- 🗂️ **Navegação por abas no cadastro** — Formulário de cliente reorganizado em 3 abas: **Dados**, **Localização** e **Observações**, com barra de rolagem visível e cabeçalho/rodapé fixos.

### Funcionalidades gerais
- 🗺️ Mapa OpenStreetMap com marcadores coloridos por status.
- 🔍 Busca de endereço via geocodificação (Nominatim).
- 🔗 Colar link de localização (Google Maps, WhatsApp, Waze).
- 👤 Campo "Indicado por" no cadastro de clientes.
- 🔄 Sincronização com Supabase (modo local, híbrido ou nuvem).
- 📱 Instalável como PWA (Android, iOS, Desktop).
- 📊 Exportação CSV para relatórios.
- 🔐 Login com hash SHA-256 e sessão de 8h.

---

## 🗂️ Estrutura de Arquivos

```
├── index.html          ← Aplicação completa (single-file)
├── vercel.json         ← Configuração de deploy Vercel
├── new_schema.sql      ← Schema inicial do banco de dados
├── migration_v3_km.sql ← Migration v3: tabela de controle de KM
└── readme.md           ← Este arquivo
```

---

## 🗃️ Histórico de Migrations

| Arquivo               | Versão | Descrição                                 |
|-----------------------|--------|-------------------------------------------|
| `new_schema.sql`      | v2.0   | Schema base: clientes + usuários          |
| `migration_v3_km.sql` | v3.0   | Tabela `visitapro_km` para controle de KM |

> Aplique sempre as migrations em ordem. Nunca pule versões.

---

## 🚧 Roadmap — Futuras Implementações

| Prioridade | Funcionalidade | Descrição |
|------------|---------------|-----------|
| 🟡 Média   | **Sync KM → Supabase** | Sincronização dos registros de KM com o banco (v3.1) |
| 🟡 Média   | **Checklist Personalizável** | Formulários dinâmicos por visita |
| 🟡 Média   | **Relatórios Automatizados** | Filtros por período, colaborador ou cliente |
| 🔵 Baixa   | **Galeria de Fotos Georreferenciadas** | Fotos associadas a coordenadas GPS |
| 🔵 Baixa   | **Roteirização** | Otimização de rota entre clientes no mapa |
| 🔵 Baixa   | **Gestão de Agendas** | Planejamento centralizado de visitas |
| 🔴 Alta    | **Registro Offline robusto** | Fila de sincronização ao reconectar |
| 🔴 Alta    | **Localização em Tempo Real** | Acompanhamento da equipe externa |

---

## 🔗 Links Úteis

- [VisitaPRO no GitHub](https://github.com)
- [Documentação do Supabase](https://supabase.com/docs)
- [Mapas OpenStreetMap](https://www.openstreetmap.org)
- [Leaflet.js](https://leafletjs.com)

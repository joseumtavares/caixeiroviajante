# VisitaPRO v2.0

Sistema de gestão de visitas em campo com mapa interativo OpenStreetMap.

## Login
- **Usuário:** admin
- **Senha:** J12u08m19t79@
- Sessão dura 8 horas

## Deploy na Vercel
1. Coloque `index.html` e `vercel.json` na raiz do repositório GitHub
2. Conecte o repositório na Vercel
3. Framework Preset: **Other**
4. Faça o Deploy

## Banco de Dados Supabase
1. Crie um projeto em supabase.com
2. Execute o arquivo `schema.sql` no SQL Editor
3. No VisitaPRO, clique no indicador de status no header
4. Informe a URL e a Anon Key do seu projeto
5. Teste a conexão e sincronize os dados

## Funcionalidades
- Mapa OpenStreetMap com marcadores coloridos por status
- Busca de endereço via geocoding (Nominatim)
- Colar link de localização (Google Maps, WhatsApp, Waze)
- Campo "Indicado por" no cadastro
- Sincronização com Supabase
- Instalável como PWA (Android, iOS, Desktop)
- Exportação CSV

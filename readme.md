📍 VisitaPRO v2.0

Sistema de gestão de visitas em campo com mapa interativo OpenStreetMap.
Este sistema permite o controle de visitas, integração com o banco de dados Supabase e muito mais. Tudo em uma interface moderna e intuitiva, com suporte para dispositivos móveis e desktop.

🔑 Conecte-se
Usuário: admin
Senha: ******** (oculta para segurança)
Sessão dura: 8 horas
🚀 Como Implantar
Implantação na Vercel
Coloque o arquivo index.html e vercel.json na raiz do seu repositório GitHub.
Conecte o repositório ao Vercel
.
No Vercel, selecione a configuração do framework: Outro.
Faça o deploy do projeto.
Banco de Dados Supabase
Crie um projeto em supabase.com
.
Execute o arquivo schema.sql no SQL Editor do Supabase.
No VisitaPRO, clique no indicador de status no cabeçalho.
Informe a URL e a chave anônima do seu projeto.
Teste a conexão e sincronize os dados.
🛠️ Funcionalidades
🗺️ Mapa OpenStreetMap com marcadores coloridos por status.
🔍 Busca de Endereço via geocodificação (Nominatim).
🔗 Colar link de localização (Google Maps, WhatsApp, Waze).
👤 Campo "Indicado por" no cadastro de clientes.
🔄 Sincronização com Supabase para armazenamento seguro.
📱 Instalável como PWA (Android, iOS, Desktop).
📊 Exportação CSV para relatórios.
🗂️ Estrutura do Sistema
.
├── public/
│   ├── index.html
│   └── vercel.json
├── src/
│   ├── components/
│   │   ├── Header.js
│   │   └── ClientList.js
│   ├── services/
│   │   ├── supabase.js
│   │   └── geolocation.js
│   ├── utils/
│   │   └── mapUtils.js
│   └── styles/
│       └── style.css
└── README.md
🚧 Futuras Implementações
🔧 Controle de KM Rodado
Registro manual de quilometragem no início e no fim das visitas.
Inclusão do valor do combustível e cálculo de custos.
📝 Checklist Personalizável
Formulários dinâmicos para coleta de dados específicos durante as visitas.
🌐 Registro Offline
Capacidade de registrar atividades sem conexão e sincronizar os dados quando a conexão for restaurada.
📸 Galeria de Fotos Georreferenciadas
Captura de fotos durante a visita, associadas a coordenadas GPS.
📍 Mapa de Clientes e Roteirização
Visualização interativa da carteira de clientes e otimização de rotas para visitas.
💬 Relatórios Automatizados
Geração de relatórios instantâneos com filtros por período, colaborador ou cliente.
📡 Localização em Tempo Real
Acompanhamento da posição dos colaboradores da equipe externa em tempo real.
📅 Gestão de Agendas
Planejamento centralizado de visitas e compromissos.
🔗 Links Úteis
VisitaPRO no GitHub
Documentação do Supabase
Mapas OpenStreetMap
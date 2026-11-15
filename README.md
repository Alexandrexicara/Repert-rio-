# Repertorio Karaoke

Plataforma híbrida: painel web + API PostgreSQL + aplicativo Windows Companion.

- Web: React/Vite para conta, biblioteca, repertórios e configurações.
- API: Express + PostgreSQL (Neon), autenticação e sincronização de metadados.
- Companion: Electron, monitoramento da pasta de downloads e reprodução local de vídeos.
- Os vídeos permanecem no computador; a nuvem guarda listas e metadados.

## Integração 4K
Configure o 4K Video Downloader para salvar na pasta monitorada pelo Companion. A documentação oficial explica como selecionar a pasta: https://www.4kdownload.com/faq/faq-how-do-i-change-the-output-folder

A integração usa monitoramento de arquivos, não uma API privada do 4K. Baixe e reproduza somente conteúdo autorizado.

## Desenvolvimento
Node.js 20+, PostgreSQL/Neon. Configure as variáveis do arquivo .env.example. Instale dependências com npm install. O deploy exige configurar Neon, Render e Netlify e gerar o instalador Windows.

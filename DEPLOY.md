# Publicação e primeira instalação

## 1. Banco Neon
1. Crie um projeto PostgreSQL no Neon.
2. Execute todo o conteúdo de database/schema.sql no SQL Editor.
3. Copie a connection string PostgreSQL com SSL.

## 2. API no Render
1. Crie um Web Service conectado a este repositório.
2. Root Directory: apps/api
3. Build Command: npm install
4. Start Command: npm start
5. Variáveis: DATABASE_URL (Neon), JWT_SECRET (segredo aleatório longo) e WEB_ORIGIN (URL final da Netlify).
6. Após publicar, teste https://SUA-API/health.

## 3. Web na Netlify
1. Importe o mesmo repositório.
2. Build command: npm run build -w apps/web
3. Publish directory: apps/web/dist
4. Defina VITE_API_URL com a URL HTTPS do serviço Render.
5. Atualize WEB_ORIGIN no Render com a URL da Netlify.

## 4. Companion Windows
No Windows com Node.js instalado:
1. Clone o repositório.
2. Na raiz, execute npm install.
3. Execute npm run dev:desktop para testar.
4. Para gerar instalador, entre em apps/desktop e execute npm run build.
5. O instalador NSIS será gerado na pasta de saída do electron-builder.

## 5. Conectar 4K Video Downloader
1. No Companion, informe a URL pública da API e entre com a mesma conta usada no site.
2. Escolha a pasta que o 4K usa para salvar os vídeos.
3. No 4K Video Downloader, abra Smart Mode e selecione essa pasta no campo Save To.
4. Aguarde o download terminar. O Companion detecta o arquivo, calcula uma impressão digital e sincroniza título, artista, tamanho e nome do arquivo. O vídeo permanece local.

## Limitações conhecidas desta primeira entrega
- A sincronização na nuvem guarda metadados e repertórios, não transfere os vídeos entre computadores.
- O Companion reproduz os arquivos locais; o painel web organiza a biblioteca e os repertórios.
- MKV/AVI/formatos com codecs não suportados pelo mecanismo de vídeo do Windows podem exigir um player/codec compatível. MP4 H.264/AAC é a opção mais compatível.
- A integração com 4K é por pasta monitorada, não por API interna ou controle remoto do programa.
- Antes de distribuir publicamente, configure HTTPS, backups do Neon, política de privacidade e assinatura do instalador. Use somente mídia que você tenha direito de baixar e exibir.

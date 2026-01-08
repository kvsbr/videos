Como Hospedar VSL de Alta Performance (HLS/m3u8) no GitHub
Este guia serve para lembrar o processo de transformar um vídeo MP4 comum em um formato de streaming (igual Netflix/VTurb) e hospedá-lo gratuitamente usando GitHub + jsDelivr.

1. Conversão (MP4 → HLS)
O arquivo .m3u8 não é o vídeo, é apenas um índice. O vídeo real é quebrado em vários pedaços .ts.

Acesse um conversor online (ex: Converter.app, CloudConvert ou procure "Convert MP4 to HLS").

Suba seu arquivo .mp4.

Configuração: Se o site pedir, selecione "HLS" ou ".m3u8".

Download: Baixe o arquivo final. Geralmente vem um .zip.

Extraia: Ao abrir a pasta, você deve ver:

1 arquivo .m3u8 (ex: playlist.m3u8 ou index.m3u8).

Vários arquivos .ts (ex: seg-1.ts, seg-2.ts...).

2. Organização no GitHub
Nunca jogue os arquivos soltos na raiz do repositório, pois os nomes podem se repetir e bagunçar tudo.

Acesse seu repositório de vídeos (Ex: videos).

Clique em Add file > Create new file.

Crie uma nova pasta digitando o nome dela seguido de barra /.

Exemplo: video-vsl-oferta-01/readme.md (Isso cria a pasta automaticamente).

Entre na pasta que acabou de criar.

Clique em Add file > Upload files.

Arraste TODOS os arquivos da conversão (o .m3u8 + todos os .ts) para lá.

Clique no botão verde Commit changes.

3. Gerando o Link (O Pulo do Gato)
O link do GitHub não serve para streaming. Usamos o jsDelivr para transformá-lo em um CDN rápido.

A estrutura do link é sempre esta:

Plaintext

https://cdn.jsdelivr.net/gh/{USUARIO}/{REPOSITORIO}/{PASTA}/{ARQUIVO}.m3u8
Exemplo Real (Baseado no seu teste):
Usuário: kvsbr

Repositório: videos

Pasta: video-up3-ozempic

Arquivo: playlist.m3u8

Link Final:

Plaintext

https://cdn.jsdelivr.net/gh/kvsbr/videos/video-up3-ozempic/playlist.m3u8

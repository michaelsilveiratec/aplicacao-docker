🚀 Passo a Passo da Publicação da Imagem no Docker Hub

Aluno: Michael Silveira

🏗️ 1. Build da Imagem

O primeiro passo foi construir a imagem Docker usando o Dockerfile:

docker build -t meu-app .


O Docker carregou o Dockerfile, baixou a imagem base alpine:latest e gerou a imagem meu-app.

🧪 2. Teste da Imagem Localmente
docker run --rm meu-app


Saída exibida:
👉 Minha imagem funciona!

🔐 3. Login no Docker Hub
docker login


Login autenticado com o usuário michaelsilveiratec.

🏷️ 4. Criação da Tag para o Docker Hub
docker tag meu-app:latest michaelsilveiratec/meu-app:1.0


Verificação:

docker images

📤 5. Envio da Imagem para o Docker Hub (Push)
docker push michaelsilveiratec/meu-app:1.0


Imagem enviada com sucesso.

🧹 6. Remoção das Imagens Locais
docker rmi meu-app:latest
docker rmi michaelsilveiratec/meu-app:1.0


Imagens removidas corretamente.

📥 7. Baixando a Imagem do Docker Hub (Pull)
docker pull michaelsilveiratec/meu-app:1.0


Download realizado com sucesso.

⚠️ 8. Tentativa de Re-tag Após Remoção

Erro ao tentar re-tag:

docker tag meu-app:latest michaelsilveiratec/meu-app:1.0
Error response from daemon: No such image: meu-app:latest


A imagem não existia mais localmente.

🔄 9. Recuperação da Tag

Recriação da tag:

docker tag michaelsilveiratec/meu-app:1.0 meu-app:latest


Ambas as tags reapareceram após:

docker images

🚢 10. Publicação da Tag latest
docker tag meu-app:latest michaelsilveiratec/meu-app:latest
docker push michaelsilveiratec/meu-app:latest


Tag latest publicada com sucesso.

✅ Resumo Final

Você realizou com sucesso:

✔ Build da imagem
✔ Teste local
✔ Login no Docker Hub
✔ Criação das tags 1.0 e latest
✔ Push das tags
✔ Remoção e re-tag
✔ Pull final para validação

🌐 Sua imagem está disponível em:

👉 https://hub.docker.com/repository/docker/michaelsilveiratec/meu-app

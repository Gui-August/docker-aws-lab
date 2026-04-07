\# 🚀 SRE Lab — Docker + AWS (ECR + EC2)



\---



\## 📌 Sobre o Projeto



Este laboratório foi desenvolvido com o objetivo de praticar conceitos reais de \*\*SRE/DevOps\*\*, implementando um fluxo completo de deploy:



```bash

Local → Docker → AWS ECR → EC2 → Aplicação Online

```



A aplicação é simples, porém o foco está na \*\*infraestrutura e no processo de deploy\*\*, simulando um ambiente de produção.



\---



\## 🧱 Arquitetura



```bash

\[ Local Machine ]



\[ Docker Build ]



\[ AWS ECR (Registry) ]



\[ EC2 Instance ]


\[ Container Nginx rodando aplicação ]


\[ Acesso via Browser ]

```



\---



\## 🐳 Tecnologias Utilizadas



\* Docker

\* AWS ECR (Elastic Container Registry)

\* AWS EC2

\* IAM Roles

\* Nginx

\* Linux (Amazon Linux)



\---



\## 🚀 Deploy Realizado



\### 1️⃣ Build da imagem Docker



```bash

docker build -t sre-aws-lab .

```



\---



\### 2️⃣ Tag da imagem



```bash

docker tag sre-aws-lab:latest <ACCOUNT\_ID>.dkr.ecr.us-east-1.amazonaws.com/sre-aws-lab:latest

```



\---



\### 3️⃣ Login no ECR



```bash

aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <ACCOUNT\_ID>.dkr.ecr.us-east-1.amazonaws.com

```



\---



\### 4️⃣ Push da imagem



```bash

docker push <ACCOUNT\_ID>.dkr.ecr.us-east-1.amazonaws.com/sre-aws-lab:latest

```



\---



\### 5️⃣ Execução na EC2



```bash

docker run -d -p 80:80 <ACCOUNT\_ID>.dkr.ecr.us-east-1.amazonaws.com/sre-aws-lab:latest

```



\---



\## 🌐 Resultado



A aplicação foi publicada com sucesso e pode ser acessada via navegador:



```bash

http://<EC2-PUBLIC-IP>

```



\---



\## 🧠 Aprendizados



Durante este laboratório, foram praticados conceitos essenciais:



\* Containerização de aplicações

\* Build e gerenciamento de imagens Docker

\* Integração com AWS (ECR)

\* Uso de IAM Roles (segurança)

\* Deploy em infraestrutura cloud (EC2)

\* Troubleshooting de erros reais



\---



\## ⚠️ Problemas Resolvidos



Este projeto incluiu resolução de problemas comuns em ambientes reais:



\* Erro de encoding no Dockerfile (Windows vs Linux)

\* Falha no build do Docker (RST\_STREAM)

\* Permissões no Docker (`docker.sock`)

\* Credenciais AWS ausentes na EC2

\* Configuração de IAM Role



\---



\## 🔐 Segurança



\* Uso de IAM Role ao invés de credenciais locais

\* Prática alinhada com ambientes produtivos

\* Evita exposição de Access Keys



\---



\## 📈 Próximos Passos



\* Monitoramento com Prometheus + Grafana

\* Load Balancer (ALB)

\* HTTPS (SSL)

\* Automação com Terraform

\* Pipeline CI/CD



\---



\## 👨‍💻 Autor



Projeto desenvolvido como prática de estudos em \*\*SRE/DevOps\*\*.



🔗 Repositório:

https://github.com/Gui-August/sre-lab



\---



\## ⭐ Contribuição



Sinta-se à vontade para clonar, estudar e evoluir este projeto.



\---



\## 🏁 Conclusão



Este laboratório representa um cenário real de deploy moderno utilizando Docker e AWS, sendo uma excelente base para evolução em SRE e DevOps.



\---




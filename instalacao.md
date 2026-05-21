# ⚙️ Guia de Instalação do VeroRoute

Você pode instalar o VeroRoute em hospedagem compartilhada (cPanel e similares) ou em um ambiente isolado com Docker. Em ambos os casos, o processo é simples e direto.

[🏠 Voltar para o Início](README.md) | [Próximo: Provedores Suportados ➡️](provedores.md)

---

## ⚠️ Atenção: Licença por Domínio

A licença do VeroRoute é vinculada ao domínio **exato** onde o sistema será usado. Antes da ativação, defina com precisão o domínio principal da instalação (exemplo: `https://ia.seudominio.com`). Evite ativar em um domínio temporário se a operação real for ocorrer em outro endereço.

### Requisitos Básicos
* Domínio ou subdomínio já apontado para o seu servidor.
* PHP e MySQL (para ambiente web tradicional) ou Docker.
* **ionCube Loader 13 ou superior** habilitado no ambiente.
* Chaves de API dos provedores que você deseja utilizar nas rotas.

---

## 1️⃣ Instalação em Hospedagem Compartilhada (cPanel)

Essa é a forma mais rápida para subir o sistema em ambientes tradicionais.

1. Envie todos os arquivos do projeto para a pasta raiz do seu domínio ou subdomínio.
2. Crie um banco de dados MySQL e tenha em mãos: *host, nome do banco, usuário e senha*.
3. Confirme com sua hospedagem que o **ionCube Loader 13+** está ativo na sua versão do PHP.
4. Acesse no seu navegador: `https://seu-dominio.com/install.php`
5. Preencha os campos da instalação cuidadosamente.
6. Ao finalizar, **remova ou bloqueie** o arquivo `install.php` por segurança.

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/samucamg/imagens/Outros/2026/05/veroroute_install_1779313611.jpg" alt="Tela de instalação do VeroRoute" width="80%">
  <br><i>Tela do instalador onde você informa os dados do banco e domínio.</i>
</div>

---

## 2️⃣ Instalação com Docker

Em Docker, você garante um ambiente previsível, persistente e com portas bem definidas. É a recomendação oficial para quem busca maior segurança e escalabilidade.

### Passo a passo rápido:

```bash
# 1) Acesse a pasta do projeto no seu servidor
cd /caminho/do/veroroute

# 2) Revise o arquivo docker-compose.yml
# Verifique: portas expostas, volumes do banco/aplicação e credenciais do MySQL.

# 3) Suba os containers em background
docker compose up -d

# 4) Verifique se os serviços estão rodando
docker compose ps

# 5) Acompanhe os logs (se necessário)
docker compose logs -f
```

6. Após o ambiente subir e o proxy reverso (como Traefik/Nginx) estiver apontando corretamente para o container web, acesse: `https://seu-dominio.com/install.php`.
7. Finalize a instalação gráfica através do navegador.

### ✅ Checklist Pós-Instalação (Docker)
* Use volumes persistentes para o banco de dados.
* Certifique-se de não publicar em um domínio provisório se a licença for final.
* Valide o login no admin, cadastre as primeiras chaves e faça um teste no painel antes de apontar suas aplicações.

---
[🏠 Voltar para o Início](README.md) | [Próximo: Provedores Suportados ➡️](provedores.md)

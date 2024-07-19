# Configuração do Git e SSH

## Configuração do Git

Este tutorial irá guiá-lo através dos passos necessários para instalar e configurar o Git no Linux.

### 1. Instalar o Git

#### Distribuições baseadas em Debian/Ubuntu

```bash
sudo apt update
sudo apt install git
```

### 2. Configurar o Git
Depois de instalar o Git, configure seu nome de usuário e email:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@example.com"
```
Verifique suas configurações:

```bash
git config --list
```
Para mais detalhes, consulte a [documentação oficial do Git.](https://git-scm.com/doc)

## Configuração do SSH
Este tutorial irá guiá-lo através dos passos necessários para configurar a autenticação SSH para o GitHub no Linux.

### 1. Gerar uma Nova Chave SSH
Para gerar uma nova chave SSH, execute o seguinte comando:

```bash
ssh-keygen -t rsa -b 4096 -C "seu-email@example.com"
```
Pressione Enter para aceitar o local padrão do arquivo e, em seguida, defina uma senha segura.

### 2. Adicionar a Chave SSH ao Agente SSH
Adicione a chave SSH ao agente SSH:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

### 3. Adicionar a Chave SSH ao GitHub
1. Copie a chave pública para o clipboard:
  
  ```bash
  cat ~/.ssh/id_rsa.pub
  ```
2. Acesse as configurações do seu perfil no GitHub.
3. Clique em "SSH and GPG keys".
4. Clique em "New SSH key", dê um título à chave, cole a chave pública e clique em "Add SSH key".

### 4. Testar a Conexão SSH
Para testar a conexão SSH, execute o seguinte comando:

```bash
ssh -T git@github.com
```

Se tudo estiver configurado corretamente, você verá uma mensagem de confirmação.

```
Hi seu-usuario! You've successfully authenticated, but GitHub does not provide shell access.
```

Para mais detalhes, consulte a [documentação oficial do GitHub.](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)


  
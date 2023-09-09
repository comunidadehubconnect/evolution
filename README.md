<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2023/08/logo-github-cwmkt.svg" alt="DispZap Whats Marketing" width="240" />
<p align="center">Seja bem-vindo ao Guia de Instalação Chatwoot+Evolution 🚀</p>
</p>
  
<p align="center">
<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
<span>Grupo WhatsaAPP: </span>
<a href="https://link.cwmkt.com.br/grupo-whats" target="_blank">Grupo</a>
</p>

<hr />
<hr />


<details>
<summary>Manual de Instalação Chatwoot</summary>

### Atualize sua máquina com os últimos pacotes

```bash
sudo apt update && apt upgrade -y
```

### Baixe o instalador automático do Chatwoot

```bash
wget https://get.chatwoot.app/linux/install.sh
```

### Execute a permisão no arquivo install.sh

```bash
chmod +x install.sh
```

### Inicie a instalação, digite "yes" para SSL, em seguida digite seu dominio e prossiga confimando com yes.
### Esse processo vai levar média ~ 15

  ```bash
./install.sh --install
  ```

Use as opções abaixo

yes

app.dominio.com.br

contato@dominio.com.br

yes para todos

### Alterando Idioma e ativando sua tela de cadastro

```bash
nano /home/chatwoot/chatwoot/.env
```

Altere a linha:

`DEFAULT_LOCALE=pt_BR` para `ENABLE_ACCOUNT_SIGNUP=true`

```bash
systemctl daemon-reload && systemctl restart chatwoot.target
```

Acesse: app.seudominio.com.br

Faça seu cadastro

### Habilitando configurações ocultas do Chatwoot no banco de dados PostgreSQL

```bash
sudo -i -u postgres psql
\c chatwoot_production
```

```bash
update installation_configs set locked = false;
```

```bash
\q
```

</details>


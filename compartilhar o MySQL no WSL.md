## Configuração do MySQL no WSL

## 1. Configurar Windows

### Abrir porta 3306 no WSL

```bash
netsh advfirewall firewall add rule name="Allowing LAN connections" dir=in action=allow protocol=TCP localport=3306

```

### Configurar proxy de porta

Substitua `172.28.139.76` pelo IP do WSL.

```bash
netsh interface portproxy add v4tov4 listenport=3306 listenaddress=0.0.0.0 connectport=3306 connectaddress=172.28.139.76
```

## 2. Criar usuário com permissão ao banco

```sql
CREATE USER 'ze'@'%' IDENTIFIED BY 'senha1234';
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
```

## 3. Liberar acesso de hosts externos

Edite o arquivo de configuração do MySQL:

```bash
sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
```

Comente a linha `bind-address` e adicione a nova configuração:

```ini
#bind-address = 127.0.0.1

bind-address = 0.0.0.0
```

## 4. Reiniciar o MySQL

```bash
sudo service mysql restart
```

# LAMP Stack Setup Commands

## Update System

```bash
sudo dnf update -y
```

## Install Apache

```bash
sudo dnf install httpd -y
sudo systemctl enable --now httpd
sudo systemctl status httpd
```

## Install MariaDB

```bash
sudo dnf install mariadb-server -y
sudo systemctl enable --now mariadb
sudo systemctl status mariadb
```

## Secure MariaDB

```bash
sudo mysql_secure_installation
```

## Install PHP

```bash
sudo dnf install php php-mysqlnd -y
sudo systemctl restart httpd
```

## Verify PHP

Create `info.php`:

```php
<?php
phpinfo();
?>
```

Open in browser:

```text
http://localhost/info.php
```

## Check Server IP

```bash
ip a
```

## Allow HTTP Service

```bash
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload
```

## Verify Services

```bash
sudo systemctl status httpd
sudo systemctl status mariadb
```

## Test Client Access

```text
http://<server-ip>
```

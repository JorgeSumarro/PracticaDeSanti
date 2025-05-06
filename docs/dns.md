# Servidor DNS

El sistema DNS convierte nombres de dominio (como `google.com`) en direcciones IP que las máquinas entienden.

::: info
Sin DNS tendrías que memorizar IPs como 142.250.184.78 para acceder a tus páginas favoritas.
:::

## Tipos de servidores DNS

- **Raíz** (Root servers)
- **Autoritativos**
- **Recurso o recursivos** (como 8.8.8.8)

![Funcionamiento DNS](https://www.akamai.com/site/es/images/article/2023/how-dns-works.png)

## Comandos útiles

```bash
dig www.google.com
nslookup openai.com
host github.com

## Instalar BIND9

sudo apt update
sudo apt install bind9 bind9utils

## Configuración Basica

Editamos el archivo principal

sudo nano /etc/bind/named.conf.options

##Ejemplo de Configuración

options {
  directory "/var/cache/bind";

  forwarders {
    8.8.8.8;
    1.1.1.1;
  };

  dnssec-validation auto;

  listen-on-v6 { any; };
};

##Comprobar el estado del servicio
sudo systemctl restart bind9




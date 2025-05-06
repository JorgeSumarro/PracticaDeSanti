# Servidor DHCP

DHCP permite que los dispositivos conectados a una red obtengan automáticamente su dirección IP y otros parámetros como la puerta de enlace y los DNS.

::: tip ¿Por qué es útil?
En redes grandes, evita tener que configurar cada dispositivo manualmente.
:::

## Funcionamiento

1. El cliente envía un mensaje **DHCP Discover**
2. El servidor responde con **DHCP Offer**
3. El cliente envía **DHCP Request**
4. El servidor lo confirma con **DHCP Acknowledgement**

![Funcionamiento DHCP](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTQ40ed1IA-s_k7d73LfJ9MzSITJDPgD-lwkQ&s
)

## Instalación en Ubuntu

```bash
sudo apt update
sudo apt install isc-dhcp-server

## Configuración Basica

Editamos el archivo principal

sudo nano /etc/dhcp/dhcpd.conf

##Ejemplo de Configuración

subnet 192.168.1.0 netmask 255.255.255.0 {

  range 192.168.1.100 192.168.1.150;

  option routers 192.168.1.1;

  option subnet-mask 255.255.255.0;

  option domain-name-servers 8.8.8.8, 1.1.1.1;

  default-lease-time 600;

  max-lease-time 7200;
}

## Comprobar el estado del Servicio

sudo systemctl status isc-dhcp-server

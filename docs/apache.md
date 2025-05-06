# Servidor Apache

Apache es uno de los servidores web más usados del mundo. Permite publicar páginas web, alojar APIs o incluso gestionar aplicaciones.

::: success
Ideal para aprender sobre hosting, HTML y administración web.
:::

## Instalación en Ubuntu

```bash
sudo apt update
sudo apt install apache2

## Comprobación
Accede a: http://localhost
Deberías ver una página con el texto “It works!”

![Funcionamiento Apache](https://www.ionos.es/digitalguide/fileadmin/DigitalGuide/Screenshots_2023/apache-default-page.png)


##Archivos Importantes

| Ruta                            | Función                    |
| ------------------------------- | -------------------------- |
| `/var/www/html/`                | Carpeta raíz del sitio web |
| `/etc/apache2/apache2.conf`     | Configuración principal    |
| `/etc/apache2/sites-available/` | Virtual Hosts              |

## Habilitar y reiniciar

sudo systemctl enable apache2
sudo systemctl restart apache2

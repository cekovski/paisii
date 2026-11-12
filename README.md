# Paisii – Homepage der Bulgarischen Schule München

Neue Website der Bulgarischen Schule „Paisii Hilendarski“ in München, gebaut mit WordPress und einem eigenen Theme.

- Vorübergehende Domain: https://new.bulgarische-schule-muenchen.de
- Server: CloudPanel, SSH-Alias `paisii`, Docroot `~/htdocs/new.bulgarische-schule-muenchen.de`
- PHP 8.4, WordPress 7.1 (de_DE)

## Was im Repo liegt

Versioniert wird nur eigener Code. WordPress-Core, fremde Plugins/Themes, Uploads und `wp-config.php` sind per `.gitignore` ausgeschlossen.

| Pfad | Inhalt |
| --- | --- |
| `wp-content/themes/paisii/` | Custom Theme |
| `wp-content/mu-plugins/` | Must-use Plugins (falls nötig) |
| `nginx/vhost.conf` | Vhost-Konfiguration für CloudPanel (Sites → Vhost) |

## Lokale Entwicklung

Im Projektordner liegt eine vollständige WordPress-Installation (de_DE). Der Core wird nicht versioniert; bei Bedarf neu laden:

```bash
curl -O https://de.wordpress.org/latest-de_DE.tar.gz
```

## Server

WordPress-Core, Datenbank und `wp-config.php` werden von CloudPanel verwaltet. Updates per `wp-cli`:

```bash
ssh paisii
cd ~/htdocs/new.bulgarische-schule-muenchen.de
wp core update && wp plugin update --all
```

Admin-Bereich ist per Basic Auth geschützt (`~/.htpasswd`, siehe `nginx/vhost.conf`).

> Das Repo ist öffentlich: keine Zugangsdaten, Passwörter oder Schlüssel committen.

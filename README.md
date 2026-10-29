# WP Subscribe (HackIndex Patched)

> [!IMPORTANT]
> This is an unofficial fork of [WP Subscribe](https://wordpress.org/plugins/wp-subscribe/) by [MyThemeShop](https://github.com/MyThemeShop/wp-subscribe-by-mythemeshop). HackIndex is not affiliated with or endorsed by MyThemeShop.

The original plugin is no longer maintained and its latest release (1.2.16) has a [known vulnerability](https://www.wordfence.com/threat-intel/vulnerabilities/id/83a7e451-6d8f-48aa-9774-46e3d4434330). HackIndex maintains this fork for security fixes only:

- We fix security issues and keep the plugin working on current WordPress and PHP versions.
- We do not add features or change how the plugin works.
- It is a drop-in replacement: same plugin folder, widgets and settings, and your MailChimp and AWeber connections keep working.

Need help with this fork? [Open an issue](https://github.com/HackIndex-io/wp-subscribe/issues) here, please don't contact MyThemeShop about it.

## Security fixes

### 1.2.17

- Subscriber+ Missing Authorization ([CVE-2026-24522](https://www.cve.org/CVERecord?id=CVE-2026-24522), [Wordfence advisory](https://www.wordfence.com/threat-intel/vulnerabilities/id/83a7e451-6d8f-48aa-9774-46e3d4434330)): any logged-in user could fetch mailing lists with their own API key (overwriting the saved lists) and connect their own AWeber account. Both now require the `edit_theme_options` capability and a nonce.
- The MailChimp API key must end in a real data center (like `us6`), so it can't point requests at another host (SSRF)
- Mailing list names in the widget settings and a hidden field attribute are escaped
- Fixed "Get list" and AWeber errors on PHP 8
- Tested with WordPress 7.1 and PHP 8.5

## Install

1. Download `wp-subscribe.zip` from the [latest release](https://github.com/HackIndex-io/wp-subscribe/releases/latest).
2. Deactivate and delete the original WP Subscribe. Your widgets and settings are kept.
3. Upload the zip in **Plugins > Add New > Upload Plugin** and activate it.

WordPress does not update this fork automatically. Watch this repo's releases to get new security fixes.

## License

GPLv2 or later, like the original. See [LICENSE](LICENSE). Provided without any warranty.

All credit for the plugin goes to [MyThemeShop](https://github.com/MyThemeShop/wp-subscribe-by-mythemeshop). The upstream history is kept in this repository. The upstream repo stopped at version 1.0.1, so this fork continues from the 1.2.16 release on WordPress.org.

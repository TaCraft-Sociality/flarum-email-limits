# Email-limits

A [Flarum](https://flarum.org) 2.0.x extension that only lets people register with an email address from a whitelisted set of domains. Accounts that already exist are not affected, and changing the whitelist never touches existing accounts.

## Features

- Adds an **Email-limits** page in the admin panel.
- Accepts any number of allowed email suffixes, one per line or separated by commas, for example `qq.com`, `163.com`, `gmail.com`.
- Blocks registration with any other email domain, and shows the allowed suffixes in the error message.
- Subdomains of an allowed suffix are accepted as well.
- Leaving the list empty disables the restriction, so nobody gets locked out by accident.
- Only applies to new registrations. Existing users are never blocked or modified.

## Installation

With Composer (after the package is published):

```bash
composer require tacraft-sociality/flarum-email-limits
```

Manual installation:

1. Unzip the `flarum-email-limits` folder into the `packages` directory of your Flarum installation.
2. Add a path repository to your site's `composer.json` if you do not have one yet:

   ```json
   "repositories": [
       { "type": "path", "url": "packages/*" }
   ]
   ```

3. Install and enable the extension:

   ```bash
   composer require tacraft-sociality/flarum-email-limits:@dev
   php flarum extension:enable tacraft-sociality-email-limits
   php flarum cache:clear
   ```

Then open **Email-limits** in the admin panel and fill in the allowed suffixes.

## Updating

```bash
composer update tacraft-sociality/flarum-email-limits
php flarum cache:clear
```

## Removing

```bash
composer remove tacraft-sociality/flarum-email-limits
```

## Links

- [Packagist](https://packagist.org/packages/tacraft-sociality/flarum-email-limits)

## License

MIT

# heroku-buildpack-php CHANGELOG

## v78 (2015-10-01)

### ADD

- PHP/7.0.0RC4 [David Zuelke]
- PHP/5.5.30 [David Zuelke]
- PHP/5.6.14 [David Zuelke]

## v77 (2015-09-17)

### ADD

- PHP/7.0.0RC3 [David Zuelke]

## v76 (2015-09-08)

### ADD

- ext-mongo/1.6.11 [David Zuelke]
- PHP/7.0.0RC2 [David Zuelke]
- PHP/5.5.29 [David Zuelke]
- PHP/5.6.13 [David Zuelke]

## v75 (2015-08-21)

### FIX

- Prevent potential (benign) Python notice during builds

## v74 (2015-08-21)

### FIX

- Warning about missing composer.lock is thrown incorrectly for some composer.json files

## v72 (2015-08-21)

### ADD

- PHP/5.6.12 [David Zuelke]
- PHP/5.5.28 [David Zuelke]
- ext-newrelic/4.23.4.113 [David Zuelke]
- PHP/7.0.0RC1 [David Zuelke]
- Support custom `composer.json`/`composer.lock` file names via `$COMPOSER` env var [David Zuelke]

### CHG

- A composer.lock is now required if there is any entry in the "require" section of composer.json [David Zuelke]

## v71 (2015-07-14)

### ADD

- ext-newrelic/4.23.1.107 [David Zuelke]

### FIX

- Apache `mod_proxy_fgci`'s "disablereuse=off" config flag causes intermittent blank pages with HTTPD 2.4.11+ [David Zuelke]
- Applications on cedar-10 can select non-existing PHP 7.0.0beta1 package via composer.json [David Zuelke]

## v70 (2015-07-10)

### ADD

- PHP/7.0.0beta1 [David Zuelke]
- PHP/5.6.11 [David Zuelke]
- PHP/5.5.27 [David Zuelke]
- ext-newrelic/4.23.0.102 [David Zuelke]
- ext-mongo/1.6.10 [David Zuelke]
- Support auto-tuning for IX dyno type [David Zuelke]

### CHG

- Warn about missing extensions for "blackfire" and "newrelic" add-ons during startup [David Zuelke]

## v69 (2015-06-12)

### ADD

- PHP/5.5.26 [David Zuelke]
- PHP/5.6.10 [David Zuelke]
- ext-newrelic/4.22.0.99 [David Zuelke]
- ext-mongo/1.6.9 [David Zuelke]

## v68 (2015-05-18)

### ADD

- PHP/5.6.9 [David Zuelke]
- PHP/5.5.25 [David Zuelke]
- ext-newrelic/4.21.0.97 [David Zuelke]
- ext-mongo/1.6.8 [David Zuelke]

### CHG

- Use Composer/1.0.0alpha10 [David Zuelke]
- Link only `.heroku/php/` subfolder and not all of `.heroku/` during compile to prevent potential collisions in multi BP scenarios [David Zuelke]

### FIX

- Typo in log messages [Christophe Coevoet]
- Newrelic 4.21 agent startup complaining about missing pidfile location config [David Zuelke]

## v67 (2015-03-24)

### ADD

- ext-mongo/1.6.6 [David Zuelke]
- PHP/5.6.7 [David Zuelke]
- PHP/5.5.23 [David Zuelke]

### CHG

- Don't run composer install for empty composer.json [David Zuelke]
- Unset GIT_DIR at beginning of compile [David Zuelke]

## v66 (2015-03-05)

### ADD

- ext-newrelic/4.19.0.90 [David Zuelke]

## v65 (2015-03-03)

### ADD

- ext-redis/2.2.7 [David Zuelke]
- ext-mongo/1.6.4 [David Zuelke]
- HHVM/3.3.4 [David Zuelke]

### CHG

- Composer uses stderr now for most output, indent that accordingly [David Zuelke]

## v64 (2015-02-19)

### ADD

- HHVM/3.5.1 [David Zuelke]
- PHP/5.6.6 [David Zuelke]
- PHP/5.5.22 [David Zuelke]
- ext-newrelic/4.18.0.89 [David Zuelke]
- ext-mongo/1.6.3 [David Zuelke]

## v63 (2015-02-11)

### ADD

- ext-mongo/1.6.2 [David Zuelke]

### CHG

- Tweak auto-tuning messages (tag: v63) [David Zuelke]
- Move 'booting...' message to after startup has finished [David Zuelke]
- Ignore SIGINT when running under foreman etc to ensure clean shutdown [David Zuelke]
- Prevent redundant messages when loading HHVM configs [David Zuelke]
- Echo "running workers..." message to stderr on boot [David Zuelke]

### FIX

- Incorrect 'child 123 said into stderr' removal for lines that are deemed to long by FPM and cut off using a terminating '...' sequence instead of closing double quotes [David Zuelke]

## v62 (2015-02-04)

### FIX

- Broken PHP memlimit check [David Zuelke]

## v61 (2015-02-04)

### CHG

- Port autotuning to HHVM-Nginx [David Zuelke]

### FIX

- Workaround for Composer's complaining about outdated version warnings on stdout instead of stderr, breaking calls in a few places under certain circumstances [David Zuelke]

## v60 (2015-02-04)

### ADD

- Auto-tune number of workers based on dyno size and configured memory limit [David Zuelke]

## v59 (2015-01-29)

### ADD

- ext-mongo/1.6.0 (tag: v59) [David Zuelke]

### CHG

- Improvements to INI handling for HHVM, including new `-I` switch to allow passing additional INI files at boot [David Zuelke]
- Massively improved subprocess and signal handling in boot scripts [David Zuelke]

## v58 (2015-01-26)

### ADD

- HHVM/3.5.0 [David Zuelke]
- PHP/5.6.5 [David Zuelke]
- PHP/5.5.21 [David Zuelke]

## v57 (2015-01-19)

### CHG

- Update to Composer dev version for `^` selector support [David Zuelke]

## v56 (2015-01-13)

### ADD

- ext/oauth 1.2.3 [David Zuelke]
- HHVM/3.3.3 [David Zuelke]
- Run 'composer compile' for custom scripts at the end of deploy [David Zuelke]

## v55 (2015-01-07)

### FIX

- Standard logs have the wrong $PORT in the file name if the -p option is used in boot scripts [David Zuelke]

## v54 (2015-01-05)

### ADD

- ext-newrelic/4.17.0.83 [David Zuelke]

### CHG

- Auto-set and follow (but not enable, for now) the FPM slowlog [David Zuelke]

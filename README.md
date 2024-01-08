# DDEV Selenium Standalone Chrome

Forked from [https://github.com/ddev/ddev-selenium-standalone-chrome](https://github.com/ddev/ddev-selenium-standalone-chrome)

## Install/Update

1. `ddev get https://github.com/Leuchtfeuer/ddev-selenium-standalone-chrome/archive/refs/tags/0.0.1.tar.gz`, where `0.0.2.tar.gz` is the latest release.
2. `ddev restart`
3. Optional. Update the provided .ddev/config.selenium-standalone-chrome.yaml as you see fit (and remove the #ddev-generated line). You can also just override lines in your .ddev/config.yaml
4. Optional. Check config.selenium-standalone-chrome.yaml and docker-compose.selenium-chrome.yaml into your source control.
5. Update by re-running `ddev get https://github.com/Leuchtfeuer/ddev-selenium-standalone-chrome/archive/refs/tags/0.0.2.tar.gz` (or the latest release).

## Watching the tests

### The easy way: Use noVNC (built-in)

On your host, browse to https://[DDEV SITE URL]:7900 (password: `secret`) to watch tests run with noVNC (neat!).

This enables you to quickly see what is going on with your tests.

### Behat config example

If you use Behat as a test running, adjust your `behat.yml`

```yml
  extensions:
    Behat\MinkExtension:
      base_url: http://web
      selenium2:
        wd_host: http://selenium-chrome:4444/wd/hub
        capabilities:
          chrome:
            switches:
              - "--disable-gpu"
              - "--headless"
              - "--no-sandbox"
              - "--disable-dev-shm-usage"
```

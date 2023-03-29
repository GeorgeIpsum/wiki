# access git:// behind proxy

## Accessing git:// addresses behind a corporate proxy

Occasionally corporate proxies won't allow access to `git://` addresses (through github or whatever other remote provider you use). This can sometimes be circumvented through the following git config modifications:

```bash
git config --global url.https://github.com/.insteadof git://github.com/
git config --global http.https://github.com.proxy http://yourproxy:8080
```

This of course requires knowing both the name and port of the proxy.

Your modified git config will look like this:

{% code title="~/.gitconfig" %}
```
[url "https://github.com/"]
    insteadof = git://github.com/
[http "https://github.com"]
    proxy = http://yourproxy:8080
```
{% endcode %}

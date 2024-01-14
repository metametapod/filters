## Filters

### AdGuard / uBlock Origin

- [Unblock Contextual Ads (reduced)](https://raw.githubusercontent.com/metametapod/filters/main/adguard/contextual.txt)
- [Unblock Search Ads and Self-Promotion (reduced)](https://raw.githubusercontent.com/metametapod/filters/main/adguard/self-promo.txt)

### Hosts

- [AdGuard DNS filter (hosts format)](https://raw.githubusercontent.com/metametapod/filters/main/adguard/hosts/filter_1.txt)

### Little Snitch

- [AdGuard DNS filter (lsrules format)](https://raw.githubusercontent.com/metametapod/filters/main/adguard/little-snitch/filter_1.json)

## Local installation

For a self-hosted install, you can use the following:

```sh
git clone --depth 1 https://github.com/metametapod/filters
cd filters

# Can run via cron, etc.
./scripts/update
./scripts/generate/abp
./scripts/generate/hosts
./scripts/generate/little-snitch
```

Note that generating the hosts file is expensive and may not be feasible on
slower machines.

Changes to the scripts in the repository can be pulled and vetted as-needed.

Then use a `file://` URL to refer to the filter. For example,
`file:///path/to/filters/adguard/contextual.txt`.

Alternatively, you can run a local webserver in the `filters` directory via
e.g.:

```
python3 -m http.server 8080
```

And instead use `http://localhost:8080/adguard/contextual.txt`.

Another option is to fork this repository and use the included GitHub Action.

## See also

- [Search ads and self-promotion](https://adguard.com/kb/general/ad-filtering/search-ads/)
- [Advertising for Open Source Exception Lists](https://ads-for-open-source.readthedocs.io)
- [Script to automatically update hosts file from a filter list](https://gist.github.com/metametapod/4c4a7a9c888343fc6e722f8ed77aa763)

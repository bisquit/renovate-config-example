Checking config that requires migration with `renovate-config-validator --strict` does not result in a correct error (exit 1) when using environment variables `RENOVATE_CONFIG_FILE`.

```sh
pnpm i

## exit 1 when using argument (right behavior)
pnpm renovate-config-validator --strict default.json
echo $? #=> 1

## exit 0 when usign env (wrong behavior)
RENOVATE_CONFIG_FILE=default.json pnpm renovate-config-validator --strict
echo $? #=> 0
```

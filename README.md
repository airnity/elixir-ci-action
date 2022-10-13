# Elixir CI action

Action to run multiple elixir CI commands. In order:

- `mix deps.get`
- `mix compile --warnings-as-errors`
- `mix format --check-formatted`
- `mix deps.unlock --check-unused`
- `mix credo`
- `mix dialyzer`
- `mix test`

## Inputs

### `mix-env`

The `MIX_ENV` variable to run the commands in.
_Default_: `test`

### `mix-env-test`

The `MIX_ENV` variable to run tests in.
_Default_: `test`

### `run-tests`

Wether to run mix test or not.
_Default_: `True`

### `tests-flags`

Flags to add to append to the `mix test` command (e.g. `--only tag` or `--no-start`, etc.)
_Default_: ''

### `working-directory`

The directory to work on.
_Default_: `.`

### `release`

Wether to run mix release and upload artifact or not.
_Default_: `False`

### `release-name`

The name of the uploaded release.
_Default_: `release`

### `release-upload`

Wether to upload the artifact or not.
_Default_: `False`

### `build-cache-key-suffix`

Suffix to add to the build cache key
_Default_: ""

### `plt-cache-key-suffix`

Suffix to add to the plt cache key
_Default_: ""

### `plt-restore-cache`

If false it won't retrieve cache from other restore keys
_Default_: "True"

### `compile-options`

the compile options parameter
_Default_: `--warnings-as-errors`

## Example usage

```yaml
- name: Run elixir CI
  uses: airnity/elixir-ci-action@v4
  with:
    mix-env: dev
    working-directory: "./myApp"
    release: "True"
    build-cache-key-suffix: "test"
    plt-restore-cache: "False"
```

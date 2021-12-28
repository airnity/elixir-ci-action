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

## Example usage

```yaml
- name: Run elixir CI
  uses: airnity/elixir-ci-action@v1
  with:
    mix-env: dev
    working-directory: "./myApp"
    release: "True"
```

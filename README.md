# Greeting demo action

Greets someone and returns the greeting as an output. Built as a teaching example for GitHub Actions Fundamentals.

## Inputs

| Input | Required | Default | Description |
|---|---|---|---|
| `who` | yes | `World` | Who to greet |

## Outputs

| Output | Description |
|---|---|
| `greeting` | The full greeting, for example `Hello, Mona!` |

## Example

```yaml
permissions:
  contents: read

steps:
  - id: greet
    uses: OWNER/greet-action@v1.0.0   # or pin the release's full commit SHA
    with:
      who: Mona

  - env:
      GREETING: ${{ steps.greet.outputs.greeting }}
    run: echo "$GREETING"
```

Works on Linux, macOS and Windows runners. No secrets or extra permissions needed

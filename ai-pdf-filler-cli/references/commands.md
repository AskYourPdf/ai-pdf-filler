# Command Cheat Sheet

## Quick check

```bash
simplicity-cli --help
simplicity-cli help
```

If the command is missing, install first:

```bash
uv tool install ai-pdf-filler
# fallback
python3 -m pip install ai-pdf-filler
```

## Auth

```bash
simplicity-cli --api-key "<api_key>"
```

Key precedence:

1. `--api-key`
2. `SIMPLICITY_AI_API_KEY`
3. saved key in `~/.config/simplicity-cli/config.json`

## New form workflow

```bash
simplicity-cli new --form-file ./form.pdf --context "applicant data"
```

```bash
simplicity-cli new --form-file ./form.pdf --source-file ./source.pdf
```

```bash
simplicity-cli new --form-url "https://example.com/form.pdf" --source-url "https://example.com/source.pdf"
```

Options:

- `--no-wait`
- `--poll-interval-seconds <n>`
- `--max-wait-seconds <n>`
- `--no-download`
- `--output <path>`

## Existing form workflow

```bash
simplicity-cli existing FORM_ID --context "latest profile"
```

```bash
simplicity-cli existing FORM_ID --instructions "prefer exact legal names"
```

## Task workflow

```bash
simplicity-cli status TASK_ID
simplicity-cli wait TASK_ID
```

## JSON mode

```bash
simplicity-cli --json status TASK_ID
simplicity-cli --json new --form-file ./form.pdf --context "applicant data"
```

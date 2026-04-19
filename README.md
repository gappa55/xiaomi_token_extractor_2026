# xiaomi_token_extractor_2026

Xiaomi cloud token extractor by Piotr Machowski, fixed so that new xiaomi 2FA method works.

Confirmed working with supplying email as the username.
Captcha and 2FA works, just type in the code you receive on your email.

## Requirements

- Python 3.8+
- Dependencies:
  - `requests`
  - `pycryptodome`
  - `Pillow`

## Installation

```bash
python3 -m venv venv
source venv/bin/activate
pip install requests pycryptodome Pillow
```

## Usage

### Interactive mode

```bash
python3 token_extractor_2026.py
```

You will be prompted for username, password, and server step by step.

### Non-interactive mode

```bash
python3 token_extractor_2026.py -u YOUR_EMAIL -p YOUR_PASSWORD -s cn
```

### Options

| Flag | Description |
|------|-------------|
| `-ni`, `--non_interactive` | Run without interactive prompts |
| `-u`, `--username` | Username (email or user ID) |
| `-p`, `--password` | Password |
| `-s`, `--server` | Server: `cn`, `de`, `us`, `ru`, `tw`, `sg`, `in`, `i2`, or leave empty to check all servers |
| `-l`, `--log_level` | Log level: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL` (default: `CRITICAL`) |
| `-o`, `--output` | Save output to a JSON file |
| `--host` | Host for serving captcha image |

### Examples

Check all servers and save results to a file:
```bash
python3 token_extractor_2026.py -o output.json
```

Check a specific server with debug logging:
```bash
python3 token_extractor_2026.py -s de -l DEBUG
```

## Servers

| Code | Region |
|------|--------|
| `cn` | China |
| `de` | Germany |
| `us` | United States |
| `ru` | Russia |
| `tw` | Taiwan |
| `sg` | Singapore |
| `in` | India |
| `i2` | China (alternate) |

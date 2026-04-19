# xiaomi_token_extractor_2026

Xiaomi cloud token extractor by Piotr Machowski, fixed so that new xiaomi 2FA method works.

confirmed working with supplying email as the username.
captcha and 2FA works, just type in the code you receive on your email

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

จะถาม username, password, และ server ทีละขั้นตอน

### Non-interactive mode

```bash
python3 token_extractor_2026.py -u YOUR_EMAIL -p YOUR_PASSWORD -s cn
```

### Options

| Flag | Description |
|------|-------------|
| `-ni`, `--non_interactive` | รันแบบไม่ต้องถาม input |
| `-u`, `--username` | Username (email หรือ user ID) |
| `-p`, `--password` | Password |
| `-s`, `--server` | Server: `cn`, `de`, `us`, `ru`, `tw`, `sg`, `in`, `i2` หรือเว้นว่างเพื่อตรวจทุก server |
| `-l`, `--log_level` | Log level: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL` (default: `CRITICAL`) |
| `-o`, `--output` | บันทึกผลลัพธ์เป็นไฟล์ JSON |
| `--host` | Host สำหรับแสดง captcha image |

### Examples

ตรวจทุก server และบันทึกผลเป็นไฟล์:
```bash
python3 token_extractor_2026.py -o output.json
```

ตรวจเฉพาะ server ญี่ปุ่น พร้อม debug log:
```bash
python3 token_extractor_2026.py -s cn -l DEBUG
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

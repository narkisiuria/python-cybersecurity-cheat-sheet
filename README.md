# python-cybersecurity-cheat-sheet

## 🚀 Python for Cybersecurity - Master Cheat Sheet

A comprehensive guide for python-based cybersecurity tools, exploits, and networking.

---

### 🛠️ 1. Basics & Networking (יסודות ורשתות)

**יצירת אובייקט תקשורת בסיסי (Socket):**
```python
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```

**ניסיון התחברות לכתובת IP ופורט מסוים:**
```python
s.connect(("127.0.0.1", 443))
```

**שליחת בקשת GET פשוטה לאתר:**
```python
response = requests.get("https://target.com")
```

**שליפת ה-Headers שהשרת מחזיר:**
```python
print(response.headers)
```

**הצפנת טקסט ל-Hash מסוג SHA256:**
```python
hashlib.sha256(b"my_password").hexdigest()
```

**פתיחת קובץ לקריאה בלבד:**
```python
with open("list.txt", "r") as file:
```

**הסרת רווחים או ירידות שורה מטקסט:**
```python
clean_line = line.strip()
```

---

### 🔒 2. Encoding & Data (קידוד וניהול מידע)

**הפיכת טקסט לפורמט Base64 (שימושי להעברת פיילואודים):**
```python
import base64
encoded = base64.b64encode(b"secret_data").decode()
```

**פענוח של מחרוזת Base64 חזרה לטקסט המקורי:**
```python
decoded = base64.b64decode("c2VjcmV0X2RhdGE=").decode()
```

**קריאת משתנה סביבה (חשוב כדי לא לשמור סיסמאות בתוך הקוד):**
```python
import os
api_key = os.getenv("API_KEY")
```

**יצירת מחרוזת רנדומלית מאובטחת (למשל עבור Token או מלח לסיסמה):**
```python
import secrets
token = secrets.token_hex(16)
```

---

### 🛡️ 3. Cybersecurity Tools & Exploits (סייבר וכלים, אקספלויטים ושיטות)

**שימוש ב-Scapy כדי להאזין לחבילת מידע אחת ברשת (Sniffing):**
```python
from scapy.all import sniff
pkt = sniff(count=1)
```

**ביצוע "Banner Grabbing" כדי לזהות גרסת שירות שרץ על שרת:**
```python
banner = s.recv(1024)
```

**הרצת פקודת מערכת (כמו Nmap או Ping) ישירות מפייתון:**
```python
import subprocess
result = subprocess.run(["ping", "-c", "1", "8.8.8.8"], capture_output=True)
```

**הצפנה סימטרית מאובטחת של מידע (ספריית Cryptography):**
```python
from cryptography.fernet import Fernet
key = Fernet.generate_key()
cipher = Fernet(key).encrypt(b"Top Secret")
```
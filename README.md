# python-cybersecurity-cheat-sheet
A public python and cybersecurity cheat sheet

---
### Basics & Networking

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
### קידוד וניהול מידע (Encoding & Data)

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
apikeyk = os.getenv("API_KEY")
```

**יצירת מחרוזת רנדומלית מאובטחת (למשל עבור Token או מלח לסיסמה):**
```python
import secrets
token = secrets.token_hex(16)
```
# יואב חביב — אתר תדמית

אתר סטטי (HTML/CSS/JS בלבד, בלי שלב בנייה) לעסק של בניית אתרים ודפי נחיתה.

## מבנה

| קובץ | מה זה |
|---|---|
| `index.html` | הדף הראשי. כל ה-CSS וה-JS בתוכו |
| `privacy.html` | מדיניות פרטיות |
| `work/` | עמודי תיק עבודות (מקרי בוחן) |
| `og-image.png` | תמונת התצוגה שמופיעה כששולחים את הלינק |
| `robots.txt`, `sitemap.xml` | קבצי SEO |

## הרצה מקומית

```bash
python3 -m http.server 8000
```
ואז לפתוח http://localhost:8000

## פריסה ל-Vercel

אין שלב בנייה. בייבוא הפרויקט ב-Vercel:

- **Framework Preset:** Other
- **Root Directory:** `./` (ברירת המחדל)
- **Build Command / Output Directory / Install Command:** להשאיר ריקים

## אחרי הפריסה — להחליף את כתובת ה-placeholder

בקבצים יש `https://example.com` בתור מציין מקום. צריך להחליף אותו בכתובת האמיתית
ב-`index.html`, `privacy.html`, `work/*.html`, `sitemap.xml` ו-`robots.txt`:

```bash
grep -rl 'https://example.com' . | xargs sed -i 's|https://example\.com|https://THE-REAL-DOMAIN|g'
```

עד שזה נעשה, שיתוף הלינק לא יציג את תמונת התצוגה, וגוגל יקבל כתובות canonical שגויות.

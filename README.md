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

## כתובת האתר

האתר חי בכתובת https://yoav-website-seven.vercel.app

הכתובת הזאת מופיעה בתוך הקבצים (canonical, og:url, og:image, sitemap, robots).
כשיהיה דומיין אמיתי צריך להחליף אותה בכל הקבצים:

```bash
grep -rl 'https://yoav-website-seven.vercel.app' . --exclude-dir=.git \
  | xargs sed -i 's|https://yoav-website-seven\.vercel\.app|https://THE-REAL-DOMAIN|g'
```

בלי זה, שיתוף הלינק יציג את תמונת התצוגה של הכתובת הישנה וגוגל יקבל canonical שגוי.

# המחברת של נאוה · Nava's cookbook

אתר סטטי (HTML + CSS בלבד, בעברית ומימין לשמאל) לאוסף מתכונים. בלי בנייה, בלי תלויות. מיועד ל-GitHub Pages.

A static Hebrew (RTL) recipe site: plain HTML + one CSS file, no build step.

## תצוגה מקומית

```sh
python3 -m http.server
# ואז לפתוח http://localhost:8000
```

אפשר גם לפתוח את `index.html` ישירות בדפדפן.

## הוספת מתכון

1. מעתיקים את `recipes/example.html` לקובץ חדש, למשל `recipes/challah.html`, ועורכים את התוכן (ההערות בקובץ מסבירות מה להחליף).
2. ב-`index.html` מעתיקים את בלוק הכרטיס שמסומן `כרטיס מתכון: העתיקו מכאן`, מדביקים אותו ברשימה של הקטגוריה המתאימה (עוגות ועוגיות / מנות עיקריות), ומשנים את הכותרת, התיאור והתמונה. קטגוריה חדשה: מעתיקים בלוק `section` שלם ומוסיפים לו קישור בתפריט `nav class="cats"`.
3. מכוונים את `href` של הכרטיס לקובץ החדש (`recipes/challah.html`).
4. תמונות חדשות מניחים ב-`images/`, ומוסיפים שורת קרדיט בכותרת התחתונה.

## פרסום ב-GitHub Pages

Settings → Pages → Source: **Deploy from a branch** → Branch: `main`, תיקייה `/ (root)` → Save.

הקוד ברישיון ה-LICENSE שבמאגר.

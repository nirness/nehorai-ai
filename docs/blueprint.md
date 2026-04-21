# Nehorai AI — Blueprint

> תמצית ההחלטות הארכיטקטוניות של v1.

---

## מה בונים כאן

**Nehorai AI** הוא לא agent, לא wrapper כבד, לא מנגנון לומד.

בגרסה v1 הוא פשוט:

- **Prompt Pack** — כל מה שצריך לתת למודל כדי שיתנהג כמו Nehorai AI
- **Style Guide** — הגדרת הפרסונה, הטון, ומה מותר ומה אסור
- **Catchphrase Bank** — בנק משפטי מחץ מסודר עם כללי שימוש
- **Presets** — קבצים מוכנים לכל כלי
- **הוראות הטמעה** — copy-paste ברמת כל כלי

---

## למה הגרסה הרזה היא הכיוון הנכון

### מוטיבציה

אם המטרה היא open-source project שאנשים יכולים לחבר מהר, הפתרון הנכון הוא **לא** לבנות runtime חדש.

במקום זה — לתת קבצי הוראות מוכנים שמתלבשים על המנגנונים שכבר קיימים בכל כלי:
- ChatGPT Custom Instructions
- Cursor Rules (.mdc)
- Claude Code CLAUDE.md
- Gemini Gems
- Windsurf .windsurfrules

### מה **לא** עושים ב-v1

- ❌ מנגנון לומד
- ❌ memory חכם ודינמי
- ❌ phrase routing לפי היסטוריה
- ❌ SDK / npm package
- ❌ middleware server
- ❌ eval framework
- ❌ complex model adapters

### מה **כן** עושים ב-v1

- ✅ מחקר חד פעמי על הסגנון
- ✅ בנק משפטי מחץ
- ✅ Style Bible קצר
- ✅ פרומפטים מוכנים לפי פלטפורמה (6 כלים)
- ✅ README עם install בשתי דקות
- ✅ דוגמאות before/after
- ✅ DISCLAIMER ברור

---

## עקרונות מוצר

1. קודם כל תשובה טובה
2. הסגנון לא פוגע בדיוק
3. עברית טבעית לפני gimmick
4. משפטי מחץ בטעם טוב
5. לא כל תשובה הופכת לפרודיה
6. נושא רגיש → מורידים נפח
7. בקוד / JSON / YAML / SQL / shell — פלט נקי

---

## מבנה Voice Blend

```
70% קול האבא   → רגוע, בטוח, מחזק, סוגר עניין
30% קול נהוראי → חד, צעיר, קצבי, שובב
```

ניתן לכיוון עם presets:
- **Lite** — כמעט רק אבא
- **Balanced** — ברירת מחדל
- **Full Poscast** — יותר נהוראי, לדמואים ולצחוקים

---

## ארכיטקטורת הקבצים

```
nahory-ai/
  README.md
  LICENSE (MIT)
  DISCLAIMER.md
  docs/
    blueprint.md         ← את זה אתה קורא
    tone-guide.md
    catchphrase-bank.md
    installation.md
    v2-roadmap.md
  presets/
    chatgpt-custom-instructions.md
    generic-system-prompt.md
    cursor/
      nehorai.mdc
    claude/
      CLAUDE.md
    gemini/
      gem-instructions.md
    windsurf/
      .windsurfrules
      global_rules.md
  examples/
    before-after.md
    general-questions.md
    coding-questions.md
    sensitive-questions.md
  research/
    notes.md
    sources.md
```

---

## אכיפת הסגנון

בגרסה הזו האכיפה נעשית דרך **Prompt Design טוב**, לא דרך קוד.

כל preset כולל:
1. **Identity** — מי הפרסונה, מה מותר ומה אסור
2. **Language rules** — עברית טבעית כשהמשתמש בעברית
3. **Tone rules** — הגדרת הטון בשתי שורות
4. **Phrase library** — רשימת catchphrases inline
5. **Placement rules** — כמה ואיפה
6. **Per-context behavior** — general / code / sensitive / life
7. **Few-shot examples** — לפחות 2-3 דוגמאות

---

## שורה תחתונה

v1 = repo קטן + prompt pack טוב + כמה קבצים שימושיים + שפה טבעית + קצת Poscast + הרבה אהבה + אפס אובר-אינג'נירינג.

זה מספיק כדי שאנשים יוכלו לקחת, להדביק, ולהתחיל לדבר עם המודל בווייב הנכון תוך כמה דקות.

# Nehorai AI — v2 Roadmap

> v1 זה הבסיס. v2 זה כשנגדל.

---

## מה v1 נותן

- Prompt pack לכל כלי מרכזי
- Catchphrase bank
- Style guide
- Examples
- Copy-paste install

---

## v2 — כיוונים

### Phrase Rotation Engine
מנגנון פשוט (JS/Python) שמבטיח שאותו catchphrase לא יחזור שוב ב-n תשובות.  
אין צורך ב-LLM בשביל זה — רשימה + counter.

### CLI Installer
```bash
npx nehorai-ai install --tool cursor
npx nehorai-ai install --tool claude
npx nehorai-ai install --tool chatgpt
```
מעתיק את הקובץ הנכון למקום הנכון, אוטומטית.

### Content Packs
גרסאות מכוונות לפי אופי:
- `--mode aba` — 90% קול האבא, מינימום נהוראי
- `--mode nehorai` — 60% נהוראי, יותר שקט ויבש
- `--mode full-poscast` — מקסימום וייב

### IDE Extensions
- VS Code Extension — inject ל-Copilot/Continue system prompt
- JetBrains Plugin

### Benchmark Prompts
סט של 20+ prompt-and-expected-response שאפשר לבדוק איתם שהפרסונה נשמרת בין מודלים.

### Browser Extension
לוגיקה פשוטה שמוסיפה את ה-system prompt ל-ChatGPT web ואוטומטית.

### Stronger Dev Preset
גרסה מכוונת לפיתוח עם:
- יותר "עושים סדר" ופחות Poscast
- הגדרות ספציפיות לקוד ב-RTL
- דוגמאות code review

---

## מה עדיין לא לv2

- ❌ Agent system
- ❌ Fine-tuning
- ❌ Learning engine
- ❌ Server-side middleware
- ❌ Analytics platform

---

## איך לתרום

Pull requests מתקבלים לכל אחד מהכיוונים האלה.  
פתח Issue עם `[v2]` בכותרת ובוא נדון.

# Nehorai AI — v2 Roadmap

> v1 זה prompt pack. v2 זה כשנבנה משהו אמיתי.

---

## הרעיון הגדול

v1 עובד כי ה-LLMs טובים מספיק לפרש instructions.  
אבל prompt בלבד לא יחזיק — חזרתיות, inconsistency, ו-drift מגיעים מהר.

v2 הוא **middleware layer** שעוטף כל LLM ומאכף את הפרסונה *מחוץ* ל-prompt:

```
user input
    ↓
[ Tone Router ]        ← מחליט כמה "נהוראי" לפי סוג הבקשה
    ↓
[ LLM call ]           ← כל מודל — OpenAI, Anthropic, Gemini, local
    ↓
[ Phrase Injector ]    ← מוסיף catchphrases לפי placement rules
    ↓
[ Repetition Guard ]   ← מוודא שאותו משפט לא חזר לאחרונה
    ↓
[ Hebrew Naturalizer ] ← מוודא שזה נשמע עברית מדוברת, לא מתורגמת
    ↓
styled response
```

---

## מה בונים

### A. Phrase Registry — `phrases.he.json`

כל catchphrase עם metadata:

```json
{
  "phrase": "נודר נדר, זאת התשובה.",
  "speaker": "abba",
  "placement": "close",
  "tone_weight": 0.8,
  "frequency_cap": 3,
  "avoid_when": ["sensitive", "code_block"]
}
```

גמישות מלאה בלי לגעת ב-prompt.

### B. Tone Router

קלסיפיקציה פשוטה של הבקשה:

| סוג | כמה נהוראי | catchphrases |
|---|---|---|
| קוד / טכני | נמוך | רק לפני ואחרי |
| שאלה כללית | בינוני | opener + closer |
| החלטה / חיים | גבוה | full Poscast |
| רגיש | מינימום | 0–1 בלבד |

### C. SDK

```bash
npm install nehorai-ai
pip install nehorai-ai
```

```ts
import { nehoraiFetch } from 'nehorai-ai';

const response = await nehoraiFetch({
  model: 'gpt-4o',
  messages: [...],
  persona: 'balanced',  // lite | balanced | full-poscast
});
```

### D. Adapters

- `@nehorai-ai/openai`
- `@nehorai-ai/anthropic`
- `@nehorai-ai/gemini`
- `@nehorai-ai/generic`

### E. CLI Installer

```bash
npx nehorai-ai install --tool cursor
npx nehorai-ai install --tool claude
npx nehorai-ai install --tool chatgpt
```

### F. Content Packs

```bash
npx nehorai-ai install --mode aba       # 90% אבא
npx nehorai-ai install --mode nehorai   # 60% נהוראי, יבש, עמוק-שטוח
npx nehorai-ai install --mode poscast   # הכל פתוח
```

### G. Eval Harness

```bash
npx nehorai-ai eval --preset balanced --model gpt-4o
# ✅ Hebrew naturalness:  94%
# ✅ Catchphrase variety: 87%
# ❌ Repetition rate:     23%  (threshold: 15%)
# ✅ Code output clean:  100%
```

---

## מה לא ב-v2

- ❌ Fine-tuning
- ❌ Agent orchestration
- ❌ Learning engine
- ❌ Memory server

---

## איך לתרום

פתח Issue עם `[v2]` בכותרת.  
הכי נצרך: מי שרוצה לבנות את ה-Phrase Registry ואת ה-Node SDK.

נודר נדר — זה יהיה משהו.

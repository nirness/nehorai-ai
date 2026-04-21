# Nehorai AI — הוראות התקנה

> כל כלי — קובץ אחד. Copy, paste, גמרנו.

---

## ChatGPT

**קובץ:** [`presets/chatgpt-custom-instructions.md`](../presets/chatgpt-custom-instructions.md)

**צעדים:**
1. פתח [chat.openai.com](https://chat.openai.com)
2. לחץ על תמונת הפרופיל שלך → **Settings**
3. **Personalization** → **Custom Instructions**
4. בשדה "How would you like ChatGPT to respond?" — הדבק את ה-**Balanced** variant
5. שמור → פתח שיחה חדשה

**גרסאות:**
- `Lite` — אם רוצים קצת פחות פלייבור בעבודה יומיומית
- `Balanced` — ברירת מחדל מומלצת
- `Full Poscast` — בגנריק סיסטם פרומפט, לדמואים

**מגבלה:** ChatGPT Custom Instructions מוגבל ל-~1500 תווים. הגרסאות כתובות בהתאם.

---

## Cursor

**קובץ:** [`presets/cursor/nehorai.mdc`](../presets/cursor/nehorai.mdc)

**אפשרות א׳ — Project rule (מומלץ):**
```bash
# מתוך שורש הפרויקט
mkdir -p .cursor/rules
cp presets/cursor/nehorai.mdc .cursor/rules/nehorai.mdc
```

**אפשרות ב׳ — User rule גלובלי:**
1. Cursor → Settings → Rules
2. הדבק את תוכן `nehorai.mdc` בשדה User Rules

**הערה:** הפורמט `.mdc` עם `alwaysApply: true` בפרונטמטר מבטיח שהחוק תמיד פעיל.

---

## Claude Code

**קובץ:** [`presets/claude/CLAUDE.md`](../presets/claude/CLAUDE.md)

**אפשרות א׳ — Project level:**
```bash
cp presets/claude/CLAUDE.md ./CLAUDE.md
```

**אפשרות ב׳ — User level (כל הפרויקטים):**
```bash
cp presets/claude/CLAUDE.md ~/.claude/CLAUDE.md
```

**אפשרות ג׳ — דרך Claude Code:**
```
/memory
```
ואז הדבק את תוכן הקובץ ישירות.

**docs:** [Claude Code Memory](https://docs.anthropic.com/en/docs/claude-code/memory)

---

## Gemini

**קובץ:** [`presets/gemini/gem-instructions.md`](../presets/gemini/gem-instructions.md)

**צעדים:**
1. פתח [gemini.google.com](https://gemini.google.com)
2. בסרגל הצד — **Gems** → **Create a Gem** (או My Gems → New Gem)
3. שם: `Nehorai AI`
4. העתק את תוכן הקובץ ל-Instructions
5. שמור → התחל שיחה דרך ה-Gem

**הערה:** Gemini Gems פעיל רק ב-Gemini Advanced (Google One AI Premium).

---

## Windsurf

**קובץ:** [`presets/windsurf/.windsurfrules`](../presets/windsurf/.windsurfrules)

**אפשרות א׳ — Project level:**
```bash
cp presets/windsurf/.windsurfrules ./.windsurfrules
```
אפשר לעשות commit ולשתף עם הצוות.

**אפשרות ב׳ — Global (כל הפרויקטים):**
```bash
# הוסף לקובץ הגלובלי
cat presets/windsurf/global_rules.md >> ~/.codeium/windsurf/memories/global_rules.md
```

**docs:** [Windsurf Rules](https://docs.windsurf.com)

---

## Any LLM / API

**קובץ:** [`presets/generic-system-prompt.md`](../presets/generic-system-prompt.md)

מתאים ל:
- OpenAI API (`system` role)
- Anthropic API (`system` parameter)
- Local models (Ollama, LM Studio)
- כל מוצר שתומך ב-system prompt

```python
# דוגמה — OpenAI Python SDK
from openai import OpenAI
import pathlib

system_prompt = pathlib.Path("presets/generic-system-prompt.md").read_text()
# קח רק את הבלוק הרלוונטי (Balanced / Lite / Full)

client = OpenAI()
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "שלום"}
    ]
)
```

```python
# דוגמה — Anthropic Python SDK
import anthropic

client = anthropic.Anthropic()
message = client.messages.create(
    model="claude-opus-4-7",
    max_tokens=1024,
    system=system_prompt,
    messages=[{"role": "user", "content": "שלום"}]
)
```

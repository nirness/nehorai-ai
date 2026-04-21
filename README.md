# Nehorai AI 🎙️

> **ערס ישראלי פוגש הייטק.**
>
> חם, חצוף, מסתלבט, מבסתלב — ועונה תשובות טובות.
>
> הכל בהומור, בחיבה, ובאהבה גדולה.

---

## מה זה?

**Nehorai AI** הוא חבילת פרסונה לכל LLM — בהשראת הוייב של father-son Poscast ישראלי.

במקום לקבל תשובות מנומסות ומחוטבות, הכלי שלך עונה בעברית מדוברת, מסתלבט על בחירות גרועות, שותק דרמטית לפני תשובה חשובה, ומסיים עם "אבא אוהב."

```
User: "כדאי להשתמש ב-Redux?"

Nehorai AI:
...נודר שאתה עדיין שוקל Redux לפרויקט חדש?

בוא נדבר דוגרי — Zustand ב-2025 אלא אם יש לך צוות גדול ו-state מורכב ממש.

שאל את האבא אם אתה רוצה שנעמיק.
```

זה פרויקט fan-style — לא מוצר רשמי, לא קשור לאף גוף, הכל אהבה.

---

## התקנה בשתי דקות

| כלי | קובץ | מה עושים |
|---|---|---|
| **ChatGPT** | [`presets/chatgpt-custom-instructions.md`](presets/chatgpt-custom-instructions.md) | Settings → Personalization → Custom Instructions → הדבק |
| **Cursor** | [`presets/cursor/nehorai.mdc`](presets/cursor/nehorai.mdc) | העתק ל-`.cursor/rules/nehorai.mdc` |
| **Claude Code** | [`presets/claude/CLAUDE.md`](presets/claude/CLAUDE.md) | העתק ל-`./CLAUDE.md` בשורש הפרויקט |
| **Gemini** | [`presets/gemini/gem-instructions.md`](presets/gemini/gem-instructions.md) | Gems → Create a Gem → הדבק |
| **Windsurf** | [`presets/windsurf/.windsurfrules`](presets/windsurf/.windsurfrules) | העתק ל-`.windsurfrules` בשורש הפרויקט |
| **כל LLM אחר** | [`presets/generic-system-prompt.md`](presets/generic-system-prompt.md) | הדבק כ-system prompt |

הוראות מפורטות: [docs/installation.md](docs/installation.md)

---

## Presets

| Preset | מה מקבלים | מתי |
|---|---|---|
| **Lite** | מינימום flavor, מכסימום דיוק | עבודה יומיומית, context window קצר |
| **Balanced** | ברירת מחדל. וייב מספיק בלי להשתלט | כל שימוש רגיל |
| **Full Poscast** | כל הכלים, כל הביטויים | דמואים, צחוקים, גרסת max |

---

## הפרסונה

שני קולות:

**האבא (70%)** — בטוח, ישיר, מסתלבט, שותק דרמטית, מסיים עם "אבא אוהב."

**נהוראי (30%)** — שקט, יבש, "אנשים לא רגילים לראות דברים רגילים."

```
...                                          ← שתיקת האבא

זאת אשכרה הארכיטקטורה שבחרת?               ← סתלבטות

קיבלנו הצעות במיליונים על פחות מזה.         ← כסף

אנשים לא רגילים לראות דברים רגילים.         ← נהוראי being Nehorai

נודר נדר, זאת התשובה.                        ← סגירה קלאסית

אבא אוהב.                                    ← ריאקשן שלם
```

עוד על הפרסונה: [docs/tone-guide.md](docs/tone-guide.md)  
בנק המשפטים המלא: [docs/catchphrase-bank.md](docs/catchphrase-bank.md)

---

## דוגמאות

- [before-after.md](examples/before-after.md) — אותה שאלה, שתי תשובות
- [coding-questions.md](examples/coding-questions.md) — Redux, useEffect, TypeScript
- [general-questions.md](examples/general-questions.md) — קריירה, פרודוקטיביות, startup
- [sensitive-questions.md](examples/sensitive-questions.md) — כשמורידים נפח

---

## Open Source

**License:** [MIT](LICENSE)

פרויקט זה חופשי לשימוש, שיתוף ופורק.  
MIT מכסה את תוכן הריפו — ראה [DISCLAIMER.md](DISCLAIMER.md) לגבי שימוש בשמות ודמויות.

---

## Contributing

PRs מתקבלים לכל אחד מהדברים האלה:

- ✅ משפטי מחץ טובים יותר / חדשים
- ✅ דוגמאות נוספות
- ✅ תמיכה בכלים נוספים (Copilot, Continue, Cline...)
- ✅ presets חזקים יותר
- ✅ תיקון ניסוח

v2 roadmap: [docs/v2-roadmap.md](docs/v2-roadmap.md)

---

## Disclaimer

Fan-style project. Made with humor and affection.  
Not affiliated with, endorsed by, or officially connected to anyone.  
Full disclaimer: [DISCLAIMER.md](DISCLAIMER.md)

---

## References

- [Poscast](https://www.poscas.co.il/)
- [ChatGPT Custom Instructions](https://help.openai.com/en/articles/8096356-custom-instructions-for-chatgpt)
- [Cursor Rules](https://docs.cursor.com/context/rules)
- [Claude Code Memory](https://docs.anthropic.com/en/docs/claude-code/memory)
- [Gemini Gems](https://gemini.google/overview/gems/)
- [Windsurf Rules](https://docs.windsurf.com/windsurf/cascade/memories)

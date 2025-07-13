# 🛠 ODCA Audit Style Guide / Гайд по стилю RSA-аудитов ODCA

Версия / Version: 1.0.1  
Обновлено / Last updated: 2025-07-13


## 📌 Structure of the report / Структура отчёта

Every audit must follow the structure below:  
Каждый аудит должен соответствовать следующей структуре:

### 1. Title / Заголовок
[Type of protection] Factorization Analysis / Анализ факторизации  [Тип защиты]

### 2. Metadata / Метаданные

- **Last updated / Последнее обновление:** `DD-MM-YYYY HH:MM:SS`
- **Target description / Описание цели:**
  - Device and firmware version / Устройство и версия прошивки
  - Source of key (e.g., `rsrc`, `bootloader`, `.bss`) / Источник ключа (например, `rsrc`, `bootloader`, `.bss`)
  - Purpose of the key (signature, encryption, etc.) / Назначение ключа (подпись, шифрование и т.д.)
  - Firmware status (supported / legacy) / Статус прошивки (актуальна / устаревшая)

---

## 🔐 Modulus Section / Раздел с модулем

- **Modulus (N):** in decimal form / в десятичном виде  
- **Bit length / Длина в битах:** (примерно / approximate)  
- **RSA type / Тип RSA:** classic / multi-prime  
- **Status / Статус:** public / static / rotating / публичный / статичный / ротационный

---

## 🔎 Factorization Analysis / Анализ факторизации

### 1. Prime range / Диапазон простых чисел
- Example: from `2^1` to `2^34`  
- Пример: от `2^1` до `2^34`

### 2. Method / Методика
- Check `N % p == 0`  
- If yes: calculate `q = N / p`  
- If `q` is prime → save  
- Проверяем `N % p == 0`  
- Если да → `q = N / p`  
- Если `q` — простое → сохраняем

### 3. Found divisors table / Таблица найденных делителей

| `p`     | `q = N / p` | Prime? / Простое? |
|---------|--------------|-------------------|
| ...     | ...          | Yes / No / Да / Нет |

### 4. Comments / Комментарии
- Are the divisors full or partial? / Полные или частичные делители?
- Can `q` be factored further? / Можно ли дофакторизовать `q`?
- Can the private key be recovered? / Возможно ли восстановление приватного ключа?

---

## 🧪 Planned Work / Планируемая работа

List additional firmware versions or devices for future audits.  
Укажи, какие прошивки и устройства планируются к анализу.

---

## ⚠️ Legal & Ethical Disclaimer / Правовой и этический дисклеймер

**Required at the end of each report.**  
**Обязателен в конце каждого отчёта.**

> This report is for educational and research purposes only.  
> No private keys, exploits, or bypass tools are shared.  
> All data is from public, unsupported firmware.  
> Author does not encourage unauthorized modifications.  
>  
> Данный отчёт составлен исключительно в исследовательских и образовательных целях.  
> Приватные ключи, эксплойты и инструменты обхода не публикуются.  
> Все данные получены из общедоступной устаревшей прошивки.  
> Автор не поощряет несанкционированное вмешательство или модификацию.

---

📌Writing requirements/Требования к написанию 

## 📘 Language & Style / Язык и стиль

- Use **English or Russian or both side by side(It can probably translated later by another contributor)** / Использовать английский или русский или оба параллельно (позже может быть переведено другим контрибьютором)
- Be concise, technical, and neutral / Писать кратко, технически и нейтрально
- No slang or jokes in audit reports / Без сленга и шуток в отчётах
- Keep structure and terminology consistent / Сохранять единую структуру и термины

---

## ✅ Minimum Requirements / Минимальные требования

| Requirement / Требование             | Status / Статус |
|--------------------------------------|------------------|
| Modulus (N) is present / Модуль указан           | ✅                |
| Source & usage are described / Источник и назначение описаны | ✅                |
| At least one factoring attempt / Есть попытка факторизации     | ✅                |
| Disclaimer is added / Есть дисклеймер           | ✅                |
| Format follows ODCA structure / Соблюден стиль ODCA         | ✅                |

---

## 📂 File Format / Формат файлов

- Location: `/audits/Device Model`
Где располагается: `/audits/Device Model`
- Example: `/audits/iPod Nano 7`
- File names: `device_model_year_version.md`
Структура названия: `устройство_модель_годвыпуска_версия.md`
- Example: `ipod_nano_7_2012_1.0.4.md`
Пример:  `ipod_nano_7_2012_1.0.4.md` 
- Use **Markdown format(md)**
Используйте **Markdown формат(md)**

---

## 🤝 Contributing / Участие

If you're unsure — open an issue or ask in Discussions.  
Если не уверен — открой issue или задай вопрос в обсуждении.

---

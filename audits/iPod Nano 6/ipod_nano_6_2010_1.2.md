# RSA Modulus Factorization Analysis / Анализ факторизации RSA-модуля

---

## English Version

### 🔐 RSA Modulus Factorization Analysis Report

**Last updated:** 14‑07‑2025 09:18:05

#### Current target

- **Modulus (N):**
917246270421564620016257087783206155540151145460123884800776897141920124137479117266742615738648711897988091348172137336792407641210933948208248100666100731095380656690020698257893228157615867337929945951392708912272281079073849256091263303137061610568238415749350532005361804879928770759160607123894858819895107973253093702267676385757707378516862114957382491403078729694348337598847421994388344070939009680431
Extracted from the rsrc section of **iPod nano 6 (2010) firmware v1.2**. Used for firmware resource signature validation.

- **Bit length:** ~1366 bits

- **Type:** Presumably classic RSA (2‑prime)(But it may also be multi-prime)

- **Status:** Static and public (Apple ended support)



---

#### Factorization Analysis

- **Tested prime factors range:**  
From `2^1` up to `2^26` (all primes within this range).

- **Method:**  
For each prime `p` in the range:  
- Check if `N % p == 0`  
- If yes, compute `q = N / p`  
- Check if `q` is prime  
- If `q` is composite, discard this factor pair

- **Tools used:**  
Efficient prime generation and `gmpy2.is_prime` for primality tests.



---

#### Known Divisors (Potential Weaknesses)

| `p`     | `q = N // p`  | Prime?  |
|---------|----------------|----------|
| 3     | Composite    | No      |
| 13  | Composite    | No      |


> ⚠️ These partial factorizations imply:
>N = 3 × q₁ or N = 13 × q₂, where q₁ and q₂ are composite.
>Further factoring of q₁ or q₂ could enable calculation of the private key via standard RSA key‑recovery methods.
>Thus, despite compositeness, this indicates a potential cryptographic weakness.
> However, recent calculations have shown that this cannot be exploited in practice, because the resulting value either increases or does not change at all within the numerical range for each of these divisors when dividing.




---

#### Future Work

- Analyse the `rsrc` section of **iPod nano 7 (2015)** for similar RSA moduli and potential weaknesses.



---

### Legal & Ethical Disclaimer

This report is provided solely for educational and research purposes.

No private keys, exploits, or bypass tools are distributed.

All data is extracted from publicly available legacy firmware, unsupported by the manufacturer.

The author does **not endorse or encourage** unauthorized modification or exploitation of any hardware or software based on this information.

Use of this information is at your own risk.


---

## Русская версия

### 🔐 Отчёт по факторизации RSA-модуля

**Дата обновления:** 14‑07‑2025 09:18:05

#### Текущий объект исследования

- **Модуль (N):**
917246270421564620016257087783206155540151145460123884800776897141920124137479117266742615738648711897988091348172137336792407641210933948208248100666100731095380656690020698257893228157615867337929945951392708912272281079073849256091263303137061610568238415749350532005361804879928770759160607123894858819895107973253093702267676385757707378516862114957382491403078729694348337598847421994388344070939009680431
Извлечён из раздела `rsrc` прошивки **iPod nano 6 (2010) версии 1.2**.
Используется для проверки подписи ресурсов прошивки.

- **Длина:** ≈1366 бит

- **Тип:** предположительно классический RSA (2 простых множителя)(Но может оказаться и multi-prime(RSA с тремя и более множителями))

- **Статус:** статичный и публичный (поддержка Apple прекращена)



---

#### Анализ факторизации

- **Проверенный диапазон простых множителей:**  
От `2^1` до `2^26` (все простые числа в этом диапазоне).

- **Методика:**  
Для каждого простого `p` в диапазоне:  
- Проверяем делимость модуля `N` на `p`  
- Если делится без остатка, вычисляем `q = N / p`  
- Проверяем, простое ли число `q`  
- Если `q` составное — отбрасываем этот набор делителей

- **Используемые инструменты:**  
Генерация простых чисел и функция `gmpy2.is_prime` для проверки простоты.



---

#### Обнаруженные делители (возможные уязвимости)

| `p`     | `q = N // p`  | Prime?  |
|---------|----------------|----------|
| 3     | Composite    | No      |
| 13  | Composite    | No      |


> ⚠️ Эти частичные факторизации означают:
> N = 3 × q₁ или N = 13 × q₂, где q₁ и q₂ — составные числа.
> Дальнейшая факторизация q₁ или q₂ может позволить вычислить приватный ключ с помощью стандартных формул RSA.
> Таким образом, несмотря на составность, это указывает на потенциальную криптографическую уязвимость.
> Однако недавние расчёты показали, что это нельзя использовать на практике: при делении на каждый из этих делителей итоговое число либо увеличивается, либо вовсе не меняется в рассматриваемом числовом диапазоне.




---

### Планируемая работа

Провести анализ раздела `rsrc` на **iPod nano 7 (2015)** и проверить RSA‑модули на аналогичные слабости.



---

### Правовой и этический дисклеймер

Данный отчёт составлен исключительно в образовательных и исследовательских целях.

Приватные ключи, эксплойты и инструменты обхода защиты не распространяются.

Все данные получены из общедоступной устаревшей прошивки, не поддерживаемой производителем.

Автор не поддерживает и не поощряет несанкционированное использование, модификацию или эксплуатацию оборудования и программного обеспечения на основе представленной информации.

Использование данной информации осуществляется на ваш страх и риск.

---

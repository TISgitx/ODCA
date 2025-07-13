# RSA Modulus Factorization Analysis / Анализ факторизации RSA-модуля

---

## English Version

### 🔐 RSA Modulus Factorization Analysis Report

**Last updated:** 13-07-2025 20:18:32

#### Current target

- **Modulus (N):**
 148129810067701804347375862364260243755056432294671513835509436291244429162420502776094213432492261725758419206324427030934251597821835326244631266999650311136455805066529132928024055122662043896148576142450489037774591066538028798319303179295361625508269501878359027724615900379674237415848284197987493545062885680715005131895700975980773493236759497963219936670367205067130969258211965229404886597945509298109694498789316014882934250492452643973917508154894345869291551759010952513448332971694722261586949163

Extracted from the `rsrc` section of the **iPod nano 7 (2012) firmware v1.0.4**.  
Used for firmware resource signature validation.

- **Bit length:** ~1024 bits  
- **Type:** Presumably classic or multi-prime RSA  
- **Status:** Public and unchanging (Apple ended support)

#### Factorization Analysis

- **Tested prime factors range:**  
From `2^1` up to `2^34` (all primes within this range).

- **Method:**  
For each prime `p` in the range:  
- Check if `N % p == 0`  
- If yes, compute `q = N / p`  
- Check if `q` is prime  
- If `q` is composite, discard this factor pair

- **Tools used:**  
Efficient prime generation and `gmpy2.is_prime` for primality tests.

#### Known Divisors (Potential Weaknesses)

| `p`     | `q = N // p`  | Prime?  |
|---------|----------------|----------|
| 31     | Composite    | No      |
| 4549  | Composite    | No      |

> ⚠️ These partial factorizations imply:  
> N = 31 x q1 or N = 4549 x q2 or ... etc., where q1 and q2 are composite.  
> Further factoring of q1 or q2 could enable calculation of the private key via standard RSA key recovery methods.  
> Thus, despite compositeness, this indicates a potential cryptographic weakness.

#### My planned further work

- Continue analyzing the `rsrc` section of:  
  - **iPod nano 7 (2015)**  
  - **iPod nano 6**

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

**Дата обновления:** 13-07-2025 20:18:32

#### Текущий объект исследования

- **Модуль (N):**
 148129810067701804347375862364260243755056432294671513835509436291244429162420502776094213432492261725758419206324427030934251597821835326244631266999650311136455805066529132928024055122662043896148576142450489037774591066538028798319303179295361625508269501878359027724615900379674237415848284197987493545062885680715005131895700975980773493236759497963219936670367205067130969258211965229404886597945509298109694498789316014882934250492452643973917508154894345869291551759010952513448332971694722261586949163

Извлечён из раздела `rsrc` прошивки **iPod nano 7 (2012) версии 1.0.4**.  
Используется для проверки подписи ресурсов прошивки.

- **Длина:** примерно 1024 бита  
- **Тип:** предположительно классический или мультипрайм RSA  
- **Статус:** публичный и неизменяемый (поддержка Apple прекращена)

#### Анализ факторизации

- **Проверенный диапазон простых множителей:**  
От `2^1` до `2^34` (все простые числа в этом диапазоне).

- **Методика:**  
Для каждого простого `p` в диапазоне:  
- Проверяем делимость модуля `N` на `p`  
- Если делится без остатка, вычисляем `q = N / p`  
- Проверяем, простое ли число `q`  
- Если `q` составное — отбрасываем этот набор делителей

- **Используемые инструменты:**  
Генерация простых чисел и функция `gmpy2.is_prime` для проверки простоты.

#### Обнаруженные делители (возможные уязвимости)

| `p`     | `q = N / p` | Простое? |
|---------|--------------|------------|
| 31     | составное   | Нет      |
| 4549  | составное   | Нет      |

> ⚠️ Эти частичные факторизации означают:  
> N = 31 x q1 или N = 4549 x q2 или ... и т. д., где q1 и q2 — составные числа.  
> Дальнейшая факторизация q1 или q2 может позволить вычислить приватный ключ с помощью стандартных формул RSA.  
> Таким образом, несмотря на составность, это указывает на потенциальную криптографическую уязвимость.

#### Планируемая мною дальнейшая работа

- Продолжить анализ раздела `rsrc` для прошивок:  
  - **iPod nano 7 (2015)**  
  - **iPod nano 6**

---

### Правовой и этический дисклеймер

Данный отчёт составлен исключительно в образовательных и исследовательских целях.

Приватные ключи, эксплойты и инструменты обхода защиты не распространяются.

Все данные получены из общедоступной устаревшей прошивки, не поддерживаемой производителем.

Автор не поддерживает и не поощряет несанкционированное использование, модификацию или эксплуатацию оборудования и программного обеспечения на основе представленной информации.

Использование данной информации осуществляется на ваш страх и риск.

---

# RSA Modulus Factorization Analysis / Анализ факторизации RSA-модуля

---

## English Version

### 🔐 RSA Modulus Factorization Analysis Report

**Last updated:** 18‑07‑2025 20:25:57

#### Current target

- **Modulus (N):**
111261188801029666796663485905869440155437861608294504997757917289395150465727434819598166367557927759722244859006577519287542276311587449133937008779469090792077329289760503086588409265973770370454553066792187012594050974205614431051342043277612553333451183833487240349950170649057039964672805759227861133721


Extracted from the rsrc section of **iPod nano 6 (2010) firmware v1.2**. Used for firmware resource signature validation.

- **Bit length:** ~1024 bits

- **Type:** Presumably classic RSA (2‑prime)

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
| -     | -    | -      |
| -  | -    | -      |


> ❌ This modulus hasn't shown any additional multipliers or anything like that yet, so for now the number is cryptographically strong




---

#### Future Work

- Get more information about certificates of all images that are used on this device



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

**Дата обновления:** 18‑07‑2025 20:25:57

#### Текущий объект исследования

- **Модуль (N):**
111261188801029666796663485905869440155437861608294504997757917289395150465727434819598166367557927759722244859006577519287542276311587449133937008779469090792077329289760503086588409265973770370454553066792187012594050974205614431051342043277612553333451183833487240349950170649057039964672805759227861133721


Извлечён из раздела `rsrc` прошивки **iPod nano 6 (2010) версии 1.2**.
Используется для проверки подписи ресурсов прошивки.

- **Длина:** ≈1024 бит

- **Тип:** предположительно классический RSA (2 простых множителя)

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
| -     | -    | -      |
| -  | -    | -      |


> ❌ Этот модуль пока не показал никаких дополнительных множителей или чего-то подобного, так что на данный момент число является криптографически стойким.




---

### Планируемая работа

Получить дополнительную информацию о сертификатах всех разделов, используемых на этом устройстве.



---

### Правовой и этический дисклеймер

Данный отчёт составлен исключительно в образовательных и исследовательских целях.

Приватные ключи, эксплойты и инструменты обхода защиты не распространяются.

Все данные получены из общедоступной устаревшей прошивки, не поддерживаемой производителем.

Автор не поддерживает и не поощряет несанкционированное использование, модификацию или эксплуатацию оборудования и программного обеспечения на основе представленной информации.

Использование данной информации осуществляется на ваш страх и риск.

---

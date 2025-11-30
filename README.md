# RepasoPythonAssesment

## **✔ Iterar sobre una lista**

```python
for x in arr:
    ...
```

## **✔ Iterar con índices**

```python
for i in range(len(arr)):
    ...
```

## **✔ Slicing**

```python
arr[i:j]
```

## **✔ Ordenar**

```python
arr.sort()            # in place
sorted_arr = sorted(arr)  # copy
```

---

# 🧠 **2. HashMap (dict) — EL patrón más importante**


## **Crear**

```python
mp = {}
```

## **Agregar / actualizar**

```python
mp[key] = value
```

## **Obtener con valor por defecto**

```python
mp.get(key, default)
```

## **Contar cosas**

```python
from collections import defaultdict
cnt = defaultdict(int)
cnt[x] += 1
```

---

# ⚡ **3. Sets (para eliminar duplicados o buscar rápido)**

```python
s = set()
s.add(x)
if x in s:
    ...
```

---

# ➡️ **4. Two Pointers Template (arrays y strings)**

Para mover dos índices:

```python
l, r = 0, 0
while r < len(arr):
    # mover r hacia la derecha
    r += 1

    # mover l según condición
    while condition:
        l += 1
```

**Usado para:**

* longest substring
* subarrays
* sliding window problems
* removing duplicates

---

# 🔍 **5. Sliding Window Template (tu mejor amigo)**

### **Max/Min subarray with a condition**

```python
l = 0
current = 0
best = 0

for r in range(len(nums)):
    current += nums[r]

    while current > K:          # condición para reducir la ventana
        current -= nums[l]
        l += 1

    best = max(best, r - l + 1)
```

---

# ➕ **6. Prefix Sums Template**

Para sumas rápidas:

```python
prefix = [0]
for x in arr:
    prefix.append(prefix[-1] + x)

# suma entre i y j:
sum_ij = prefix[j+1] - prefix[i]
```

---

# 🌲 **7. DFS Template (grid)**

```python
def dfs(i, j):
    if i < 0 or j < 0 or i >= rows or j >= cols: return
    if grid[i][j] == 0: return

    grid[i][j] = 0

    dfs(i+1, j)
    dfs(i-1, j)
    dfs(i, j+1)
    dfs(i, j-1)
```

---

# 🔁 **8. BFS Template (cola)**

```python
from collections import deque

q = deque()
q.append((0,0))

while q:
    i, j = q.popleft()
    ...
```

---

# ✂️ **9. Strings esenciales**

```python
s[::-1]             # invertir
s.split()           # separar
"".join(list)       # unir
```

Contar caracteres:

```python
from collections import Counter
Counter(s)
```

---

# 🏗 **10. Ordenar por criterio**

```python
arr.sort(key=lambda x: x[1])
```

---

# 🔥 **BONUS: Plantilla general para resolver cualquier problema del OA**

1️⃣ Entiende rápido: “¿es hash map?”, “¿es sliding window?”, “¿es two pointers?”
2️⃣ Escribe la versión simple del código (aunque no sea óptima).
3️⃣ Prueba con estos edge cases:

* lista vacía
* lista con 1 elemento
* todos iguales
* valores extremos

4️⃣ Optimiza si hace falta.
5️⃣ Imprime o retorna el resultado.


¿Quieres intentarlo tú primero en Python y luego lo corregimos juntos?

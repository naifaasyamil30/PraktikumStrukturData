# Operasi Queue

## Konsep Queue
Queue adalah struktur data yang mengikuti prinsip **FIFO (First In First Out)** - elemen yang masuk pertama akan keluar pertama, seperti antrian di kasir. Program ini mendemonstrasikan operasi dasar pada struktur data **Queue (Antrian)** menggunakan Python list.

---

##  Operasi Queue

### 1. **membuat Queue**
```python
queue = []
```
- Membuat list kosong sebagai queue (antrian)

### 2. **Enqueue (menambah elemen)**
```python
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)
```
- `append()` menambahkan elemen ke **belakang** antrian
- Output: `Queue: ['A', 'B', 'C']`

### 3. **Dequeue (mengeluarkan Elemen)**
```python
element = queue.pop(0)
print("Dequeue: ", element)
```
- `pop(0)` mengambil dan menghapus elemen paling **depan** (index 0)
- Output: `Dequeue: A`
- Queue sekarang: `['B', 'C']`

### 4. **Peek (melihat elemen depan)**
```python
frontElement = queue[0]
print("Peek: ", frontElement)
```
- Melihat elemen paling depan **tanpa menghapusnya**
- Output: `Peek: B`

### 5. **isEmpty (mengecek Queue kosong)**
```python
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)
```
- Mengecek apakah queue kosong atau tidak
- Output: `isEmpty: False` (masih ada 'B' dan 'C')

### 6. **Size (ukuran Queue)**
```python
print("Size: ", len(queue))
```
- Menampilkan jumlah elemen dalam queue
- Output: `Size: 2` (tersisa 'B' dan 'C')

---

## Output Program

```
Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2
```

---

# Operasi Stack

## Konsep Stack
Stack adalah struktur data yang mengikuti prinsip **LIFO (Last In First Out)** - elemen yang masuk terakhir akan keluar pertama, seperti tumpukan piring. Program ini mendemonstrasikan operasi dasar pada struktur data **Stack (Tumpukan)** menggunakan Python list.

---

##  Operasi Stack

### 1. **membuat Stack**
```python
stack = []
```
- Membuat list kosong sebagai stack (tumpukan)

### 2. **Push (menambah Elemen)**
```python
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)
```
- `append()` menambahkan elemen ke **atas** tumpukan
- Output: `Stack: ['A', 'B', 'C']`

### 3. **Pop (mengeluarkan Elemen)**
```python
element = stack.pop()
print("Pop: ", element)
```
- `pop()` mengambil dan menghapus elemen paling **atas** (terakhir)
- Output: `Pop: C`
- Stack sekarang: `['A', 'B']`

### 4. **Peek (melihat Elemen atas)**
```python
topElement = stack[-1]
print("Peek: ", topElement)
```
- Melihat elemen paling atas **tanpa menghapusnya**
- Output: `Peek: B`

### 5. **isEmpty (mengecek Stack kosong)**
```python
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)
```
- Mengecek apakah stack kosong atau tidak
- Output: `isEmpty: False` (masih ada 'A' dan 'B')

### 6. **Size (ukuran Stack)**
```python
print("Size: ", len(stack))
```
- Menampilkan jumlah elemen dalam stack
- Output: `Size: 2` (tersisa 'A' dan 'B')

---

## Output Program

```
Stack:  ['A', 'B', 'C']
Pop:  C
Peek:  B
isEmpty:  False
Size:  2
```

---

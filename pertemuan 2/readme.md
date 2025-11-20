# Implementasi Linked List di Python

## Class Node

### Membuat class Node
```python
class Node:
```
Mendefinisikan class Node untuk membuat node dalam linked list.

### Constructor Node
```python
def __init__(self, data=None, pointer=None):
```
Method khusus yang dipanggil saat membuat object Node baru, menerima 2 parameter: data dan pointer.

### Atribut data
```python
self.data = data
```
Menyimpan nilai/data yang akan disimpan dalam node.

### Atribut next
```python
self.next = pointer
```
Menyimpan referensi/pointer ke node berikutnya dalam linked list.

---

## Class LinkedList

### Membuat class LinkedList
```python
class LinkedList:
```
Mendefinisikan class LinkedList sebagai struktur utama untuk mengelola linked list.

### Constructor LinkedList
```python
def __init__(self):
```
Method khusus yang dipanggil saat membuat object LinkedList baru.

### Inisialisasi head
```python
self.head = None
```
Membuat linked list kosong dengan head (awal list) bernilai None.

---

## Method insert_at_first(data)

### Definisi method insert_at_first
```python
def insert_at_first(self, data):
```
Mendefinisikan method untuk menambahkan node baru di awal linked list.

### Membuat node baru
```python
node = Node(data, self.head)
```
Membuat object Node baru dengan data yang diberikan, dan next-nya menunjuk ke head saat ini.

### Update head
```python
self.head = node
```
Menjadikan node baru sebagai head (node pertama) dari linked list.

---

## Method insert_at_last(data)

### Definisi method insert_at_last
```python
def insert_at_last(self, data):
```
Mendefinisikan method untuk menambahkan node baru di akhir linked list.

### Cek list kosong
```python
if self.head is None:
```
Mengecek apakah linked list masih kosong (head bernilai None).

### Insert di list kosong
```python
self.head = Node(data)
```
Jika list kosong, node baru langsung menjadi head.

### Kondisi list tidak kosong
```python
else:
```
Jika list tidak kosong, masuk ke blok code ini.

### Mulai dari head
```python
node_sekarang = self.head
```
Menyimpan referensi node head ke variabel node_sekarang untuk mulai traversal.

### Loop ke node terakhir
```python
while node_sekarang.next:
```
Melakukan perulangan selama node berikutnya masih ada (belum mencapai node terakhir).

### Pindah ke node berikutnya
```python
node_sekarang = node_sekarang.next
```
Memindahkan pointer node_sekarang ke node berikutnya dalam list.

### Buat node baru
```python
node = Node(data)
```
Membuat object Node baru dengan data yang diberikan.

### Hubungkan ke node terakhir
```python
node_sekarang.next = node
```
Menghubungkan node terakhir dengan node baru yang dibuat.

---

## Method insert_at(index, data)

### Definisi method insert_at
```python
def insert_at(self, index, data):
```
Mendefinisikan method untuk menambahkan node baru di posisi/index tertentu.

### Validasi index
```python
if index < 0 or index > self.length() - 1:
```
Mengecek apakah index yang diberikan valid (tidak negatif dan tidak melebihi panjang list).

### Pesan error index invalid
```python
print("indeks tidak valid")
```
Menampilkan pesan error jika index tidak valid.

### Cek insert di awal
```python
elif index == 0:
```
Mengecek apakah insert dilakukan di posisi 0 (awal list).

### Panggil insert_at_first
```python
self.insert_at_first(data)
```
Jika index 0, memanggil method insert_at_first untuk efisiensi.

### Kondisi insert di tengah/akhir
```python
else:
```
Jika index lebih dari 0, masuk ke blok code ini.

### Inisialisasi counter
```python
urutan = 0
```
Membuat variabel counter untuk melacak posisi saat traversal.

### Mulai dari head
```python
node_sekarang = self.head
```
Menyimpan referensi head untuk mulai traversal.

### Loop sampai sebelum index
```python
while urutan < index - 1:
```
Melakukan perulangan sampai mencapai node sebelum posisi insert.

### Increment counter
```python
urutan += 1
```
Menambah nilai counter sebesar 1 setiap iterasi.

### Pindah ke node berikutnya
```python
node_sekarang = node_sekarang.next
```
Memindahkan pointer ke node berikutnya.

### Buat node baru dengan pointer
```python
node = Node(data, node_sekarang.next)
```
Membuat node baru dengan next menunjuk ke node yang akan digeser.

### Berikan node baru
```python
node_sekarang.next = node
```
Menghubungkan node sebelumnya dengan node baru (menyisipkan node).

---

## Method remove_first()

### Definisi method remove_first
```python
def remove_first(self):
```
Mendefinisikan method untuk menghapus node pertama (head) dari linked list.

```python
if self.head is None:
```
Mengecek apakah linked list kosong.

```python
print("tidak ada data yang bisa dihapus")
```
Menampilkan pesan error jika tidak ada data yang bisa dihapus.

```python
else:
```
Jika list tidak kosong, masuk ke blok code ini.

```python
self.head = self.head.next
```
Memindahkan head ke node berikutnya, sehingga node pertama terhapus.

---

## Method remove_last()

```python
def remove_last(self):
```
Mendefinisikan method untuk menghapus node terakhir dari linked list.

```python
if self.head is None:
```
Mengecek apakah linked list kosong.

```python
print("tidak ada data yang bisa dihapus")
```
Menampilkan pesan error jika tidak ada data yang bisa dihapus.

```python
elif self.head.next is None:
```
Mengecek apakah hanya ada 1 node dalam list (next head adalah None).

```python
self.head = None
```
Menghapus satu-satunya node dengan set head menjadi None.

```python
else:
```
Jika ada lebih dari 1 node, masuk ke blok code ini.

```python
node_sebelumnya = None
```
Membuat variabel untuk menyimpan referensi node sebelum node terakhir.

```python
node_sekarang = self.head
```
Menyimpan referensi head untuk mulai traversal.

### Loop ke node terakhir
```python
while node_sekarang.next:
```
Melakukan perulangan sampai mencapai node terakhir.

### Simpan node sebelumnya
```python
node_sebelumnya = node_sekarang
```
Menyimpan node saat ini sebagai node sebelumnya sebelum pindah.

### Pindah ke node berikutnya
```python
node_sekarang = node_sekarang.next
```
Memindahkan pointer ke node berikutnya.

### Putus koneksi node terakhir
```python
node_sebelumnya.next = None
```
Memutus koneksi ke node terakhir dengan set next menjadi None (menghapus node terakhir).

## Method remove_at(index)

### Definisi method remove_at
```python
def remove_at(self, index):
```
Mendefinisikan method untuk menghapus node di posisi/index tertentu.

### Validasi index
```python
if index < 0 or index >= self.length():
```
Mengecek apakah index yang diberikan valid (tidak negatif dan tidak melebihi atau sama dengan panjang list).

### Pesan error index invalid
```python
print("index invalid")
```
Menampilkan pesan error jika index tidak valid.

### Cek hapus di awal
```python
elif index == 0:
```
Mengecek apakah hapus dilakukan di posisi 0 (awal list).

### Panggil remove_first
```python
self.remove_first()
```
Jika index 0, memanggil method remove_first untuk efisiensi.

### Kondisi hapus di tengah/akhir
```python
else:
```
Jika index lebih dari 0, masuk ke blok code ini.

### Inisialisasi counter
```python
urutan = 0
```
Membuat variabel counter untuk melacak posisi saat traversal.

### Mulai dari head
```python
node_sekarang = self.head
```
Menyimpan referensi head untuk mulai traversal.

### Loop sampai sebelum index
```python
while urutan < index - 1:
```
Melakukan perulangan sampai mencapai node sebelum posisi hapus.

### Pindah ke node berikutnya
```python
node_sekarang = node_sekarang.next
```
Memindahkan pointer ke node berikutnya.

### Increment counter
```python
urutan += 1
```
Menambah nilai counter sebesar 1 setiap iterasi.

### Lewati node yang dihapus
```python
node_sekarang.next = node_sekarang.next.next
```
Menghubungkan node sebelumnya langsung ke node setelah node yang dihapus (melewati node yang akan dihapus).

---

## Method print()

### Definisi method print
```python
def print(self):
```
Mendefinisikan method untuk menampilkan semua data dalam linked list.

### Cek list kosong
```python
if self.head is None:
```
Mengecek apakah linked list kosong.

### Pesan list kosong
```python
print("data kosong")
```
Menampilkan pesan jika list kosong.

### Kondisi list tidak kosong
```python
else:
```
Jika list tidak kosong, masuk ke blok code ini.

### Inisialisasi string hasil
```python
text_print = ''
```
Membuat variabel string kosong untuk menampung hasil yang akan di-print.

### Mulai dari head
```python
node_sekarang = self.head
```
Menyimpan referensi head untuk mulai traversal.

### Loop semua node
```python
while node_sekarang:
```
Melakukan perulangan selama masih ada node (sampai None).

### Tambahkan data ke string
```python
text_print += str(node_sekarang.data) + "→"
```
Menambahkan data node saat ini dan asimbol panah ke string hasil.

### Pindah ke node berikutnya
```python
node_sekarang = node_sekarang.next
```
Memindahkan pointer ke node berikutnya.

### Print hasil akhir
```python
print(text_print)
```
Menampilkan string yang berisi semua data linked list.

---

## Method length()

### Definisi method length
```python
def length(self):
```
Mendefinisikan method untuk menghitung jumlah node dalam linked list.

```python
urutan = 0
```
Membuat variabel counter untuk menghitung jumlah node.

### Mulai dari head
```python
data_sekarang = self.head
```

### Loop semua node
```python
while data_sekarang:
```
Melakukan perulangan selama masih ada node (sampai None).

### Pindah ke node berikutnya
```python
data_sekarang = data_sekarang.next
```
Memindahkan pointer ke node berikutnya.

```python
urutan += 1
```
Menambah counter sebesar 1 untuk setiap node yang dilalui.

### Return jumlah node
```python
return urutan
```
Mengembalikan nilai counter yang berisi jumlah total node dalam linked list.

---

## Eksekusi Program

### Membuat instance LinkedList
```python
ll = LinkedList()
```
Membuat object LinkedList baru dengan nama variabel `ll`.

```python
ll.insert_at_first("jeruk")
```
Method insert_at_first untuk menambahkan "jeruk" di posisi pertama. Hasil: [jeruk]

```python
ll.insert_at_first("mangga")
```
Method insert_at_first untuk menambahkan "mangga" di posisi pertama. Hasil: [mangga→jeruk]

```python
ll.insert_at_first("manggis")
```
Method insert_at_first untuk menambahkan "manggis" di posisi pertama. Hasil: [manggis→mangga→jeruk]

```python
ll.insert_at_last("apel")
```
Method insert_at_last untuk menambahkan "apel" di posisi terakhir. Hasil: [manggis→mangga→jeruk→apel]

```python
ll.insert_at(2, "anggur")
```
Method insert_at untuk menambahkan "anggur" di index 2. Hasil: [manggis→mangga→anggur→jeruk→apel]

```python
ll.remove_first()
```
Method remove_first untuk menghapus "manggis". Hasil: [mangga→anggur→jeruk→apel]

```python
ll.remove_last()
```
Method remove_last untuk menghapus "apel". Hasil: [mangga→anggur→jeruk]

```python
ll.remove_at(1)
```
Method remove_at untuk menghapus "anggur" di index 1. Hasil: [mangga→jeruk]

```python
ll.remove_at(1)
```
Method remove_at untuk menghapus "jeruk" di index 1. Hasil: [mangga]

### Tampilkan linked list
```python
ll.print()
print(ll.length())
```
## Output:
`mangga → 1`

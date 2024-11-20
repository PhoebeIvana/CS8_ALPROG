# Case Study 8
```bash
Nama    : [Kaera Yukio || CHANGE ME]
NPM     : [2306839344 || CHANGE ME]
```
---
Kalian diminta untuk membuat program pengelolaan **toko buku** dengan menggunakan konsep **single linked list**. Toko ini ingin memiliki sistem pencatatan buku dengan beberapa ketentuan, yaitu sebagai berikut:
## Struktur Node
Setiap buku disimpan dalam node dengan informasi berikut:
1. **ID Buku** (integer)
2. **Judul Buku** (string)
3. **Harga Buku** (integer)
4. **Stok Buku** (integer)
5. Pointer ke node berikutnya.

## Kalian diminta untuk melengkapi program ini agar dapat bekerja dengan baik. Berikut fungsi yang dibutuhkan:
1. **`addBookAtPosition`**  
   Menambahkan buku baru di posisi tertentu (indeks 1-based). Jika posisi lebih besar dari jumlah node, maka tambahkan data pada posisi terakhir.

2. **`deleteBookByID`**  
   Menghapus buku berdasarkan ID Buku. Jika ID tidak ditemukan, maka akan ditampilkan pesan error.

3. **`updateStock`**  
   Mengupdate jumlah stok sebuah buku berdasarkan ID Buku. Jika ID tidak ditemukan, maka akan ditampilkan pesan error.

4. **`findBookByTitle`**  
   Mencari buku berdasarkan judul. Jika ada lebih dari satu buku dengan judul yang sama, maka kembalikan ID dan informasi buku pertama yang ditemukan.

## Program yang Diprovide
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct Book {
    int id;
    char title[100];
    int price;
    int stock;
    struct Book *next;
} Book;

// Fungsi untuk membuat node baru
Book* createBook(int id, char *title, int price, int stock) {
    Book *newBook = (Book*)malloc(sizeof(Book));
    newBook->id = id;
    strcpy(newBook->title, title);
    newBook->price = price;
    newBook->stock = stock;
    newBook->next = NULL;
    return newBook;
}

// TODO 1: Tambahkan fungsi `addBookAtPosition`

// TODO 2: Tambahkan fungsi `deleteBookByID`

// TODO 3: Tambahkan fungsi `updateStock`

// TODO 4: Tambahkan fungsi `findBookByTitle`


int main() {
    Book *head = NULL;

    int choice, id, price, stock, position;
    char title[100];
    do {
        printf("\n=== Toko Buku ===\n");
        printf("1. Tambah Buku di Posisi Tertentu\n");
        printf("2. Hapus Buku berdasarkan ID\n");
        printf("3. Update Stok Buku\n");
        printf("4. Cari Buku berdasarkan Judul\n");
        printf("0. Keluar\n");
        printf("Pilih: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Masukkan posisi, ID, Judul, Harga, dan Stok: ");
                scanf("%d %d %s %d %d", &position, &id, title, &price, &stock);
                // Panggil fungsi `addBookAtPosition`
                break;
            case 2:
                printf("Masukkan ID buku yang ingin dihapus: ");
                scanf("%d", &id);
                // Panggil fungsi `deleteBookByID`
                break;
            case 3:
                printf("Masukkan ID dan stok terbaru: ");
                scanf("%d %d", &id, &stock);
                // Panggil fungsi `updateStock`
                break;
            case 4:
                printf("Masukkan judul buku yang ingin dicari: ");
                scanf("%s", title);
                // Panggil fungsi `findBookByTitle`
                break;
            case 0:
                printf("Terima kasih.\n");
                break;
            default:
                printf("Pilihan tidak valid. Silakan coba beberapa saat kembali.\\n");
        }
    } while (choice != 0);
    return 0;
```

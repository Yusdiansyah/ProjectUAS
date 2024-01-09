# ProjectUAS
# Nama  : Yusdiansyah Andika H.S
# NIM   : 312310650
# Kelas : TI.23.A6

## Program kasir kantin
 + membuat list menu yang akan digunakan
   ```python
   menu = {contoh1, contoh2}
   ```
 + Membuat interface pengguna untuk memesan
   ```python
   print("+=============================+")
   print("| No |   Makanan      | Harga |")
   print("+=====================+=======+")
   for i, (item, harga) in enumerate(menu.items(), start=1):
    print(f"| {i:2d} | {item:14} | {harga:5} |")
   print("+=============================+")

Disini menggunakan enumerate agar memudahkan pembeli untuk memesan dengan memasukan nomor.

+ Buat list baru untuk menyimpan pesanan pengguna

```
pesanan_sekarang = {}
```

+ Looping dalam menerima pesanan
```python
while True:
    pesanan = input("Masukan nomor pesanan (Tulis selesai untuk mengakhiri): ")
    
    if pesanan.lower() == 'selesai':
         break
        
    try:
        pesanan = int(pesanan)
        if 1 <= pesanan <= len(menu):
                dipesan = list(menu.keys()) [pesanan - 1]

                if dipesan in pesanan_sekarang:
                    pesanan_sekarang[dipesan] += 1
                else:
                    pesanan_sekarang[dipesan] = 1
        else: 
            print("Pilihan tidak valid")
    except ValueError:
            print("Masukan nomor yang valid")
```
<P>Disini menggunakan metode try & exception dalam proses loopingnya.</P> 
<P>Sistem akan meminta input pengguna untuk melanjutkan atau mengakhiri program.</P> 
<P>program looping akan berakhir jika pengguna memasukan 'selesai' sebagai input.</P>

+ list terakhir untuk menghitung pesanan pelanggan
```python
total_harga = sum(menu[item]*pesanan_sekarang[item] for item in pesanan_sekarang)
```
+ Bagian akhir yaitu menampilkan hasil perhitungan dari menu yang di pesan oleh pelanggan
```python
print("Struk Pembelian")
for item,jumlah in pesanan_sekarang.items():
    print(f"pilihan menu: {item} - jumlah: {jumlah} - harga: {menu[item]*jumlah} ")

print(f"\nTotal Pembelian: {total_harga}")
```

<P>Itu dia kode singkat untuk program kasir kantin</P>
<P>Terima Kasih</P>



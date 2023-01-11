# UAS

# 1.Main.py berisi program utama
```phyton
from view import input_nilai, view_nilai
from model import daftar_nilai

data = daftar_nilai.Data_mahasiswa()

print("="*20)
print("|PROGRAM INPUT DATA|")
print("="*20)

while True: 
    print()
    menu = input("[(T)ambah, (I)nputNilai, (L)ihat, (C)ari, (H)apus, (U)bah, (K)eluar] : ")
    print("~"*78)
    print()

    if menu.lower() == 't':
        data.tambah()


    elif menu.lower() == "i":
        input_nilai.nilai()


    elif menu.lower() == 'l':
        if data.nama:
            view_nilai.lihat()
        else:
            print("BELUM ADA DATA!, pilih [T/t] untuk menambah data")  

    elif menu.lower() == 'c':
        if data.nama:
            data.cari()
        else:
            print("BELUM ADA DATA!, pilih [T/t] untuk menambah data") 
            

    elif menu.lower() == "h":
        data.hapus(data.nama)


    elif menu.lower() == "u":
        data.ubah(data.nama) 

    elif menu.lower() == "k":
        print("Program selesai, Terima Kasih :) ")
        break

    else:
        print("\n INPUT {} TIDAK ADA!, Silakan pilih [T/L/I/H/U/K] untuk menjalankan program!".format(menu))
```
# Penjelasan
Didalam program utama terdapat modul yang di import ke file 'from view import input_nilai', 'view_nilai' & 'from model import daftar_nilai'.

### contoh tampilan menu :
# ![Screenshot 2023-01-10 233934](https://user-images.githubusercontent.com/116090827/211700188-b60e8cfd-ddb9-4867-9e24-d8077f5ae27c.png)

# 2.daftar_nilai.py
 Didalam daftar_nilai memiliki sourcecode dibawah ini
 
 ```phython
 class Data_mahasiswa:
    nama = []
    nim = []
    uts = []
    uas = []
    tugas = []

    # Tambah data
    def tambah(self):
        print("Tambah data\n")
        nama    = input("Nama           : ")
        self.nama.append(nama)
        nim     = int(input("NIM            : "))
        self.nim.append(nim)
        uts     = 0
        self.uts.append(uts)
        uas     = 0
        self.uas.append(uas)
        tugas   = 0
        self.tugas.append(tugas)

        print("\nData {0} berhasil di tambahkan".format(nama))
                
    # Menghapus inputan nama
    def hapus(self, nama):
        print("Hapus data inputan")
        print("="*15)
        nama = (input("\nMasukan Nama berdasarkan inputan : "))
        if nama in self.nama:
            print("Data {0} berhasil di hapus".format(nama))
            index = self.nama.index(nama)
            del self.nama[index]
            del self.nim[index]
            del self.uts[index]
            del self.uas[index]
            del self.tugas[index]
        else:
            print("NAMA {0} TIDAK ADA!".format(nama))
    
        # Mengubah data NIM
    def ubah(self, nama):
        print("Ubah data NIM")
        print("="*15)
        input_nama = input("Masukan Nama : ")
        if input_nama in nama:
            index = nama.index(input_nama)
            self.nim[index]     = int(input("NIM            : "))

            print("\nNIM Data {0} berhasil di ubah".format(input_nama))
        else:
            print("NAMA {0} TIDAK ADA! / ANDA BELUM MENAMBAHKAN DATA".format(input_nama))
            
        # Mencari data yg sudah di input 
    def cari(self):
        print("Mencari data")
        print("="*15)
        nama = (input("\nMasukan Nama yg ingin di cari : "))
        if nama in self.nama:
            index = self.nama.index(nama)
            print(f"Nama Mahasiswa: {self.nama[index]}")
            print(f"NIM Mahasiswa : {self.nim[index]}")
            print(f"Nilai UTS     : {self.uts[index]}")
            print(f"Nilai UAS     : {self.uas[index]}")
            print(f"Nilai TUGAS   : {self.tugas[index]}")
        else:
            print("NAMA {0} TIDAK ADA!".format(nama))
            
# Penjelasan 
 Pada bagian daftar_nilai.py berisi program untuk menambahkan data,hapus data,ubah data NIM,dan mencari data.
 
## Tampilan output tambah data ;

# ![Screenshot_20230110_102233](https://user-images.githubusercontent.com/116090827/211703072-af367e25-4aee-457a-8da9-778ab22954cd.png)





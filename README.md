# latihan 1 
# mengubah kode menjadi fungsi lambda
input : 

    import math
    
    # Menggunakan lambda untuk mendefinisikan fungsi
    a = lambda x: x**2
    b = lambda x, y: math.sqrt(x**2 + y**2) 
    c = lambda *args: sum(args) / len(args) if args else 0  
    d = lambda s: "".join(set(s))
    
    if __name__ == "__main__": 
        print("a(5):", a(5))
        print("b(3, 4):", b(3, 4))
        print("c(1, 2, 3, 4, 5):", c(1, 2, 3, 4, 5))
        print("d('hello world'):", d('hello world'))  
output: 
![Screenshot 2024-11-28 121934](https://github.com/user-attachments/assets/7e03ab79-f739-4a3a-8560-29816c3da681)
# praktikum 
    Buat program sederhana dengan mengaplikasikan penggunaan fungsi
    yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan:
    1. Fungsi tambah() untuk menambah data
    2. Fungsi tapilkan() untuk menampilkan data
    3. Fungsi hapus(nama) untuk menghapus data berdasarkan nama
    4. Fungsi ubah(nama) untuk mengubah data berdasarkan nama
 _flowchart_: 









 _kode program_:
 _input_:
 
    # Daftar untuk menyimpan data mahasiswa
    data_mahasiswa = []
    
    # Fungsi untuk menambah data mahasiswa
    def tambah():
        nama = input("Masukkan nama mahasiswa: ")
        nim = input("Masukkan NIM: ")
        nilai = float(input("Masukkan nilai: "))
        data_mahasiswa.append({"nama": nama, "nim": nim, "nilai": nilai})
        print("Data berhasil ditambahkan.")
    
    # Fungsi untuk menampilkan data mahasiswa
    def tampilkan():
        if not data_mahasiswa:
            print("Tidak ada data mahasiswa.")
        else:
            print("Daftar Data Mahasiswa:")
            for i, mahasiswa in enumerate(data_mahasiswa, start=1):
                print(f"{i}. Nama: {mahasiswa['nama']}, NIM: {mahasiswa['nim']}, Nilai: {mahasiswa['nilai']}")
    
    # Fungsi untuk menghapus data mahasiswa berdasarkan nama
    def hapus(nama):
        for mahasiswa in data_mahasiswa:
            if mahasiswa['nama'].lower() == nama.lower():
                data_mahasiswa.remove(mahasiswa)
                print(f"Data mahasiswa dengan nama {nama} berhasil dihapus.")
                return
        print(f"Data mahasiswa dengan nama {nama} tidak ditemukan.")
    
    # Fungsi untuk mengubah data mahasiswa berdasarkan nama
    def ubah(nama):
        for mahasiswa in data_mahasiswa:
            if mahasiswa['nama'].lower() == nama.lower():
                print(f"Data lama: Nama: {mahasiswa['nama']}, NIM: {mahasiswa['nim']}, Nilai: {mahasiswa['nilai']}")
                mahasiswa['nama'] = input("Masukkan nama baru: ")
                mahasiswa['nim'] = input("Masukkan NIM baru: ")
                mahasiswa['nilai'] = float(input("Masukkan nilai baru: "))
                print("Data berhasil diubah.")
                return
        print(f"Data mahasiswa dengan nama {nama} tidak ditemukan.")
    
    # Menu utama
    def menu():
        while True:
            print("\nMenu:")
            print("1. Tambah Data")
            print("2. Tampilkan Data")
            print("3. Hapus Data")
            print("4. Ubah Data")
            print("5. Keluar")
            pilihan = input("Pilih menu (1-5): ")
    
            if pilihan == "1":
                tambah()
            elif pilihan == "2":
                tampilkan()
            elif pilihan == "3":
                nama = input("Masukkan nama mahasiswa yang akan dihapus: ")
                hapus(nama)
            elif pilihan == "4":
                nama = input("Masukkan nama mahasiswa yang akan diubah: ")
                ubah(nama)
            elif pilihan == "5":
                print("Keluar dari program.")
                break
            else:
                print("Pilihan tidak valid. Silakan coba lagi.")
    
    # Menjalankan menu utama
    menu()

_output_:

![Screenshot 2024-11-28 124850](https://github.com/user-attachments/assets/20da5366-16a4-4c2e-9d7d-f05d620292d2)
![Screenshot 2024-11-28 124904](https://github.com/user-attachments/assets/a01c23e1-3500-4137-b284-4778afe45c43)

_penjelasan program_:
1. Data Mahasiswa:
Data mahasiswa disimpan dalam list data_mahasiswa, yang berisi dictionary untuk setiap mahasiswa dengan atribut nama, nim, dan nilai.
2. Fungsi:
- tambah(): Meminta input dari pengguna untuk menambah data mahasiswa baru ke dalam list.
- tampilkan(): Menampilkan semua data mahasiswa yang ada. Jika tidak ada data, akan menampilkan pesan bahwa tidak ada data mahasiswa.
- hapus(nama): Menghapus data mahasiswa berdasarkan nama yang diberikan. Jika nama tidak ditemukan, akan menampilkan pesan yang sesuai.
- ubah(nama): Mengubah data mahasiswa berdasarkan nama. Jika nama ditemukan, pengguna dapat mengubah nama, NIM, dan nilai. Jika tidak ditemukan, akan menampilkan pesan 
  yang sesuai.
3. Menu Utama:
  Fungsi menu() menampilkan menu interaktif kepada pengguna untuk memilih tindakan yang diinginkan (tambah, tampilkan, hapus, ubah, atau keluar). Program akan terus 
  berjalan hingga pengguna memilih untuk keluar.

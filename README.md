### Nama    : Mohammad Azmi Abdussyukur
### NIM     : 312210109
### Kelas   : TI.22.A.1

## Latihan Menggunakan Function dan Lambda Pada Python dan membuat program crud sederhana

### Reporsitory ini sebagai tugas kuliah bahasa pemograman


1. Pertama masukkan codingan ini, lalu run :

              import math
              # Mohammad Azmi Abdussyukur
              # TI.22.A.1
              def a(n): return lambda x: x**n

              lambdaA = a(4)
              print(lambdaA(4))

              def b(i, j):
                  return lambda x, y: math.sqrt(x**i + y**j)

              lambdaB = b(4,0)
              print(lambdaB(3,0))

              def c(*args):
                  return lambda *params: sum (args) / len(params)

              lambdaC = c(1,2,3,4,5)
              print(lambdaC(2,2,5))

              def d(firstname):
                  return lambda *lastname: "".join(set(firstname)) + "".join(set(lastname))

              lambdaD = d("Mohammad")
              print(lambdaD("Azmi", "Abdussyukur"))
              
              
Dan Berikut Hasilnya :

![Latiham](https://user-images.githubusercontent.com/115864496/205640373-63a678f4-7dec-4bbd-9830-f97eb09343a0.png)


2. Selanjutnya kita akan buat program crud sederhana dan berikut flowchart program yang akan di buat.



3. Lalu Buka file Pratikum6.py dan masukkan codingan sebagi berikut lau run :

              from os import system
              s_nama = []
              s_nim = []
              s_tugas = []
              s_uts = []
              s_uas = []
              s_akhir = []


              def judul():
                  print('==================================')
                  print('|     Daftar Nilai Mahasiswa     |')
                  print('==================================')


              def menu():
                  system('cls')
                  print('=====================================')
                  print('Input Data Nilai Mahasiswa'.center(40))
                  print('=====================================')
                  print('|    1. Tambah Data                 |')
                  print('|    2. Tampilkan Data Mahasiswa    |')
                  print('|    3. Ubah Data Mahasiswa         |')
                  print('|    4. Hapus Data Mahasiswa        |')
                  print('|    5. Selesai                     |')
                  print('=====================================')
                  choose = input('Pilih Menu  : ')
                  if choose == '1':
                      tambah()
                  elif choose == '2':
                      tampilkan()
                  elif choose == '3':
                      ubah()
                  elif choose == '4':
                      hapus()
                  elif choose == '5':
                      selesai()
                  else:
                      tidak = input('Menu Tidak Ada')
                      system('cls')
                      menu()


              def tambah():
                  system('cls')
                  judul()
                  print('Tambah Data'.center(40))
                  print('==================================')
                  nama = input('Nama     : ')
                  s_nama.append(nama)
                  nim = input('NIM       : ')
                  s_nim.append(nim)

                  system('cls')
                  judul()
                  print('Tambah Data'.center(40))
                  print('==================================')
                  tugas = float(input('Nilai Tugas    : '))
                  s_tugas.append(tugas)

                  uts = float(input('Nilai UTS        : '))
                  s_uts.append(uts)

                  uas = float(input('Nilai UAS        : '))
                  s_uas.append(uas)

                  total = tugas * 0.30 + uts * 0.35 + uas * 0.35
                  s_akhir.append(total)
                  print('Data Tersimpan'.center(40))
                  kembali = input('Kembali [Enter]')
                  menu()


              def tampilkan():
                  system('cls')
                  judul()

                  for i in range(len(s_nim)):
                      print('%d. Nama         : %s' % (i + 0, s_nama[i]))
                      print('    NIM          : %s' % s_nim[i])
                      print('    Nilai Tugas  : %.2f' % s_tugas[i])
                      print('    UTS          : %.2f' % s_uts[i])
                      print('    UAS          : %.2f' % s_uas[i])
                      print('    Nilai Akhir  : %.2f' % s_akhir[i])
                      print('-----------------------------')
                  kembali = input('Kembali Tekan [Enter]')
                  menu()


              def ubah():
                  rubah = input('Ubah Biodata Tekan [B]   : ')
                  if rubah == 'B' or rubah == 'b':
                      i = int(input('Masukkan Nomor Urut  : '))
                      if (i > len(s_nim[i])):
                          print('Nomor Urut Salah')
                      else:
                          namabaru = input('Nama      : ')
                          s_nama[i] = namabaru
                  kembali = input('Kembali Tekan [Enter]')
                  menu()


              def hapus():
                  system('cls')
                  judul()
                  print('Hapus Data'.center(40))
                  print('=================================')
                  i = int(input('Masukkan Nomor Urut  : '))

                  if (i > len(s_nim[i])):
                      tidak = input('NIM Tidak Ada')
                      hapus()

                  else:
                      s_nim.remove(s_nim[i])
                      s_nama.remove(s_nama[i])
                      s_tugas.remove(s_tugas[i])
                      s_uts.remove(s_uts[i])
                      s_uas.remove(s_uas[i])
                      s_akhir.remove(s_akhir[i])

                  print('Data Berhasil Di Hapus')
                  kembali = input('Kembali Tekan [Enter]')
                  menu()


              def selesai():
                  system('')



              menu()
              
              
              
Dan berikut hasil runnya :

Jika memilih opsi 1 = Tambah Data maka akan tampil sebagai berikut :

![Tambah Data](https://user-images.githubusercontent.com/115864496/205642533-591077a1-1d73-4bb8-aa4a-fde916302340.png)


Jika memilih Opsi 2 = Melihat Data Maka tampil sebagai berikut :

![Melihat Data](https://user-images.githubusercontent.com/115864496/205642778-ee9be6c2-14b6-4130-a1dd-86bb7287013a.png)


Jika memilih opsi 3 = Mengubah Data Maka tampil sebagai berikut :

![Mengubah Data](https://user-images.githubusercontent.com/115864496/205643019-e8c2b65f-246a-4688-a4ec-e3eb530ce016.png)


Jika memilih opsi 4 = Menghapus Data Maka tampil sebagai berikut :

![Menghapus Data](https://user-images.githubusercontent.com/115864496/205643527-6ed76b9e-54e2-4c0d-9c2c-d1e474196948.png)


Jika memilih opsi 5 = Doneeee Maka akan codingan selesai :

![Doneee](https://user-images.githubusercontent.com/115864496/205643773-a6ad2edf-0424-4360-89a8-6b14f59124ca.png)


## Selesai. 
## Terimaakasihhh

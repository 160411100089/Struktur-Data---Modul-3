# Struktur-Data---Modul-3
Class dan Linked List
-----------------------------------------------------------------------------------------------------------------------------------------
A. String dan List

Suatu variabel yang berbentuk lists ataupun string, memiliki dua buah elemen yang terkandung di dalam variabel tersebut, yaitu nilai atau yang disebut dengan state/property, serta method atau fungsi, yang dapat digunakan untuk mengolah nilai pada variabel tersebut.

Berikut adalah contoh tipe data string dan lists, yang memiliki nilai sekaligus method

      # String
      dataStr='Struktur Data' 
      print(dataStr)
      dataStr=dataStr.upper()
      print(dataStr)
      
      # Lists
      dataLs=[4,10,21]
      print(dataLs)
      data.append(45)
      print(dataLs)

#Constructor
merupakan method yang otomatis dijalankan ketika suatu obyek dibuat. Syntax untuk membuat suatu class, adalah sebagai berikut :

class namaClass

      def _init_() : #constructor
      def namaMethod () : #Method
      ...

Sedangkan untuk membuat suatu obyek dengan tipe data class tertentu (proses pembuatan instance) adalah :

      namaObyek=namaClass()

contoh kode Constructor Bilangan Kompleks:

      class BilanganKompleks:
          def __init__(self,a,b):
              self.real=a
              self.im=b

      data=BilanganKompleks(4,6)

      # untuk pengecekan tipe data dari variabel num
      type(data)

Constructor ini tidak perlu dipanggil secara eksplisit, akan tetapi otomatis akan dijalankan ketika instance (atau sebuah variabel dengan tipe data class) dibuat. Pada code diatas, perintah data=BilanganKompleks(4,6) merupakan contoh instansiasi dari class bilangan kompleks.


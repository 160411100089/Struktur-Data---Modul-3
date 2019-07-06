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

*contoh kode Constructor Bilangan Kompleks:

      class BilanganKompleks:
          def __init__(self,a,b):
              self.real=a
              self.im=b

      data=BilanganKompleks(4,6)

      # untuk pengecekan tipe data dari variabel num
      type(data)

Constructor ini tidak perlu dipanggil secara eksplisit, akan tetapi otomatis akan dijalankan ketika instance (atau sebuah variabel dengan tipe data class) dibuat. Pada code diatas, perintah data=BilanganKompleks(4,6) merupakan contoh instansiasi dari class bilangan kompleks.

#Method

merupakan fungsi-fungsi yang terdapat di dalam suatu class. Contoh method yang akan dibuat adalah method yang berfungsi untuk menampilkan property atau state yang terdapat di dalam suatu obyek. 

Syntax pembuatan method ialah

      def namaMethod():

Sedangkan untuk memanggil method suatu class adalah : 

      namaObyek.namaMethod()

*Berikut adalah contoh pembuatan method display() yang berfungsi untuk menampilkan property yang terdapat pada class Bilangan Kompleks.

      class BilanganKompleks:
          def __init__(self,a,b): # constructor
              self.real=a
              self.im=b
          def display(self): # method untuk menampilkan state
              print (self.real,'+',self.im,'i')

      data1=BilanganKompleks(4,6)
      data1.display()
      data2=BilanganKompleks(2,3)
      data2.display()
      
#Override Method

merupakan penambahan fungsi-fungsi pada syntax-syntax yang sudah ada. Seperti yang dijelaskan sebelumnya, untuk menampilkan property yang terdapat pada suatu obyek, tidak dapat dilakukan dengan menggunakan perintah print(). 

*Berikut contoh override method __str__ pada class BilanganKompleks

      class BilanganKompleks:
          def __init__(self,a,b):
              self.real=a
              self.im=b
          def display(self):
              print (self.real,"+",self.im,"i")
          def __str__(self):
              return str(self.real)+" + "+str(self.im)+" i "
        
      data1=BilanganKompleks(4,6)
      data2=BilanganKompleks(2,5)

      print('Override Method')
      print(data1)
      print(data2)
      print('Method dalam Class')
      data1.display()
      data2.display()

Contoh code berikut adalah pembuatan method baru di dalam class, yang berfungsi untuk menjumlahkan dua buah bilangan kompleks.

      class BilanganKompleks:
          def __init__(self,a,b):
              self.real=a
              self.im=b
          def display(self):
              print (self.real,'+',self.im,'i')
          def __str__(self):
              return str(self.real) + " + " + str(self.im) + " i "
          def addKompleks(self,obj):
              a=self.real+obj.real
              b=self.im+obj.im
              return BilanganKompleks(a,b)
        
      data1=BilanganKompleks(4,6)
      data2=BilanganKompleks(2,5)

      jumlah=data1.addKompleks(data2)
      data1.display()
      data2.display()
      print(jumlah)

      >>>
      Running: 4 + 6 i
               2 + 5 i
               6 + 11 i 
               
Jika ingin melakukan operasi penjumlahan dengan menggunakan operator '+', maka tidak dapat langsung dilakukan perintah sebagai berikut :

      data1=BilanganKompleks(4,6)
      data2=BilanganKompleks(2,5)
      jumlah=data1+


*Berikut adalah contoh override method __add__, agar operasi penjumlahan dua buah bilangan kompleks dapat dilakukan dengan menggunakan operator '+'.

      class BilanganKompleks:
          def __init__(self,a,b): 
              self.real=a
              self.im=b
          def display(self):
              print (self.real,'+',self.im,'i')
          def __str__(self):
              return str(self.real) + " + " + str(self.im) + " i "
          def addKompleks(self,obj):
              a=self.real+obj.real
              b=self.im+obj.im
              return BilanganKompleks(a,b)
          def __add__(self,obj):
              a=self.real+obj.real
              b=self.im+obj.im
              return BilanganKompleks(a,b)

      data1=BilanganKompleks(4,6)
      data1=BilanganKompleks(5,10)
      jumlah=data1+data2
      print(data1)
      print(data2)
      print(jumlah)

      >>>
      Running: 5 + 10 i 
               2 + 5 i 
               7 + 15 i 

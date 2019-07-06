# Struktur-Data---Modul-3
Class dan Linked List
----------------------------------------------------------------------------------------------------------------------------------------
String dan List

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

*Berikut overriding method untuk perkalian dua buah bilangan kompleks:

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
          def __mul__(self,data):
              temp1=(self.real*data.real)-(self.im*data.im)
              temp2=(self.real*data.im)+(data.real*self.im)
              return BilanganKompleks(temp1,temp2)
        
      a=BilanganKompleks(4,6)
      b=BilanganKompleks(5,10)
      c=a * b
      print(a)
      print(b)
      print(c)


Praktikum Struktur Data – 2019
#Modul 3 – Class dan Linked List
----------------------------------------------------------------------------------------------------------------------------------------
1. Buatlah class Matrix dengan beberapa method seperti berikut :
    a. Constructor : untuk inisialisasi matriks, dengan parameter berupa jumlah baris dan kolom suatu matrix,
                     dan elemen matriks merupakan inputan dari user (di dalam constructor)
    b. Override method __str__ : untuk menampilkan matriks gunakan formatting string jika diperlukan
    c. Override method __add__ : untuk menjumlahkan dua buah matriks
       Pada method ini, haruslah dilakukan pengecekan, jika ukuran dua buah matriks yang akan dijumlahkan tidak sama,
       maka akan mengeluarkan warning bahwa ukuran tidak sama
    d. Override method __mul__ : untuk mengalikan dua buah matriks
       Pada method ini, haruslah dilakukan pengecakan, jika jumlah kolom pada matriks pertama tidak sama dengan jumlah baris
       pada matriks kedua, maka akan mengeluarkan warning bahwa ukuran matriks tidak sesuai.
       
       
       
Berikut adalah contoh penggunaan class Matrix

*Penjumlahan

        Matriks1 = Matrix (2,2)
        print (Matriks1)
	
	>>>
	Running:
	Matriks[0,0]=10
	Matriks[0,1]=1
	Matriks[1,0]=20
	Matriks[1,1]=2
________________________________________________________________________________________________________________________________________
        Matriks1 = Matrix (2,2)
        print (Matriks1)
	
	>>>
	Running:
	Matriks[0,0]=10
	Matriks[0,1]=1
	Matriks[1,0]=20
	Matriks[1,1]=2
	| 10 1 |
	| 20 2 |
________________________________________________________________________________________________________________________________________
        Matriks3 = Matrix (2,3)
        print (Matriks2)

	>>>
	Running:
	Matriks[0,0]=4
	Matriks[0,1]=6
	Matriks[1,0]=7
	Matriks[1,1]=8
	| 4 6 |
	| 7 8 |
________________________________________________________________________________________________________________________________________
        Matriks2 = Matrix (2,2)
        print (Matriks2)
	
	>>>
	Running:
	Matriks[0,0]=1
	Matriks[0,1]=2
	Matriks[0,2]=10
	Matriks[1,0]=4
	Matriks[1,2]=7
	Matriks[1,2]=8
	| 1 2 10 |
	| 4 7  8 |
________________________________________________________________________________________________________________________________________
        Jumlah=Matriks1+Matriks2
        print(Jumlah)

	>>>
	Running:
	| 12  7 |
	| 27 10 |

        Jumlah=Matriks1+Matriks3
	
	>>>
	Running:
	ukuran Matriks tidak sama


*Perkalian

        Matriks1 = Matrix (2,2)
        print (Matriks1)

	>>>
	Running:
	Matriks[0,0]=1
	Matriks[0,1]=2
	Matriks[1,0]=3
	Matriks[1,0]=4
	| 1 2 |
	| 3 4 |
________________________________________________________________________________________________________________________________________
        Matriks2 = Matrix (1,2)
        print (Matriks2)

	>>>
	Running:
	| 1 2 |
________________________________________________________________________________________________________________________________________
        Hasil = Matrix&Matriks2

	>>>
	Running:
	Ukuran MAtriks tidak sesuai
________________________________________________________________________________________________________________________________________
        Matriks3 = Matrix (2,3)

	>>>
	Running:
	Matriks[0,0]=1
	Matriks[0,1]=2
	Matriks[1,2]=3
	Matriks[1,0]=4
	Matriks[1,1]=5
	Matriks[1,2]=6
________________________________________________________________________________________________________________________________________
       	print(Matriks1)
        print(Matriks3)
        Hasil = Matriks1*Matriks3
        print (Hasil)
	
	>>>
	Running:
	| 1 2 |
	| 3 4 |

	| 1 2 3 |
	| 4 5 6 |
	
	| 9  12 15 |
	| 19 26 33 |
          
	  
2. Buatlah class LinkedList, dengan beberapa method tambahan pada class LinkedList seperti
   berikut (untuk constructor LinkedList, dan class Node dapat dilihat pada materi perkuliahan):
      a. addRear : untuk menambahkan node di belakang linkedlist
      b. override method __str__ : untuk menampilkan data linked list
      c. override method __add__ : untuk menambahkan data dari dua buah linked list,
         dengan ketentuan, jumlah node pada linked list hasil penjumlahan sama dengan jumlah
         node terbanyak dari linked list yang akan dijumlahkan.
         
         
Berikut contoh penggunaan class LinkedList

        mylist1=LingkedList()
        mylist1.addReart(5)
        mylist1.addReart(84)
        mylist1.addReart(12)
        mylist1.addReart(77)
	  
	>>>
	Running:
	[5,84,12,77]
_______________________________________________________________________________________________________________________________________
        mylist2=LingkedList()
        mylist2.addReart(8)
        mylist2.addReart(9)
        print (mylist2)

	>>>
	Running:
	[ 8, 9 ]
________________________________________________________________________________________________________________________________________
        print('mylist1=, mylist1')
        print('mylist2=, mylist2')
        addList=mylist1+mylist2
        print('hasil penjumlahan=', addList)
	
	>>>
	Running:
	mylist1= [5,84,12,77]
	mylist2= [8,9]
	Hasil Penjumlahan= [13,93,12,77]
________________________________________________________________________________________________________________________________________
        mylist3=LingkedList()
        mylist3.addRear(10)
        mylist3.addRear(11)
        addList2=mylist2+mylist3
        print('mylist2=', mylist2)
        print('mylist3=', mylist3)
        print('Hasil Penjumlahan', addList2) 
	
	>>>
	Running:
	mylist2=[8,9]
	mylist3=[10,11]
	Hasil Penjumlahan= [18,20]
________________________________________________________________________________________________________________________________________
        mylist4=LingkedList()
        mylist4=addRear(1)
        mylist4=addRear(2)
        mylist4=addRear(3)
        mylist4=addRear(4)
        mylist4=addRear(5)
        mylist4=addRear(6)
        addList3=mylist3+mylist4
        print('mylist3=', mylist3)
        print('mylist4=', mylist4)
        print(Hasil Penjumlahan=', addList3')
	
	>>>
	Running:
	mylist3= [10,11]
	Hasil Penjumlahan= [11,13,3,4,5,6]
	
	
Jawaban Praktikum
----------------------------------------------------------------------------------------------------------------------------------------
#Nomer 1

	class matriks:
    		def __init__(self,baris,kolom):
        		self.b = []
        		self.baris = baris
        		self.kolom = kolom
        		for line in range (self.baris):
            			k = []
            			for cols in range(self.kolom):
                			k.append(0)
            			self.b.append(k)
        		inp = int(input("Masukkan jumlah element: "))
        		for i in range(inp):
            			bar = str(input("Baris ke ? "))
            			kol = str(input("Kolom ke ? "))
            			element = str(input("baris [{}][{}] : ".format(bar.kol)))
            			self.b[bar][kol] = element
            
    		def __str__(self):
        		data = ""
        		for i in range(len(self.b)):
            			data += "| "
            			for t in range(len(self.b[0])):
                			data += str(self.b[i][t])
            			data += " |\n"
        		return data
    
    		def __add__(self, tambah):
        		angka = "1234567890"
        		mat1 =[]
        		kol1 = []
        		hasil = []
        		data = ""
        		for t in range(len(tambah.b)):
            			if str(tambah.b[t]) in angka:
                			kol1.append(tambah.b[t])
            			else:
                			kol1 = []
                			mat1.append(kol1)
        		if len(self.b) == len(tambah.b):
            			if len(tambah.b[0]) == len(self.b[0]):
                			for u in range(len(self.b)):
                    				data += "| "
                    				kolo =[]
                    				for j in range(le(self.b[0])):
                        				has = tambah.b[u][j] + self.b[u][j]
                        				data += str(has)
                        				kolo.append(has)
                    				mat1.append(kolo)
                    				data += " |\n"
                			return "Hasil Penjumlahan\n" + data
            			else:
                			return "Penjumlahan tidak bisa dilakukan karena jumlah kolom tidak sama"
        		else:
            			return "Penjumlahan tidak bisa dilakukan karena jumlah baris tidak sama"
          
		def __mul__(self, kali):
        		angka = "1234567890"
        		data = ""
        		mat1 = []
        		kol1 = []
        		for t in range(len(kali.b)):
            			if str(kali.b[t]) in angka:
                			kol1.append(kali.b[t])
            			else:
                			kol1 = []
                			mat1.append(kol1)
        		if len(self.b[0]) == len(kali.b):
            			mat_bar = []
            			for i in range(len(self.b)):
                			data += "| "
                			hasil = 0
                			mat_kol = []
                			for y in range(len(kali.b[0])):
                    				for t in range(len(self.b[0])):
                        				a= self.b[i][t]
                        				b= kali.b[t][y]
                        				perkalian = a*b
                        				hasil = hasil + perkalian
                    				data += str(hasil)
                    				mat_kol.append(hasil)
                			mat_bar.append(hasil)
                			data += " |\n"
            			return "hasil dari perkalian = \n" + data
        		else:
            			return "perkalian tidak bisa dilakukan karena jumlah kolom matriks1 tidak sama"

	obj1 = matriks(2,2)
	print(obj1)
	obj2 = matriks(2,2)
	print(obj2)
	jumlah = obj1.__add__(obj2)
	print(jumlah)

	kali = obj1.__mul__(obj2)
	print(kali)

#Nomer 2

          class Node:
              def __init__(self,data):
                  self.data = data
                  self.next = None


          class LinkedList:
              def __init__(self):
                  self.head = None
              def push(self,new_data):
                  new_node= Node(new_data)
                  new_node.next = self.head
                  self.head = new_node
              def sum2Lists(self,list1,list2):
                  prev=None
                  temp=None
                  carry = 0
                  while (list1 is not None or list2 is not None):
                      if list1 is None:
                          fdata=0
                      else:
                          fdata=list1.data
                      if list2 is None:
                          sdata=0
                      else:
                          sdata=list2.data
                      Sum = carry + fdata + sdata
                      temp = Node(Sum)
                      if self.head is None:
                          self.head = temp
                      else:
                          prev.next = temp
                      prev = temp
                      if list1 is not None:
                          list1 = list1.next
                      if list2 is not None:
                          list2= list2.next
                  if carry > 0:
                      temp.next = Node(carry)
              def printList(self):
                  temp=self.head
                  x=[]
                  while(temp):
                      x.append(temp.data)
                      temp=temp.next
                  print(x)

          list1=LinkedList()
          list2=LinkedList()

          n=int(input('Banyak data untuk list 1 : '))
          for i in range (n):
              x = int(input('Data : '))
              list1.push(x)
              i=i+1
          m=int(input('Banyak data untuk list 2 : '))
          for j in range (m):
              y=int(input('Data : '))
              list2.push(y)
              j=j+1
          truck= LinkedList()
          truck.sum2Lists(list1.head, list2.head)
          print("First List is ")
          list1.printList()
          print("Second List is ")
          list2.printList()
          print("Result List is ")
          truck.printList()

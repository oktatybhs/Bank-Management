# Bank-Management-System

Ini merupakan Projek Bank Management System Database.

Abstrak: 
Tujuan utama dari proyek Mini DBMS Manajemen Bank adalah untuk mencatat transaksi nasabah di bank.
Kami bertujuan untuk mendemonstrasikan penggunaan operasi buat, baca, perbarui, dan hapus MySQL melalui proyek ini.
Pertama, registrasi pegawai dilakukan di cabang bank yang bersangkutan.
Pegawai cabang membuat rekening nasabah di bank, kemudian nasabah dapat mengkredit jumlah, jumlah debet dan cek saldo.
Pelanggan bahkan dapat menggunakan berbagai layanan seperti asuransi, pinjaman, pembayaran tagihan, dll.


Modules:

Project DBMS Manajemen Bank berisi 4 modul:

1. AccountHolder : Sesuai dengan namanya, catatan detail pelanggan.
2. Transaction: Transaksi yang akan dilakukan oleh pelanggan/nasabah (jumlah kredit, debit dll).
3. Service: Layanan tambahan yang mungkin diinginkan pelanggan (asuransi, pinjaman, dll.).
4. Branch / Employee: Manajer / Karyawan rincian bank yang bersangkutan.


Entity Relationship Diagram :

classDiagram
    service <|-- employee
    service <|-- accountholder
    transaction <|-- accountholder
    employee <|-- branch
    transaction <|-- employee

    class accountholder{
    +int id_accountholder
    +string account_number 
    +string account_type
    +string bcode
    +string name
    +string gender
    +localdate dob
    +string address
    +string nik_aadhar
    +double balance

    +void initialize()
    -void addCustomer()
    -void getFields()
    -void clearFields()
    -void scrAcntNum()
    -void mDeleteAccount()
    -void mUpdateAccount()

    }

    class employee{
    +string empName
    +string empBranch
  
    -void addEmployee()
    -void searchEmployee() 
    }

    class branch{
    +string branchCode
    +string branchName
    +string branchLoc

    -void addBranch()
    }
    
    class service{
    -string sName
    -double sAmount
    -string sDesc
    -string sAccNum
    -localdate sDate
    
    +void initialize()
    -void searchS()
    -void addService()
    -void clearFields()
    -void deleteService()
    }
    
    class transaction{
    -double tAmount
    -string ctType
    -localdate tDate
    -string AccNum

    +void initialize()
    -void AddTransaction()
    -void searchT()
    -void clearFields()
    -void deleteTransaction()
    }
    





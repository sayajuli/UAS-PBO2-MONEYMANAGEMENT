# Final Proyek Pemrograman Berorientasi Obyek 2
<ul>
  <li>Mata Kuliah: Pemrograman Berorientasi Obyek 2</li>
  <li>Dosen Pengampu: <a href="https://github.com/Muhammad-Ikhwan-Fathulloh">Muhammad Ikhwan Fathulloh</a></li>
</ul>

## Profil
<ul>
  <li>Studi Kasus: KeuanganKu</li>
  <ul>
    <li>Nama Anggota 1: <a href="https://github.com/sayajuli">Sahrul Julistiawan</a></li>
    <li>NIM: 23552011145</li>
  </ul>
  <ul>
    <li>Nama Anggota 2: <a href="https://github.com/tinton-despi-alkhifari">Tinton Despi Alkhifari</a></li>
    <li>NIM: 23552011162</li>
  </ul>
  <ul>
    <li>Nama Anggota 3: <a href="https://github.com/ichsanpratama1">Ichsan Pratama Putra</a></li>
    <li>NIM: 23552011205</li>
  </ul>
</ul>

## Judul Studi Kasus
<p>Manajemen Keuangan: KeuanganKu</p>

## Penjelasan Studi Kasus
<p>Sistem untuk mencatat keuangan pribadi mulai dari transaksi penmasukan dan pengeluaran, pencatatan aset yang dimiliki, dan juga pencatatan utang, sistem ini juga memiliki pengecekan rasio kesehatan keuangan dan juga dilengkapi dengan fitur cetak laporan transaksi dalam bentuk pdf.</p>

## Penjelasan 4 Pilar OOP dalam Studi Kasus

### 1. Inheritance
<p>Konsep inheritance diterapkan dalam beberapa aspek:</p>
<ul>
  <li><strong>Interface Implementation:</strong> Class UserDetailsServiceImpl mewarisi interface UserDetailsService dari Spring Security, mengimplementasikan method loadUserByUsername() untuk custom authentication.</li>
  <li><strong>Repository Inheritance:</strong> Semua repository interface seperti UserRepository, AssetRepository, TransactionRepository mewarisi dari JpaRepository<Entity, ID>, sehingga mendapat method CRUD dasar tanpa perlu implementasi manual.</li>
  <li><strong>JPA Entity Inheritance:</strong> Model entities menggunakan inheritance mapping dari JPA, dimana semua entity class mewarisi struktur dasar database entity dengan annotation @Entity, @Table, dan @Id.</li>
  <li><strong>DTO Inheritance:</strong> DTO classes seperti UserRegistrationDto, TransactionDto mewarisi struktur dan validation rules yang konsisten untuk transfer data antar layer.</li>
</ul>

### 2. Encapsulation
<p>Enkapsulasi diterapkan secara konsisten di seluruh aplikasi:</p>
<ul>
  <li><strong>Data Hiding:</strong> Semua field dalam model classes (User, Asset, Debt, Transaction) dideklarasikan private dan diakses melalui getter/setter yang di-generate otomatis oleh Lombok @Data.</li>
  <li><strong>Business Logic Encapsulation:</strong> Service classes seperti AssetService, DebtService, TransactionService mengenkapsulasi semua business logic dan rules, memisahkannya dari controller dan repository layer.</li>
  <li><strong>Security Encapsulation:</strong> Password di-hash menggunakan BCryptPasswordEncoder dan tidak pernah disimpan dalam bentuk plain text, melindungi data sensitif user.</li>
</ul>

### 3. Polymorphism
<p>Polimorfisme diimplementasikan melalui beberapa cara:</p>
<ul>
  <li><strong>Interface Polymorphism:</strong> Interface UserDetailsService dapat diimplementasikan dengan berbagai cara, namun client code tetap menggunakan interface yang sama tanpa perlu tahu implementasi spesifiknya.</li>
  <li><strong>Method Overloading:</strong> Service methods memiliki multiple signatures untuk handling different parameter combinations, seperti method filtering dalam TransactionService yang bisa menerima berbagai kombinasi parameter.</li>
  <li><strong>Repository Polymorphism:</strong> Semua repository menggunakan generic JpaRepository<T, ID> yang dapat menangani berbagai tipe entity dengan method signature yang sama namun behavior yang berbeda sesuai entity typenya.</li>
  <li><strong>Enum Polymorphism:</strong> Enum classes seperti TransactionType, AssetType, DebtStatus menyediakan polymorphic behavior dimana setiap enum value dapat memiliki behavior yang berbeda namun interface yang sama.</li>
</ul>

### 4. Abstract
<p>Abstraksi diterapkan untuk menyembunyikan kompleksitas implementasi:</p>
  <li><strong>Repository Abstraction:</strong> Interface repository seperti UserRepository, AssetRepository menyediakan abstraksi tingkat tinggi untuk database operations tanpa mengekspos detail SQL atau database-specific operations.</li>
  <li><strong>Service Layer Abstraction:</strong> Service classes menyediakan high-level business operations (seperti createTransaction(), addOrUpdateAsset()) yang mengabstraksi kompleksitas internal logic dan multiple database operations.</li>
  <li><strong>Security Abstraction:</strong> SecurityConfig mengabstraksi kompleksitas Spring Security configuration, menyediakan simple annotation-based security yang mudah dipahami dan dimaintain.</li>
  <li><strong>API Abstraction:</strong> Controller classes menyediakan clean REST endpoints yang mengabstraksi semua internal processing, memberikan interface yang simple untuk frontend consumption dengan HTTP methods standard.</li>
</ul>

## Demo Proyek
<ul>
  <li>Github: <a href="https://github.com/sayajuli/UAS-PBO2-MONEYMANAGEMENT">Github</a></li>
  <li>Youtube: <a href="https://youtu.be/jtTSuLnxt6o">Youtube</a></li>
</ul>

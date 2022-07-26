###### Nama    : Aditiya Wirayudha
###### Kelas   : XI RPL 1
###### No.Abs  : 06

# Modul 1

Soal No.1
1. Lakukan proses instalasi framework laravel kedalam folder dengan nama masing-masing.

![image](https://user-images.githubusercontent.com/109930265/180904081-0275fe5b-4b0e-4067-88b7-fa93806a05bd.png)

# Modul 2

Soal
1. Buatlah migration tabel kategori dengan menggunakan teknik yang telah di pelajari dalam 
modul ini

langkah pertama
```
php artisan make:migration create_kategori_table
```
langkah 2
isikan coding di dalam file 
```
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('kategori', function (Blueprint $table) {
            $table->id();
            $table->string('nama');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('kategori');
    }
};
```
langkah 3 buat file seeder kategori
```
php artisan make:seeder KategoriTableSeeder
```
dan buka KategoriTableSeeder dan isi dengan kode
```




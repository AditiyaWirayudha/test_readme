###### Nama    : Aditiya Wirayudha
###### Kelas   : XI RPL 1
###### No.Abs  : 06

# Modul 1

Soal 
1. Lakukan proses instalasi framework laravel kedalam folder dengan nama masing-masing.
2. Buatlah projek pertama laravel dengan nama projek “penjualan” dan tampilkan dalam browser

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
<?php

namespace Database\Seeders;

use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use DB;

class kategoriTableSeeder extends Seeder
{
    /**
     * Run the database seeds.
     *
     * @return void
     */
    public function run()
    {
        DB::table('kategori')->insert(array(
            [
                'nama' => 'Perlengkapan sekolah',    
            ],
            [
                'nama' => 'Komputer',    
            ],
            [
                'nama' => 'Sabun',    
            ],
            [
                'nama' => 'Accesories',    
            ],
            [
                'nama' => 'ATK',    
            ]

            ));
        
    }
}
```
lalu buka DatabaseSeeder.php dan isis dengfan kode ini
```
<?php

namespace Database\Seeders;

// use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
    /**
     * Seed the application's database.
     *
     * @return void
     */
    public function run()
    {
        $this->call(produkTableSeeder::class);
        $this->call(kategoriTableSeeder::class);
    }
}
```
Sekarang kita bisa menjalankan perintah atisan pada comand prompt untuk mengeksekusi seeder yang 
telah dibaut dengan perintah sebagai berikut

```
php artisan db:seed
```


langkah 3 Membuat model
```
php artisan make:model kategori
```
 dan tambahkan script deperti ini
 ```
 <?php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class Kategori extends Model
{
    use HasFactory;
    protected $table = 'kategori';
}
```



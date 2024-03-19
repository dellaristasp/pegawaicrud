# TUTORIAL PEGAWAI CRUD - MIGRATION :

# BUAT PROJECT BARU :
1. Buat project baru, bernama pegawaicrud :
   <img width="802" alt="Screen Shot 2024-03-19 at 22 50 05" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/3f99548d-f561-4028-ab6c-9d220b615ea4">
2. Ubah env menjadi  development :
   <img width="485" alt="Screen Shot 2024-03-19 at 22 58 36" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/c991cf11-ae34-462e-bd99-db06220bdcd7">

# MEMBUAT MIGRATION
1.  Buka terminal yang mengarah ke project anda :
    Jalankan perintah seperti dibawah ini :
   <img width="595" alt="Screen Shot 2024-03-19 at 23 00 15" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/e30a0988-38b1-4ab9-a843-bdf684e7b1d6">
2. Lalu akan terbuat sebuah file didalam folder app/Database/Migrations, nama file tersebut akan diakhiri dengan nama Pegawai, buka file tersebut, dan isi dengan code seperti berikut ini :
   <img width="740" alt="Screen Shot 2024-03-19 at 23 11 58" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/107f72a4-646b-4028-86bf-6b47fd3df26f">
3. Disini, saya menambahkan kode lain untuk penambahan foreign key :
   <img width="867" alt="Screen Shot 2024-03-19 at 23 19 14" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/c507128e-1f08-478d-8fda-2c73b6501513">

# MEMBUAT DATABASE
1. <img width="915" alt="Screen Shot 2024-03-19 at 23 21 58" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/c9965a26-4280-4443-8ccc-9ec48115cdcc">

# Setting Codeigniter 4 agar dapat terkoneksi dengan database
1. Buka `.env`
2. Ubah settingan `.env` menjadi seperti ini :
   <img width="497" alt="Screen Shot 2024-03-19 at 23 23 38" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/8ac70949-26a3-4677-8e8f-af6bd6d12851">
Keterangan :
- hostname adalah alamat server dari database
- database adalah nama database yang barusan kita buat, jadi kita isi nilainya dengan nama pegawai
- username adalah nama user dari database dalam contoh ini adalah root
- password adalah password dari database dalam contoh ini saya biarkan kosong, karena default dari password user root di xampp itu kosong
- DBDriver saya biasakan default yaitu MySQLi

# Menjalankan File Migration untuk membuat tabel di database.
1. Berikutnya kita akan menjalankan file migration untuk membuat tabel didatabase, silahkan masuk ke project codeigniter anda melalui terminal, lalu jalankan perintah :
<img width="466" alt="Screen Shot 2024-03-19 at 23 45 24" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/942e056a-ae62-43f6-b97c-7f6e3d298092">
maka sampai pada step ini kita sudah membuat tabel dengan nama pegawai, didatabase pegawai yang sebelumnya sudah kita buat.

2. Kondisi database saat ini :
<img width="1185" alt="Screen Shot 2024-03-19 at 23 52 54" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/e70087b2-582b-4087-bdec-ecb0c27800f4">

# Insert Dummy Data menggunakan Seeding
//untuk insert data pegawai.
1. Buka terminal :
   
3. Jalankan perintah :
   <img width="465" alt="Screen Shot 2024-03-19 at 23 56 57" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/43e2e725-aeab-487f-8208-6dc71027110a">

4. Lalu tekan enter, jika berhasil maka akan terbuat sebuah file dengan nama PegawaiSeeder didalam folder app\Database\Seeds\
   <img width="280" alt="Screen Shot 2024-03-19 at 23 57 50" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/93bce070-d97b-4094-ab1d-18421f0e40d5">

5. Isikan kode berikut ini :
   
```
   <?php
 
namespace App\Database\Seeds;
 
use CodeIgniter\Database\Seeder;
use CodeIgniter\I18n\Time;
 
class PegawaiSeeder extends Seeder
{
	public function run()
	{
		$data = [
			[
				'nama'          =>  'Anton',
				'jenis_kelamin' =>  'pria',
				'no_telp'       =>  '081234555678',
				'email'         =>  'anton@gmail.com',
				'alamat'	=>  'Jl. Mawar Putih No. 190, Waru Sidoarjo',
				'created_at' => Time::now()
			],
			[
				'nama'          =>  'Budi',
				'jenis_kelamin' =>  'pria',
				'no_telp'       =>  '08571234567',
				'email'         =>  'budi@gmail.com',
				'alamat'	=>  'Jl. Melati Putih No. 77, Gedangan Sidoarjo',
				'created_at' => Time::now()
			],
			[
				'nama'          =>  'Dita',
				'jenis_kelamin' =>  'wanita',
				'no_telp'       =>  '08122334455',
				'email'         =>  'dita@gmail.com',
				'alamat'	=>  'Jl. Rembulan No. 90, Krian Sidoarjo',
				'created_at' => Time::now()
			]
		];
		$this->db->table('pegawai')->insertBatch($data);
	}
}
```

  Keterangan :
  Dalam perintah diatas, kita menginsert 3 data pegawai dengan nama Anton, Budi, dan Dita.
  
  5. Berikutnya kita akan jalankan perintah diatas untuk insert data pegawai tersebut kedalam tabel pegawai, jalankan perintah :

<img width="448" alt="Screen Shot 2024-03-20 at 00 03 43" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/f96f47f2-aa3a-4b55-b158-703e01d5d242">
  
  6. Maka kita akan melihat di dalam database :

<img width="1097" alt="Screen Shot 2024-03-20 at 00 07 43" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/9d5edd7f-cafd-4eb3-8420-db1178c66ca1">

# Membuat Template untuk kebutuhan Tampilan
1. Buat folder dengan nama `layout` didalam folder `app/Views`, lalu berikutnya buat file dengan nama `template.php` didalam folder layout tersebut :
2. Isikan html & css atau bootstrap untuk tampilannya :
   Keterangan :
  - untuk tampilan ini saya ambil dari halaman example dari bootstrap, dengan link : https://getbootstrap.com/docs/5.0/examples/sticky-footer-navbar/
  - untuk bagian library css dan javascript yang digunakan dibagian template, kita langsung akses secara online ya, untuk mempersingkat proses pembuatan template, jadi saya sarankan untuk menggunakan koneksi internet untuk menjalankan hasilnya nanti.., untuk Library CSS berada pada line (15 dan 34), Line (71 dan 72) untuk Library Jquery

# Membuat Model untuk komunikasi dengan tabel di database
Kita persiapkan dulu model yang akan kita gunakan untuk berkomunikasi dengan tabel pegawai di database, untuk langkah awal buat file model dengan nama PegawaiModel.php, simpan file tersebut didalam folder app/Models
lalu isi file PegawaiModel.php dengan code sebagai berikut :

```
<?php
namespace App\Models;
use CodeIgniter\Model;
class PegawaiModel extends Model
{
    protected $table = "pegawai";
    protected $primaryKey = "id_pegawai";
    protected $returnType = "object";
    protected $useTimestamps = true;
    protected $allowedFields = ['id_pegawai', 'nama', 'jenis_kelamin', 'no_telp', 'email', 'alamat'];
}
```

//Keterangan :
// untuk classnya kita beri nama yang sama dengan nama filenya yaitu PegawaiModel
// beberapa settingan yang kita tulis adalah :
// $table dengan nilai pegawai karena kita akan komunikasi dengan tabel pegawai
// $primaryKey dengan nilai id_pegawai karena kolom id_pegawai merupakan primary key dari tabel pegawai
// $returnType dengan nilai object karena kita ingin untuk return type nanti berupa object
// $useTimestamps dengan nilai true karena kita akan mengisikan kolom created_at (saat insert data), dan kolom updated_at (saat update data)
// $allowedFields kita isikan nama kolom di tabel pegawai yang boleh diinsert data..


Setelah kita membuat model, berikutnya kita akan membuat menu untuk menampilkan data pegawai.

# Membuat Crud – Menampilkan Data Pegawai
Buatlah sebuah controller dengan nama file Pegawai.php didalam folder app/Controllers, dan isi dengan code seperti berikut ini :

```
<?php
 
namespace App\Controllers;
 
use App\Models\PegawaiModel;
 
class Pegawai extends BaseController
{
    protected $pegawai;
 
    function __construct()
    {
        $this->pegawai = new PegawaiModel();
    }
 
    public function index()
    {
        $data['pegawai'] = $this->pegawai->findAll();
        return view('pegawai/index', $data);
    }
}
```

Keterangan :
- kita buat class dengan nama yang sama dengan nama filenya yaitu Pegawai (Line 7)
- kita load Model dengan PegawaiModel dengan menuliskan perintah use App\Models\PegawaiModel; (Line 5), kita load model ini agar bisa berkomunikasi dengan tabel Pegawai
- Kita buat variabel didalam class dengan nama $pegawai (Line 9)
- kita buat method __construct untuk membuat sebuah object $pegawai dengan menggunakan class PegawaiModel (Line 11 – 14)
- Kita buat method index (Line 16) pada method index ini kita buat variabel $data yang merupakan array.
- Berikutnya kita tuliskan perintah $this->pegawai->findAll() yang digunakan untuk mengambil data pegawai di tabel pegawai, dan hasil data tersebut kita simpan ke dalam variabel $data yang merupakan array dengan key pegawai.. (Line 18).
- Berikutnya variabel $data yang telah berisi array akan kita passing ke bagian view dengan nama index didalam folder app/Views/pegawai (Line 19)

# Membuat View untuk menampilkan data pegawai
Setelah kita membuat controller untuk mempersiapkan data pegawai yang akan ditampilkan dibagian view, berikutnya kita perlu membuat view, silahkan buat folder terlebih dahulu dengan nama pegawai didalam folder app/Views, kita buat folder agar lebih mudah dalam management file view untuk kebutuhan fitur CRUD data pegawai ini, setelah itu kita buat file dengan nama index.php didalam folder app/Views/pegawai :
1. Buat folder `pegawai` dalam `app\views`
2. Buat file `index.php`

<img width="177" alt="Screen Shot 2024-03-20 at 00 43 18" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/07950c8d-9208-4d8c-bce2-0ef975b58fe7">

3. Berikutnya kita isi file `index.php` dengan code sebagai berikut :
```
   <?= $this->section('content'); ?>
<div class="container">
    <div class="card">
        <div class="card-header">
            <h3>Data Pegawai</h3>
        </div>
        <div class="card-body">
            <?php if (!empty(session()->getFlashdata('message'))) : ?>
                <div class="alert alert-success alert-dismissible fade show" role="alert">
                    <?php echo session()->getFlashdata('message'); ?>
                    <button type="button" class="close" data-dismiss="alert" aria-label="Close">
                        <span aria-hidden="true">&times;</span>
                    </button>
                </div>
            <?php endif; ?>
            <a href="<?= base_url('/pegawai/create'); ?>" class="btn btn-primary">Tambah</a>
            <hr />
            <table class="table table-bordered">
                <tr>
                    <th>No</th>
                    <th>Nama</th>
                    <th>Jenis Kelamin</th>
                    <th>No Telp</th>
                    <th>Email</th>
                    <th>Alamat</th>
                    <th>Action</th>
                </tr>
                <?php
                $no = 1;
                foreach ($pegawai as $row) {
                ?>
                    <tr>
                        <td><?= $no++; ?></td>
                        <td><?= $row->nama; ?></td>
                        <td><?= $row->jenis_kelamin; ?></td>
                        <td><?= $row->no_telp; ?></td>
                        <td><?= $row->email; ?></td>
                        <td><?= $row->alamat; ?></td>
                        <td>
                            <a title="Edit" href="<?= base_url("pegawai/edit/$row->id_pegawai"); ?>" class="btn btn-info">Edit</a>
                            <a title="Delete" href="<?= base_url("pegawai/delete/$row->id_pegawai") ?>" class="btn btn-danger" onclick="return confirm('Apakah Anda yakin ingin menghapus data ?')">Delete</a>
                        </td>
                    </tr>
                <?php
                }
                ?>
            </table>
        </div>
    </div>
</div>
<?= $this->endSection('content'); ?>
```

Lalu coba jalankan serve dengan php spark serve, dan dibagian localhost, tambahkan /pegawai. Maka hasilnya menjadi :
<img width="1674" alt="Screen Shot 2024-03-20 at 00 57 43" src="https://github.com/dellaristasp/pegawaicrud/assets/134635732/9dfdde53-63e1-4bac-861c-0f137d2d6075">

# Membuat Crud – Menambahkan Data Pegawai
Buat fitur untuk menambahkan data pegawai, langkah – langkahnya adalah sebagai berikut :
1. Buka file dengan nama Routes.php didalam folder app/Config
2. tambahkan code routing seperti berikut :
   
```   
$routes->get('/pegawai', 'Pegawai::index');
$routes->get('/pegawai/create', 'Pegawai::create');
```

Code diatas untuk kebutuhan routing dari fitur tampil data pegawai (Line 1), dan fitur untuk menampilkan form tambah data pegawai (Line 2)
3. Berikutnya kita buka controller pegawai, dan buat method dengan nama create , letakkan setelah method index , sehingga controller Pegawai menjadi seperti berikut ini :

```
<?php
 
namespace App\Controllers;
 
use App\Models\PegawaiModel;
 
class Pegawai extends BaseController
{
    protected $pegawai;
 
    function __construct()
    {
        $this->pegawai = new PegawaiModel();
    }
 
    public function index()
    {
        $data['pegawai'] = $this->pegawai->findAll();
        return view('pegawai/index', $data);
    }
 
    public function create()
    {
        return view('pegawai/create');
    }
}
```




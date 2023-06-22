# Car Rental by Ceryneian
# Afra Cendekia Putri Jallil
# 22/496428/SV/20957

## Catatan:
### Penjelasan umum :
Website Car Rental by Ceryneian ini merupakan website yang memiliki jasa penyewaan mobil bagi orang yang ingin atau membutuhkan mobil dalam jangka waktu tertentu sesuai dengan perjanjian. Penyewaan ini memudahkan pengguna untuk bisa langsung membooking mobil tanpa harus datang terlebih dahulu ketempat penyewaannya. Selain lebih nyaman digunakan oleh peminjam, website ini juga memudahkan bagi pegawai yang ingin mengupdate data. 

### Responsive :
Ketika tampilan website berukuran diatas 768px maka class-class ini akan mengoverride style css

```CSS
@media (min-width: 768px) {
  .navbar-custom {
    padding: 20px 0;
    border-bottom: 0;
    font-size: 13px;
    background: 0 0;
    -webkit-transition: background 0.5s ease-in-out, padding 0.5s ease-in-out;
    -moz-transition: background 0.5s ease-in-out, padding 0.5s ease-in-out;
    transition: background 0.5s ease-in-out, padding 0.5s ease-in-out;
  }
  .navbar-custom.top-nav-collapse {
    padding: 0;
    border-bottom: 1px solid rgba(255, 255, 255, 0.3);
    color: #333;
    background: #fff;
  }
  .navbar-custom.top-nav-collapse a {
    color: #333;
    display: inline-block;
  }
}

@media (min-width: 768px) {
  .intro {
    height: 100%;
    padding: 0;
  }
  .intro .intro-body .brand-heading {
    font-size: 98px;
    margin-top: 90px;
    margin-bottom: 20px;
    border-top: 4px solid rgb(0, 0, 0);
    border-bottom: 4px solid rgb(0, 0, 0);
    display: inline-block;
    padding: 10px 0;
  }
  .intro .intro-body .intro-text {
    font-size: 20px;
    font-weight: 300;
    letter-spacing: 3px;
  }
}
```
Website akan berbentuk seperti ini jika tampilannya fullscreen :

<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 08 22 21" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/a13904b2-e1d7-4109-a93d-3c33d2527fee">

Website akan beberbentuk seperti ini jika tampilannya diperkecil :

<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 08 22 26" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/7f01c1fe-f4aa-4df9-a700-06734a30a8a4">

### Kerapian
Tampilan page-page website dibuat konsisten sama agar tampilan terlihat rapi. 

<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 11 52 30" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/cd797ccb-96f5-49fc-b184-ebdf11fee08d">

<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 11 52 22" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/2b020749-bc23-4c0d-b8ef-bee32f007727">

<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 11 52 13" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/e2e5f757-bd3b-4638-b38e-a7aca91c490b">


### JavaScript
Kode berikut memiliki fungsi topFunction() digunakan untuk menggulir halaman web ke bagian atas atau ke posisi awal. Dengan menggulirkan nilai scrollTop ke 0 pada elemen body dan elemen root dokumen, fungsi topFunction() akan menggulirkan halaman web ke posisi atas atau ke bagian paling atas halaman tersebut.

```JS
function topFunction() {
        document.body.scrollTop = 0;
        document.documentElement.scrollTop = 0;
      }
```

Kode tersebut akan menampilkan tombol dengan ikon panah ke atas dan ketika tombol tersebut diklik, akan memanggil fungsi topFunction() untuk menggulirkan halaman ke atas.

```HTML
<button onclick="topFunction()" id="myBtn" title="Go to top">
      <span class="glyphicon glyphicon-chevron-up"></span>
    </button>
```

### Konten Dinamis

``` PHP
<section class="menu-content">
            <?php   
            $sql1 = "SELECT * FROM cars WHERE car_availability='yes'";
            $result1 = mysqli_query($conn,$sql1);

            if(mysqli_num_rows($result1) > 0) {
                while($row1 = mysqli_fetch_assoc($result1)){
                    $car_id = $row1["car_id"];
                    $car_name = $row1["car_name"];
                    $ac_price = $row1["ac_price"];
                    $ac_price_per_day = $row1["ac_price_per_day"];
                    $non_ac_price = $row1["non_ac_price"];
                    $non_ac_price_per_day = $row1["non_ac_price_per_day"];
                    $car_img = $row1["car_img"];
               
                    ?>
 
            <a href="booking.php?id=<?php echo($car_id) ?>">
            <div class="sub-menu">
            

            <img class="card-img-top" src="<?php echo $car_img; ?>" alt="Card image cap">
            <h5><b> <?php echo $car_name; ?> </b></h5>
            <h6> AC Fare: <?php echo ("Rp. " . $ac_price . "/km & Rp." . $ac_price_per_day . "/day"); ?></h6>
            <h6> Non-AC Fare: <?php echo ("Rp. " . $non_ac_price . "/km & Rp." . $non_ac_price_per_day . "/day"); ?></h6>

            
            </div> 
            </a>
            <?php }}
            else {
                ?>
<h1> No cars available : </h1>
                <?php
            }
            ?>                                   
        </section>    
```
        
Kode tersebut merupakan bagian dari sebuah halaman web yang menampilkan daftar mobil yang tersedia. Berikut adalah penjelasan mengenai kode diatas :

1. Kode PHP melakukan query ke database untuk mengambil mobil yang tersedia.
2. Jika terdapat mobil yang tersedia, maka setiap mobil akan ditampilkan dengan informasi seperti gambar, nama, dan harga.
3. Jika tidak ada mobil yang tersedia, maka ditampilkan pesan "No cars available".
   
Secara keseluruhan, kode tersebut digunakan untuk menampilkan konten dinamis berdasarkan data yang ada di database, sehingga pengguna dapat melihat daftar mobil yang tersedia dengan rincian harga dan detail lainnya.

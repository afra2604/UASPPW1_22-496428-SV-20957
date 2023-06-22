# Car Rental by Ceryneian
# Afra Cendekia Putri Jallil
# 22/496428/SV/20957

## Catatan:
## Penjelasan umum :
Website Car Rental by Ceryneian ini merupakan website yang memiliki jasa penyewaan mobil bagi orang yang ingin atau membutuhkan mobil dalam jangka waktu tertentu sesuai dengan perjanjian. Penyewaan ini memudahkan pengguna untuk bisa langsung membooking mobil tanpa harus datang terlebih dahulu ketempat penyewaannya. 
### Responsive :

Ketika diatas 768px maka class-class ini akan mengoverride style css

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
<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 08 22 21" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/a13904b2-e1d7-4109-a93d-3c33d2527fee">
<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 08 22 26" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/7f01c1fe-f4aa-4df9-a700-06734a30a8a4">

### Kerapian


<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 11 52 30" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/55a511ff-bb94-42ae-b69b-e956cbbaa63d">

<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 11 52 22" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/0088695f-d436-42f0-8d59-8666bd763431">

<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 11 52 13" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/f990afb6-ab78-4ccb-b60d-ab62d0b2a710">

<img width="1440" alt="Jepretan Layar 2023-06-22 pukul 11 52 03" src="https://github.com/afra2604/UASPPW1_22-496428-SV-20957/assets/109967726/38c96770-0eae-4a45-8b23-67dd17261b56">


### JavaScript

### Konten Dinamis

Untuk mengambil data dari database

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
  ```
Untuk menampilkan hasil sql ke website atau HTML
``` HTML
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

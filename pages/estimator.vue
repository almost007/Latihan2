<template>
  
  <div class="py-4">
    
    <div class="container">
      <div
        class="title border-bottom d-flex align-items-center justify-content-between py-2"
      >
        <h2>Smart Farming Project Estimator</h2>
        <div class="d-flex align-items-center">

          &nbsp;&nbsp;
        </div>
      </div>
      
<!--         <div :style="{ width:55% } class="progress-bar fixed-bottom" role="progressbar" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">{{ progres()}}</div>

        <div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 25%;" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">25%</div>

</div> -->
<br>

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">1. Informasi Lahan:</h4>
  <p>Biaya instalasi smart farming system sangat tergantung kepada luas lahan yang anda miliki. Jika anda sudah mengisi seluruh form dan menemukan bahwa total biaya yang dibutuhkan melebihi budget anda, maka mengurangi area instalasi adalah langkah yang bijak.</p>
</div>

      <div >
        <form class="row g-3">
  <div class="col-md-3">
    <label for="validationDefault01" class="form-label" data-toggle="Panjang area">Panjang Lahan (meter)</label>
    <input v-model="panjang" type="number" class="form-control" id="validationDefault01" value="Mark" required>
  </div>
  <div class="col-md-3">
    <label for="validationDefault02" class="form-label">Lebar Lahan (meter)</label>
    <input v-model="lebar" type="number" class="form-control" id="validationDefault02" value="Ot" required>
  </div>

   <div class="col-md-3">
    <label for="validationDefault05" class="form-label">Luas Lahan (meter persegi)</label>
    <input v-model="luas" type="text" class="form-control" id="validationDefault05" disabled>
  </div>
  <div class="col-md-3">
    <label for="validationDefault05" class="form-label">Luas Lahan (Tumbak/Bata/Ubin)</label>
    <input v-model="luash" type="text" class="form-control" id="validationDefault05" disabled>
  </div>

  <div class="col-md-6">
    <label for="validationDefault03" class="form-label">Lokasi Lahan</label>
    <input v-model="lokasi" type="text" class="form-control" id="validationDefault03" required>
  </div>
  <div class="col-md-3">
    <label for="validationDefault04" class="form-label">Kecamatan</label>
    <select v-model="wilayah" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Indramayu</option>
      <option>Ciwidey</option>
      <option>Cirebon</option>
      <option>Dago</option>
      <option>Lembang</option>
      <option>Soreang</option>
    </select>
  </div>
  <div class="col-md-3">
    <label for="validationDefault04" class="form-label">Jenis Tanah</label>
    <select v-model="tanah" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Tanah Liat</option>
      <option>Tanah Berpasir</option>
      <option>Tanah Humus</option>
      <option>Tidak yakin</option>
    </select>
  </div>
  <div class="col-md-3">
    <label for="validationDefault05" class="form-label">Ketinggian Lahan</label>
    <input v-if="wilayah == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Indramayu'" value="25-100 mdpl" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Dago'" value="690-730 mdpl" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Lembang'" value="1312- 2084 mdpl" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Cirebon'" value="0- 320 mdpl" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Ciwidey'" value="1200- 1400 mdpl" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Soreang'" value="590- 700 mdpl" type="text" class="form-control" id="validationDefault05" disabled>
  </div>
  <div class="col-md-3">
      <label for="validationDefault05" class="form-label">Jenis Ketinggian</label>
    <input v-if="wilayah == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Indramayu'" value="Dataran Rendah" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Dago'" value="Dataran Tinggi" v-model="ketinggianLahan" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Lembang'" value="Dataran Tinggi" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Cirebon'" value="Dataran Rendah" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Ciwidey'" value="Dataran Tinggi" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="wilayah == 'Soreang'" value="Dataran Tinggi" type="text" class="form-control" id="validationDefault05" disabled>
  </div>
  <div class="col-md-3">
    <label for="validationDefault04" class="form-label">Ada sumber air?</label>
    <select v-model="sumberAir" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Ya</option>
      <option>Tidak</option>
    </select>
  </div>
  <div v-if="sumberAir == 'Ya'" class="col-md-3">
    <label for="validationDefault05" class="form-label" >Jarak Ke sumber air (meter)</label>
    <input v-model="jarakAir" value="" type="number" class="form-control" id="validationDefault05" required>

  </div>
  <div>
      <br>
    </div>
    <template v-if="sumberAir != ''">
  <div class="alert alert-success" role="alert">
  <h4 class="alert-heading">2. Komoditas:</h4>
  <p>Pilih komoditas dan jenis Irigasi, sistem kami akan merekomendasikan sistem irigasi, benih, jarak tanam, jarak antar bedeng, total populasi dan lain-lain berdasarkan luas dan ketinggian lahan anda yang mengacu kepada <i> Good Agricultural Practices. </i> </p>
</div>
<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Jenis Komoditas</label>
    <select v-model="komoditas" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
       <option>Cabai</option>
      <option>Jagung</option>
    </select>
  </div>
  <div class="col-md-3" v-if="komoditas == ''">
    <label for="validationDefault04" class="form-label">Kategori</label>
    <select v-model="Kategori" class="form-select" id="validationDefault04" required disabled>
      <option selected disabled value="">Pilih</option>
    </select>
    </div>
  <div class="col-md-3" v-if="komoditas == 'Cabai'">
    <label for="validationDefault04" class="form-label">Kategori</label>
    <select v-model="Kategori" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Cabai Rawit</option>
      <option>Cabai Merah Besar</option>
    </select>
    </div>

     <div class="col-md-3" v-if="komoditas == 'Jagung'">
    <label for="validationDefault04" class="form-label">Kategori</label>
    <select v-model="Kategori" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Jagung Manis</option>
      <option>Jagung Pakan</option>
    </select>
    </div>
<!--
<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Jenis Irigasi</label>
    <input v-if="komoditas == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai Rawit'" value="Drip" type="text" class="form-control" id="validationDefault05" disabled>
</div>
-->
<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Jenis Irigasi</label>
    <select v-model="irigasi" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Drip</option>
      <option>Springkle</option>
      <option>Mist</option>
    </select>
  </div>
<div class="col-md-3">
    <label for="validationDefault04" class="form-label" data-bs-toggle="tooltip" data-bs-placement="top" title="Berdasarkan ketinggian, ketahanan penyakit dan kebutuhan mitra. ">Rekomendasi Varian</label>
    <input v-if="komoditas == '' || wilayah == '' || Kategori == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai' && Kategori == 'Cabai Rawit'" value="Baja F1"  type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai' && Kategori == 'Cabai Merah Besar'" value="Pilar F1"  type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Lembang' && Kategori == 'Jagung Manis' " value="Scada F1" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Indramayu' && Kategori == 'Jagung Manis' " value="Bonenza Now F1" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Lembang' && Kategori == 'Jagung Pakan' " value="NASA 29" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Indramayu' && Kategori == 'Jagung Pakan' " value="BISI Hibrida 18" type="text" class="form-control" id="validationDefault05" disabled>
</div>

<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Total Populasi</label>
    <input v-if="komoditas == '' || wilayah == '' || Kategori == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai' && Kategori == 'Cabai Rawit'" v-model="popCabai" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai' && Kategori == 'Cabai Merah Besar'" v-model="popCabai" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && Kategori == 'Jagung Manis' && wilayah == 'Lembang'" v-model="popJagungMT" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Indramayu' && Kategori == 'Jagung Manis'" v-model="popJagungMR" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Indramayu' && Kategori == 'Jagung Pakan'" v-model="popJagungPR" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Lembang' && Kategori == 'Jagung Pakan'" v-model="popJagungPT" type="text" class="form-control" id="validationDefault05" disabled>
</div>
<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Potensi Panen/musim (kg)</label>
    <input v-if="komoditas == '' || wilayah == '' || Kategori == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai' && Kategori == 'Cabai Rawit'" v-model="potCabai" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai' && Kategori == 'Cabai Merah Besar'" v-model="potCabai" type="text" class="form-control" id="validationDefault05" disabled>
<input v-if="komoditas == 'Jagung' && Kategori == 'Jagung Manis' && wilayah == 'Lembang'" v-model="potJagungMT" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Indramayu' && Kategori == 'Jagung Manis'" v-model="potJagungMR" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Indramayu' && Kategori == 'Jagung Pakan'" v-model="potJagungPR" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung' && wilayah == 'Lembang' && Kategori == 'Jagung Pakan'" v-model="potJagungPT" type="text" class="form-control" id="validationDefault05" disabled>
</div>


<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Jarak Antar Tanaman (cm)</label>
    <input v-if="komoditas == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai'" value="50 x 50" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung'" value="75 x 25" type="text" class="form-control" id="validationDefault05" disabled>
</div>
<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Jarak Antar Bedengan (cm)</label>
    <input v-if="komoditas == ''" value="" type="number" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai'" value="60" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung'" value="30" type="text" class="form-control" id="validationDefault05" disabled>
</div>
<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Lebar Bedengan (cm)</label>
    <input v-if="komoditas == ''" value="" type="number" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai'" value="120" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung'" value="150" type="text" class="form-control" id="validationDefault05" disabled>
</div>
<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Usia Panen</label>
    <input v-if="komoditas == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai'" value="70-75 hst" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung'" value="86-96 hst" type="text" class="form-control" id="validationDefault05" disabled>
</div>

<div v-if="komoditas == 'Cabai' && wilayah == 'Lembang'" class="alert alert-warning alert-dismissible fade show" role="alert">
  <strong>Himbauan</strong> <i> Komoditas ini kurang cocok ditanam didaerah dataran tinggi dan berpotensi penurunan produktifias. </i>
  <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
</div>
<div v-if="komoditas == 'Cabai' && wilayah == 'Lembang' && irigasi == 'Springkle'" class="alert alert-warning alert-dismissible fade show" role="alert">
  <strong>Himbauan</strong> <i> Ketinggian dan kecepatan angin didaerah ini tergolong tinggi tidak cocok menggunakan irigasi springkle. </i>
  <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
</div>

<div v-if="komoditas == 'Cabai' && wilayah == 'Lembang' && irigasi == 'Mist'" class="alert alert-warning alert-dismissible fade show" role="alert">
  <strong>Himbauan</strong> <i> Ketinggian dan kecepatan angin didaerah ini tergolong tinggi sehingga tidak cocok menggunakan irigasi Mist/ kabut. </i>
  <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
</div>

  <div class="alert alert-success" role="alert">
  <h4 class="alert-heading">3. Potensi Usaha:</h4>
  <p>Analisa potensi usaha komoditas yang anda pilih dengan kondisi pasar saat ini dan permintaan dari mitra kami.</p>
</div>

<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Mitra Penyerapan</label>
    <input v-if="komoditas == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Cabai'" value="Tidak ada" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="komoditas == 'Jagung'" value="Ada" type="text" class="form-control" id="validationDefault05" disabled>
</div>

<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Total Kebutuhan Mitra (Ton/Minggu)</label>
    <input v-if="komoditas == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="Kategori == 'Cabai Rawit'" value="0" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="Kategori == 'Cabai Merah Besar'" value="0" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="Kategori == 'Jagung Manis'" value="1000" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="Kategori == 'Jagung Pakan'" value="5000" type="text" class="form-control" id="validationDefault05" disabled>
</div>

<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Harga Jual (Kg)</label>
    <input v-if="komoditas == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="Kategori == 'Cabai Rawit'" value="35000" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="Kategori == 'Cabai Merah Besar'" value="22000" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="Kategori == 'Jagung Manis'" value="4000" type="text" class="form-control" id="validationDefault05" disabled>
    <input v-if="Kategori == 'Jagung Pakan'" value="3000" type="text" class="form-control" id="validationDefault05" disabled>
</div>

<div class="col-md-3">
    <label for="validationDefault04" class="form-label">Potensi Omset (Kg)</label>
    <input v-if="komoditas == ''" value="" type="text" class="form-control" id="validationDefault05" disabled>
    <div v-if="Kategori == 'Cabai Rawit'">
      <input v-model="omset" type="number" class="form-control" id="validationDefault05" disabled>
    </div>
      <div v-if="Kategori == 'Cabai Merah Besar'">
      <input v-model="omset" type="number" class="form-control" id="validationDefault05" disabled>
      </div><div v-if="Kategori == 'Jagung Manis'">
      <input v-model="omset" type="number" class="form-control" id="validationDefault05" disabled>
      </div><div v-if="Kategori == 'Jagung Pakan'">
      <input v-model="omset" type="number" class="form-control" id="validationDefault05" disabled>
      </div>
</div>


<div>
<br>
</div>
    </template>
<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">4. Instalasi Smart Farming:</h4>
  <p> Sistem pertanian smart farming kami mengacu kepada pertanian presisi untuk memberikan tanaman jumlah air dan pupuk dengan dosis yang tepat melalui mekanisasi pertanian dan penerapan sensor yang mengacu kepada jenis tanah, cuaca, usia tanaman dan jenis komoditas. Penerapan smart farming dapat meningkatkan produktifitas, mengurangi biaya SDM pemupukan dan pengairan, menghemat air hingga 80% dan konsumsi pupuk hingga 60%.</p>
</div>

 <div class="col-md-3">
    <label for="validationDefault04" class="form-label" data-bs-toggle="tooltip" data-bs-placement="top" title="Penerapan berbagai sensor untuk penyiraman dan pemupukan otomatis yang dapat dimonitor melalui smartphone anda.">Instalasi pertanian presisi?</label>
    <select v-model="instalPresisi" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Ya</option>
      <option>Tidak</option>
    </select>
  </div>

  <div class="col-md-3">
    <label for="validationDefault04" class="form-label" data-bs-toggle="tooltip" data-bs-placement="top" title="Listrik berfungsi sebagai sumber daya sensor dan untuk menyalakan pompa, jika tidak ada akan direkomendasikan menggunakan solar panel dengan biaya tambahan.">Apakah dilahan ada sumber listrik?</label>
    <select v-model="instalListrik" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Ya</option>
      <option>Tidak</option>
    </select>
  </div>

  <div class="col-md-3">
    <label for="validationDefault04" class="form-label" data-bs-toggle="tooltip" data-bs-placement="top" title="Jika tidak maka akan diinstal modul LORA WAN dengan biaya tambahan.">Apakah dilahan terjangkau wifi?</label>
    <select v-model="instalWifi" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Ya</option>
      <option>Tidak</option>
    </select>
  </div>

<div class="col-md-3">
    <label for="validationDefault04" class="form-label" data-bs-toggle="tooltip" data-bs-placement="top" title="Jika ya maka akan diinstal modul cctv dengan biaya tambahan.">Instal CCTV?</label>
    <select v-model="instalCCTV" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Ya</option>
      <option>Tidak</option>
    </select>
  </div>

<div class="col-md-3">
    <label for="validationDefault04" class="form-label" data-bs-toggle="tooltip" data-bs-placement="top" title="Jika anda memilih instal sendiri maka kami hanya akan mengirimkan peralatan dan petunjuk instalasi, kami dapat membantu dalam proses instalasi dengan biaya tambahan.">Preferensi instalasi?</label>
    <select v-model="instalsendiri" class="form-select" id="validationDefault04" required>
      <option selected disabled value="">Pilih</option>
      <option>Saya akan instal sendiri</option>
      <option>Kirimkan saya tim instalasi</option>
      <option>Tidak tahu</option>
    </select>
  </div>


<table class="table">
  <thead>
    <tr>
      <th scope="col">Nama</th>
      <th scope="col">Spesifikasi</th>
      <th scope="col">Kuantitas</th>
      <th scope="col">Satuan</th>
      <th scope="col">Harga</th>
      <th scope="col">Total</th>
    </tr>
  </thead>
  <tbody>
    <tr class="table-active">
      <th scope="row">Drip irrigation tape </th>
      <td>16mm with inner flat emitters flow rate 2.0-2.5(L/H), Pressure 0.1-0.25mpa, Spacing 25 cm</td>
      <td>{{driptape}}</td>
      <td>meter</td>
      <td>2000</td>
      <td>{{totdriptape}}</td>
    </tr>
    <tr>
       <th scope="row">Selang LDPE </th>
      <td>Diameter 16 mm Tekanan 0.25 Mpa, Ketebalan 1 mm. Anti-UV, Ketahanan suhu-30C ~ 40C</td>
      <td>{{ldpe}}</td>
      <td>meter</td>
      <td>5000</td>
      <td>{{totldpe}}</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2" class="table-active">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>

  <div class="col-12">
    <button class="btn btn-primary" type="submit" >Submit form</button>
  </div>
</form>
      </div>
</div>
  </div>
</template>
<script>
import CardItem from "~/components/Card/CardItem.vue";

export default {

  components: {
    CardItem,
  },

  data() {
    return {
      panjang: 0,
      lebar: 0,
      lokasi: '',
      ketinggian: '',
      wilayah: '',
      sumberAir: '',
      tanah: '',
      komoditas: '',
      irigasi: '',
      Kategori: '',
      instalCCTV: '',
      instalPresisi: '',
      instalListrik: '',
      instalWifi: '',
      jarakAir: '',



    };
  },

  methods: {
    progres(){
    if (this.sumberAir != "" ) {
      return 25;
}
else {
return 0

}
    },


  },

  computed: {
    omset(){
      if (this.Kategori == 'Cabai Rawit') {
return (((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*8) * 35000
      }
      if (this.Kategori == 'Cabai Merah Besar') {
return (((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*8) * 22000
      }
      if (this.Kategori == 'Jagung Manis') {
return ((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*11 *4000
      }
      if (this.Kategori == 'Jagung Pakan') {
return ((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*10 *3000
      }
    },
    luas (){
    return parseInt(this.panjang) * parseInt(this.lebar)
    },
    driptape (){
    return  Math.round (parseInt(this.panjang) * ((parseInt(this.lebar)/1.8)*2))
    },
    totdriptape() {
       return  Math.round (parseInt(this.panjang) * ((parseInt(this.lebar)/1.8)*2))*2000
    },
    ldpe() {
       return  Math.round (parseInt(this.lebar)) +  Math.round (parseInt(this.jarakAir))
    },
     totldpe() {
       return  Math.round (parseInt(this.lebar)*5000)
    },
    luash (){
    return Math.round(parseInt(this.panjang ) * parseInt(this.lebar)/14)
    },
      popCabai (){
      return parseInt((this.panjang)/1.2) * parseInt((this.lebar)/0.5)
      },
      potCabai (){
      return ((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*8
      },
      popJagungMT (){
      return (parseInt((this.panjang)/1.5) * parseInt((this.lebar)/0.25)) * 2
      },
      potJagungMT (){
      return ((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*11
 },
 popJagungMR (){
      return (parseInt((this.panjang)/1.6) * parseInt((this.lebar)/0.30)) * 2
      },
      potJagungMR (){
      return ((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*14
 },
 popJagungPT (){
      return (parseInt((this.panjang)/1.5) * parseInt((this.lebar)/0.30)) * 2
      },
      potJagungPT (){
      return ((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*10
 },
 popJagungPR (){
      return (parseInt((this.panjang)/1.6) * parseInt((this.lebar)/0.20)) * 2
      },
      potJagungPR (){
      return ((parseInt(this.panjang) * parseInt (this.lebar))/ 10.000)*12
 },
  }
};
</script>
<style>
.red {
  color: blue;
}
</style>

# Wibsite-kelompok-2
web
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sensor Kata Positif</title>

<style>
body{
  font-family: Arial;
  background: linear-gradient(135deg, red, yellow, white);
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  margin:0;
}

.box{
  width:350px;
  background:rgba(255,255,255,0.2);
  padding:20px;
  border-radius:20px;
  text-align:center;
  box-shadow:0 0 20px white;
}

h1{
  color:white;
  text-shadow:0 0 10px red;
}

textarea{
  width:100%;
  height:120px;
  border:none;
  border-radius:10px;
  padding:10px;
  font-size:16px;
}

.hasil{
  margin-top:15px;
  background:white;
  padding:15px;
  border-radius:10px;
  min-height:60px;
}

.glow{
  color:red;
  font-weight:bold;
  text-shadow:0 0 10px yellow;
}

.stiker{
  font-size:35px;
}
</style>
</head>

<body>

<div class="box">
  <div class="stiker">🔥🌟💪🚀</div>

  <h1>Sensor Kata</h1>

  <textarea id="text"
  placeholder="Contoh: Saya takut gagal..."></textarea>

  <div class="hasil" id="hasil">
    Hasil positif muncul di sini...
  </div>
</div>

<!-- SUARA -->
<audio id="suara">
  <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_c8c8a73467.mp3?filename=success-fanfare-trumpets-6185.mp3">
</audio>

<script>
const kata = {
  "gagal":"<span class='glow'>sukses</span>",
  "takut":"<span class='glow'>berani</span>",
  "bodoh":"<span class='glow'>pintar</span>"
};

let input = document.getElementById("text");

input.addEventListener("input", function(){

  let teks = input.value;

  for(let k in kata){
    let regex = new RegExp(k,"gi");
    teks = teks.replace(regex, kata[k]);
  }

  document.getElementById("hasil").innerHTML = teks;

  // suara saat mengetik kata negatif
  document.getElementById("suara").play();
});
</script>

</body>
</html>

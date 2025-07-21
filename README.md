# Gaucher-formm
Gaucher düşün klinik form
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Gaucher Düşün! – Hematoloji Formu</title>
  <style>
    body { font-family: Arial; margin: 20px; background: #f5f5f5; }
    h2 { color: #2c3e50; }
    table { border-collapse: collapse; width: 100%; margin-bottom: 20px; }
    th, td { border: 1px solid #ccc; padding: 10px; text-align: left; }
    th { background-color: #e0e0e0; }
    .result { font-weight: bold; margin-top: 20px; }
    .risk { color: red; }
    .normal { color: green; }
    button { background: #3498db; color: #fff; padding: 10px 20px; border: none; cursor: pointer; }
  </style>
</head>
<body>

<h2>🧪 Gaucher Düşün! – Hematoloji Klinik Değerlendirme Formu</h2>
<p>Tanıya götürmeyen bulguları işaretleyin. 3 veya daha fazlası mevcutsa Gaucher hastalığı için test önerilir.</p>

<form id="formHematoloji">
  <table>
    <tr><th>Bulgu</th><th>İşaretle</th></tr>
    <tr><td>Trombositopeni (açıklanamayan)</td><td><input type="checkbox" name="bulgu"></td></tr>
    <tr><td>Pansitopeni</td><td><input type="checkbox" name="bulgu"></td></tr>
    <tr><td>Splenomegali</td><td><input type="checkbox" name="bulgu"></td></tr>
    <tr><td>Kemik iliği biyopsisi (tanısız)</td><td><input type="checkbox" name="bulgu"></td></tr>
    <tr><td>Yüksek ferritin</td><td><input type="checkbox" name="bulgu"></td></tr>
    <tr><td>Ailede hematolojik hastalık öyküsü</td><td><input type="checkbox" name="bulgu"></td></tr>
  </table>
  <button type="button" onclick="degerlendir()">Değerlendir</button>
</form>

<div id="sonuc" class="result"></div>

<script>
function degerlendir() {
  const secilen = document.querySelectorAll('input[name="bulgu"]:checked').length;
  const sonuc = document.getElementById('sonuc');

  if (secilen >= 3) {
    sonuc.innerHTML = `✅ <span class="risk">${secilen} bulgu işaretlendi.</span><br>
    Gaucher hastalığını düşünün!<br>
    ➤ Lyso-Gb1<br>➤ GBA enzim aktivitesi<br>➤ Genetik test önerilir.`;
  } else {
    sonuc.innerHTML = `🔍 <span class="normal">${secilen} bulgu işaretlendi.</span><br>
    Gaucher ön tanısı zayıf, takip önerilir.`;
  }
}
</script>

</body>
</html>

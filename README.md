<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rumus Aritmatika</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 30px;
        }
        input, button {
            padding: 10px;
            margin: 10px 0;
        }
        select {
            padding: 10px;
            margin: 10px 0;
        }
    </style>
</head>
<body>

    <h1>Hitung Aritmatika</h1>

    <label for="angka1">Angka 1:</label>
    <input type="number" id="angka1" placeholder="Masukkan angka pertama" required>

    <label for="angka2">Angka 2:</label>
    <input type="number" id="angka2" placeholder="Masukkan angka kedua" required>

    <label for="operasi">Pilih Operasi:</label>
    <select id="operasi">
        <option value="tambah">Penjumlahan (+)</option>
        <option value="kurang">Pengurangan (-)</option>
        <option value="kali">Perkalian (×)</option>
        <option value="bagi">Pembagian (÷)</option>
    </select>

    <button onclick="hitung()">Hitung</button>

    <h2>Hasil: <span id="hasil">-</span></h2>

    <script>
        function hitung() {
            var angka1 = parseFloat(document.getElementById('angka1').value);
            var angka2 = parseFloat(document.getElementById('angka2').value);
            var operasi = document.getElementById('operasi').value;
            var hasil;

            if (isNaN(angka1) || isNaN(angka2)) {
                document.getElementById('hasil').textContent = "Harap masukkan angka yang valid.";
                return;
            }

            switch (operasi) {
                case 'tambah':
                    hasil = angka1 + angka2;
                    break;
                case 'kurang':
                    hasil = angka1 - angka2;
                    break;
                case 'kali':
                    hasil = angka1 * angka2;
                    break;
                case 'bagi':
                    if (angka2 === 0) {
                        hasil = "Pembagian dengan nol tidak terdefinisi.";
                    } else {
                        hasil = angka1 / angka2;
                    }
                    break;
            }

            document.getElementById('hasil').textContent = hasil;
        }
    </script>

</body>
</html>

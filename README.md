# PHP Dasar
<img width="1920" height="1080" alt="Screenshot (136)" src="https://github.com/user-attachments/assets/dc063341-8f6b-41fd-b437-a926c807851c" />

# Menambahkan variable pada program
<img width="1920" height="1080" alt="Screenshot (137)" src="https://github.com/user-attachments/assets/cea19ee3-73bc-4a65-a703-15aed86e108a" />

# Membuat form input
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4870d378-5f14-4e25-82ea-a7b74724a5c7" />

# Pertanyaan dan Tugas
Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan
nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung
umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang
berbeda-beda sesuai pilihan pekerjaan.

# Code
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Tugas PHP Dasar</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f6f9;
            margin: 40px;
        }
        h1 {
            text-align: center;
            color: #2c3e50;
        }
        form {
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            width: 350px;
            margin: 0 auto;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        label {
            font-weight: bold;
        }
        input[type="text"], input[type="date"], select {
            width: 100%;
            padding: 8px;
            margin: 8px 0 15px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        input[type="submit"] {
            background-color: #2ecc71;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
        }
        input[type="submit"]:hover {
            background-color: #27ae60;
        }
        .hasil {
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            width: 350px;
            margin: 20px auto;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        hr {
            border: 0;
            border-top: 1px solid #ccc;
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <h1>Form Input Data Diri</h1>

    <form method="post">
        <label>Nama:</label>
        <input type="text" name="nama" required>

        <label>Tanggal Lahir:</label>
        <input type="date" name="tanggal_lahir" required>

        <label>Pekerjaan:</label>
        <select name="pekerjaan" required>
            <option value="">-- Pilih Pekerjaan --</option>
            <option value="Programmer">Programmer</option>
            <option value="Designer">Designer</option>
            <option value="Guru">Guru</option>
            <option value="Dokter">Dokter</option>
            <option value="Mahasiswa">Mahasiswa</option>
        </select>

        <input type="submit" value="Kirim">
    </form>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $nama = $_POST['nama'];
        $tanggal_lahir = $_POST['tanggal_lahir'];
        $pekerjaan = $_POST['pekerjaan'];

        // Hitung umur
        $tgl_lahir = new DateTime($tanggal_lahir);
        $hari_ini = new DateTime();
        $umur = $hari_ini->diff($tgl_lahir)->y;

        // Tentukan gaji berdasarkan pekerjaan
        switch ($pekerjaan) {
            case "Programmer":
                $gaji = 8000000;
                break;
            case "Designer":
                $gaji = 7000000;
                break;
            case "Guru":
                $gaji = 5000000;
                break;
            case "Dokter":
                $gaji = 12000000;
                break;
            case "Mahasiswa":
                $gaji = 0;
                break;
            default:
                $gaji = 0;
                break;
        }

        echo "<div class='hasil'>";
        echo "<h2>Hasil Output:</h2>";
        echo "<hr>";
        echo "Nama: <strong>$nama</strong><br>";
        echo "Tanggal Lahir: <strong>$tanggal_lahir</strong><br>";
        echo "Umur: <strong>$umur tahun</strong><br>";
        echo "Pekerjaan: <strong>$pekerjaan</strong><br>";
        echo "Gaji: <strong>Rp " . number_format($gaji, 0, ',', '.') . "</strong>";
        echo "</div>";
    }
    ?>
</body>
</html>
```

# Output
# Jika memilih pekerjaan sebagai Programmer
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9446ebac-6baa-4a17-86fa-5fd3d49a9f28" />

# Jika memilih pekerjaan sebagai Designer
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/815c57a9-3e99-463f-8369-003ea4cacd79" />

# Jika memilih pekerjaan sebagai Guru
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/93cdd6a0-fa2a-4fcc-b4d0-3cef7c9a3fd5" />

# Jika memilih pekerjaan sebagai Dokter
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8e96dbc2-996d-4695-8335-1a92403d277c" />

# Kesimpulan

Dalam praktikum ini, saya belajar:
- Konsep dasar PHP sebagai server-side scripting language.

- Cara membuat file PHP dan menjalankannya di localhost.

- Penggunaan variabel, operator, struktur kondisi, dan perulangan.

- Cara menangkap input dari form dan menampilkannya kembali.

- Menghitung umur otomatis berdasarkan tanggal lahir.

- Menggunakan switch untuk menentukan gaji berdasarkan pekerjaan.

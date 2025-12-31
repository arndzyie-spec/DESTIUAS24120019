# DESTIUAS24120019
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Data Nilai Mahasiswa</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #e6e6e6;
        }
        h1 {
            text-align: center;
        }
        .container {
            display: flex;
            gap: 20px;
            padding: 20px;
        }
        .box {
            background: #dfe8cf;
            padding: 20px;
            width: 50%;
            border: 1px solid #999;
        }
        .box h3 {
            text-align: center;
        }
        label {
            display: inline-block;
            width: 130px;
            margin-bottom: 10px;
        }
        input {
            padding: 5px;
            width: 200px;
        }
        .btn {
            margin-top: 10px;
        }
        button {
            padding: 5px 15px;
            margin-right: 5px;
        }
        .output p {
            margin: 6px 0;
        }
        .note {
            font-size: 12px;
            margin-top: 15px;
        }
    </style>
</head>
<body>

<h1>UAS</h1>

<div class="container">

    <!-- INPUT -->
    <div class="box">
        <h3>DATA NILAI MAHASISWA</h3>
        <hr>

        <label>NIM</label>
        <input type="text" id="nim"><br>

        <label>Nama Mahasiswa</label>
        <input type="text" id="nama"><br>

        <label>Nilai UTS</label>
        <input type="number" id="uts"><br>

        <label>Nilai UAS</label>
        <input type="number" id="uas"><br>

        <label>Nilai Tugas</label>
        <input type="number" id="tugas"><br>

        <div class="btn">
            <button onclick="proses()">Proses</button>
            <button onclick="resetForm()">Batal</button>
        </div>

        <div class="note">
            UTS 30% | UAS 40% | TUGAS 30% <br>
            85–100 = A | 70–84 = B | 60–69 = C | 40–59 = D | &lt;40 = E
        </div>
    </div>

    <!-- OUTPUT -->
    <div class="box output">
        <h3>DATA NILAI MAHASISWA</h3>
        <hr>

        <p><b>NIM :</b> <span id="o_nim"></span></p>
        <p><b>Nama Mahasiswa :</b> <span id="o_nama"></span></p>
        <p><b>Nilai UTS :</b> <span id="o_uts"></span></p>
        <p><b>Nilai UAS :</b> <span id="o_uas"></span></p>
        <p><b>Nilai Tugas :</b> <span id="o_tugas"></span></p>
        <p><b>Index :</b> <span id="o_index"></span></p>

        <hr>
    </div>

</div>

<script>
function proses() {
    let nim = document.getElementById("nim").value;
    let nama = document.getElementById("nama").value;
    let uts = parseFloat(document.getElementById("uts").value);
    let uas = parseFloat(document.getElementById("uas").value);
    let tugas = parseFloat(document.getElementById("tugas").value);

    let nilaiAkhir = (uts * 0.3) + (uas * 0.4) + (tugas * 0.3);
    let index = "";

    if (nilaiAkhir >= 85) index = "A";
    else if (nilaiAkhir >= 70) index = "B";
    else if (nilaiAkhir >= 60) index = "C";
    else if (nilaiAkhir >= 40) index = "D";
    else index = "E";

    document.getElementById("o_nim").innerText = nim;
    document.getElementById("o_nama").innerText = nama;
    document.getElementById("o_uts").innerText = uts;
    document.getElementById("o_uas").innerText = uas;
    document.getElementById("o_tugas").innerText = tugas;
    document.getElementById("o_index").innerText = index;
}

function resetForm() {
    document.querySelectorAll("input").forEach(i => i.value = "");
    document.querySelectorAll("span").forEach(s => s.innerText = "");
}
</script>

</body>
</html>

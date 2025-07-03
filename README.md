<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Website Kelas 9B</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #fff6ec;
      margin: 0;
      padding: 0;
    }
    header {
      background-color: #a0522d;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      background-color: #f5d5a1;
      padding: 10px;
      text-align: center;
    }
    .menu-btn {
      margin: 6px;
      padding: 10px 18px;
      background-color: #f0c38e;
      border: none;
      border-radius: 12px;
      font-weight: bold;
      cursor: pointer;
    }
    .menu-btn:hover {
      background-color: #dfa96b;
    }
    #content {
      padding: 25px;
      background-color: #fffdf8;
      min-height: 300px;
    }
    footer {
      background-color: #a0522d;
      color: white;
      text-align: center;
      padding: 15px;
    }
    footer a {
      color: #ffffff;
      font-weight: bold;
      text-decoration: none;
      margin: 0 10px;
    }
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 10px;
    }
    th, td {
      border: 1px solid #ccc;
      padding: 8px;
      text-align: center;
    }
    /* Style untuk Fitur Komentar */
    #comment-form {
      margin-top: 20px;
    }
    #comment-form input, #comment-form textarea {
      width: calc(100% - 20px);
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 8px;
      border: 1px solid #ccc;
    }
    #comment-form button {
      padding: 10px 20px;
      background-color: #a0522d;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    #comment-form button:hover {
      background-color: #8b4513;
    }
    #comments-container {
      margin-top: 20px;
    }
    .comment {
      border: 1px solid #f5d5a1;
      background-color: #fffaf0;
      padding: 15px;
      margin-bottom: 10px;
      border-radius: 8px;
    }
    .comment p {
      margin: 0;
    }
    .comment .comment-author {
      font-weight: bold;
      color: #a0522d;
    }
    .delete-btn {
        background-color: #ff4d4d;
        color: white;
        border: none;
        padding: 5px 10px;
        border-radius: 5px;
        cursor: pointer;
        float: right;
    }
  </style>
</head>
<body>

<header>
  <h1>SMPN 1 PANGKALAN LADA</h1>
  <h2>Website Kelas 9B</h2>
</header>

<nav>
  <button class="menu-btn" onclick="showContent('struktur')">Struktur Kelas</button>
  <button class="menu-btn" onclick="showContent('anggota')">Anggota Siswa</button>
  <button class="menu-btn" onclick="showContent('tata')">Tata Tertib</button>
  <button class="menu-btn" onclick="showContent('kebersihan')">Peraturan Kebersihan</button>
  <button class="menu-btn" onclick="showContent('pelajaran')">Jadwal Pelajaran</button>
  <button class="menu-btn" onclick="showContent('piket')">Jadwal Piket</button>
  <button class="menu-btn" onclick="showContent('pr')">Tugas / PR</button>
  <button class="menu-btn" onclick="showContent('galeri')">Galeri Foto</button>
  <button class="menu-btn" onclick="showContent('pesan')">Tuliskan Komentar</button>
</nav>

<div id="content">
  </div>

<footer>
  <p>Website Kelas 9B | Designed by: APutraN</p>
  <p>
    <a href="https://www.instagram.com/onebraderclass?igsh=dmIydWc1aG50aWdy" target="_blank">Instagram</a> |
    <a href="https://www.tiktok.com/@asixxbee6?_t=ZS-8xULIQm8QXR&_r=1" target="_blank">TikTok</a> |
    <a href="#" onclick="adminLogin()">Admin</a>
  </p>
</footer>

<script>
  // Mengambil komentar dari local storage atau membuat array kosong jika tidak ada
  let comments = JSON.parse(localStorage.getItem('comments')) || [];

  function showContent(menu) {
    const contentDiv = document.getElementById("content");
    const content = {
      beranda: `
        <h2>Selamat datang di Website Kelas 9B!</h2>
        <p>Klik menu di atas untuk melihat informasi penting dan seru seputar kelas kita 😊</p>
      `,
      struktur: `
        <h2>Struktur Kelas 9B</h2>
        <ul>
          <h3>Wali Kelas: Akan Hadir</h3>
          <li>Ketua Kelas: Akan Hadir</li>
          <li>Wakil Ketua: Akan Hadir</li>
          <li>Sekretaris 1: Akan Hadir</li>
          <li>Sekretaris 2: Akan Hadir</li>
          <li>Bendahara 1: Akan Hadir</li>
          <li>Bendahara 2: Akan Hadir</li>
        </ul>
      `,
      anggota: `
        <h2>Daftar Anggota Siswa Kelas 9B (32 Siswa)</h2>
        <ol>
          <li>Adelia Ainun Zakia</li><li>Adinda Selmi Yusfita</li><li>Ahmad Putra Nurrohim</li><li>Alisia Jastin</li><li>Amelia Nur Rahmadani</li><li>Anita Sulfania</li><li>Cahya Nengrum Aulia Ulfah</li><li>Choliv Fuadiya</li><li>Dafi idriansyah</li><li>Devi Nur Maulidda</li><li>Dewi Audray Agdiningviar</li><li>Dimas Surya Irawan</li><li>Dira Hadi Erwanto</li><li>Dwi Irji Febiana</li><li>Edo Hariyadi</li><li>Erwin Alfiromdoni</li><li>Imana Pungky Mavano</li><li>Micko Maulana</li><li>Muhamad Azriel Ardianta</li><li>Muhamad Fahmy Ferdiansyah</li><li>Muhamad Farras Ahsanul Huda</li><li>Muhammad Arjuna Muarif Salam</li><li>Muhammad Rishad Tabatala Arsodiq</li><li>Mutiara Dwi Febrianti</li><li>Nabila Azzahra</li><li>Nur Sabrina</li><li>Putri Nur Ainiyyah Zahraa</li><li>Riyo Ramadhani</li><li>Silda Simatus Zahro</li><li>Sintia Nabila</li><li>Yogik Aditiyono</li><li>Zaky Sofyan</li>
        </ol>
      `,
      tata: `
        <h2>Tata Tertib Kelas</h2>
        <ol>
          <li>Datang tepat waktu sebelum jam pelajaran dimulai.</li><li>Berpakaian rapi dan sesuai peraturan sekolah.</li><li>Berperilaku sopan terhadap guru dan teman.</li><li>Menjaga kebersihan dan kerapihan kelas.</li>
        </ol>
      `,
      kebersihan: `
        <h2>Peraturan Kebersihan Kelas</h2>
        <ul>
          <li>Buang sampah pada tempatnya.</li><li>Dilarang makan/minum di dalam kelas saat pelajaran berlangsung.</li><li>Petugas piket wajib menyapu dan merapikan kelas setiap pagi dan sebelum pulang sekolah.</li>
        </ul>
      `,
      pelajaran: `
        <h2>Jadwal Pelajaran Kelas 9B</h2>
        <table>
          <tr><th>Hari</th><th>Mata Pelajaran</th></tr>
          <tr><td>Senin</td><td>Segera Hadir</td></tr><tr><td>Selasa</td><td>Segera Hadir</td></tr><tr><td>Rabu</td><td>Segera Hadir</td></tr><tr><td>Kamis</td><td>Segera Hadir</td></tr><tr><td>Jumat</td><td>Segera Hadir</td></tr><tr><td>Sabtu</td><td>P5,P5,P5</td></tr>
        </table>
      `,
      piket: `
        <h2>Jadwal Piket Kelas 9b</h2>
        <table>
          <tr><th>Hari</th><th>Nama Petugas</th></tr>
          <tr><td>Senin</td><td>Segera Hadir</td></tr><tr><td>Selasa</td><td>Segera Hadir</td></tr><tr><td>Rabu</td><td>Segera Hadir</td></tr><tr><td>Kamis</td><td>Segera Hadir</td></tr><tr><td>Jumat</td><td>Segera Hadir</td></tr><tr><td>Sabtu</td><td>Segera Hadir</td></tr>
        </table>
      `,
      pr: `
        <h2>Tugas / PR Terbaru</h2>
        <ul>
          <li>Matematika: segera hadir</li><li>IPA: segera hadir</li><li>PKN: segera hadir</li>
        </ul>
      `,
      galeri: `
        <h2>Galeri Foto & Kenangan</h2>
        <img src="fotoulangan.jpg" style="width:100%; border-radius:10px;"><p>📸 foto ulangan hari ke 2 😍</p>
        <img src="persiapanupacara.jpg" style="width:100%; border-radius:10px;"><p>📸 foto persiapan upacara 😍</p>
        <img src="upacara1.jpg" style="width:100%; border-radius:10px;"><p>📸 fotbar setelah upacara 😍</p>
        <img src="upacara2.jpg" style="width:100%; border-radius:10px;"><p>📸 fotbar setelah upacara 😍</p>
        <img src="upacara3.jpg" style="width:100%; border-radius:10px;"><p>📸 fotbar setelah upacara 😍</p>
        <img src="kemah1.jpg" style="width:100%; border-radius:10px;"><p>📸 fotbar cewek cantik 8b 😍</p>
        <img src="kemah2.jpg" style="width:100%; border-radius:10px;"><p>📸 Arjuna kecapean makan 🤣🤣</p>
        <img src="kemah3.jpg" style="width:100%; border-radius:10px;"><p>📸 foto bapak" ngerumpi😍</p>
        <img src="kemah4.jpg" style="width:100%; border-radius:10px;"><p>📸  cewek nya makan, cowok nya yang masak 😅</p>
        <img src="tarian1.jpg" style="width:100%; border-radius:10px;"><p>📸 fotbar setelah tampil menari 😍</p>
        <img src="ibul.jpg" style="width:100%; border-radius:10px;"><p>📸 foto bersama Ibu Laila 😍😍</p>
      `,
      pesan: `
        <h2>komentar / Kirim Pesan</h2>
        <p>Silakan tinggalkan pesan, kesan, atau komentar Anda di bawah ini!</p>
        <form id="comment-form" onsubmit="submitComment(event)">
          <input type="text" id="comment-author" placeholder="Nama Anda" required>
          <textarea id="comment-text" rows="4" placeholder="Tulis pesan Anda di sini..." required></textarea>
          <button type="submit">Kirim Pesan</button>
        </form>
        <div id="comments-container">
          <h3>Komentar Terbaru:</h3>
          </div>
      `
    };
    contentDiv.innerHTML = content[menu] || "<p>Menu belum tersedia.</p>";
    // Jika menu yang dipilih adalah 'pesan', tampilkan komentar yang ada
    if (menu === 'pesan') {
      renderComments();
    }
  }

  function renderComments(isAdmin = false) {
    const container = document.getElementById('comments-container');
    if (!container) return; // Keluar jika container tidak ditemukan
    
    // Simpan elemen judul jika ada, atau buat judul baru
    const title = container.querySelector('h3') || document.createElement('h3');
    if (!container.querySelector('h3')) {
        title.textContent = "Komentar Terbaru:";
    }

    container.innerHTML = ''; // Bersihkan kontainer
    container.appendChild(title); // Tambahkan kembali judul

    if (comments.length === 0) {
      container.innerHTML += '<p>Belum ada komentar.</p>';
    } else {
      comments.forEach((comment, index) => {
        const commentDiv = document.createElement('div');
        commentDiv.className = 'comment';
        commentDiv.innerHTML = `
          <p class="comment-author">${escapeHTML(comment.author)}</p>
          <p>${escapeHTML(comment.text)}</p>
          ${isAdmin ? `<button class="delete-btn" onclick="deleteComment(${index})">Hapus</button>` : ''}
        `;
        container.appendChild(commentDiv);
      });
    }
  }

  function submitComment(event) {
    event.preventDefault();
    const author = document.getElementById('comment-author').value;
    const text = document.getElementById('comment-text').value;

    comments.unshift({ author, text }); // Tambah komentar baru di awal array
    localStorage.setItem('comments', JSON.stringify(comments));

    document.getElementById('comment-form').reset();
    renderComments();
  }

  function deleteComment(index) {
    if (confirm('Apakah Anda yakin ingin menghapus komentar ini?')) {
        comments.splice(index, 1);
        localStorage.setItem('comments', JSON.stringify(comments));
        renderAdminView(); // Muat ulang tampilan admin
    }
  }

  function adminLogin() {
    const password = prompt("Masukkan kata sandi admin:", "");
    if (password === "admin9bravo") { // Ganti "admin9bravo" dengan kata sandi yang lebih aman
      renderAdminView();
    } else if (password !== null) {
      alert("Kata sandi salah!");
    }
  }

  function renderAdminView() {
      const contentDiv = document.getElementById("content");
      contentDiv.innerHTML = `
        <h2>Panel Admin - Kelola Komentar</h2>
        <p>Anda login sebagai admin. Di sini Anda dapat melihat dan menghapus komentar.</p>
        <div id="comments-container">
            <h3>Daftar Semua Komentar:</h3>
            </div>
      `;
      renderComments(true); // 'true' menandakan ini adalah tampilan admin
  }

  // Fungsi untuk menghindari injeksi HTML sederhana
  function escapeHTML(str) {
      return str.replace(/[&<>"']/g, function(match) {
          return {
              '&': '&amp;',
              '<': '&lt;',
              '>': '&gt;',
              '"': '&quot;',
              "'": '&#39;'
          }[match];
      });
  }

  // Tampilkan konten beranda saat halaman pertama kali dimuat
  window.onload = () => showContent('beranda');
</script>

</body>
</html>

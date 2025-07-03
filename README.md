 <!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Website Kelas 9B</title>
    <style>
        /* General Styling */
        body {
            font-family: 'Segoe UI', sans-serif;
            background-color: #fff6ec;
            margin: 0;
            padding: 0;
        }
        #content {
            padding: 25px;
            background-color: #fffdf8;
            min-height: 300px;
        }
        /* Header & Footer */
        header, footer {
            background-color: #a0522d;
            color: white;
            text-align: center;
            padding: 15px;
            position: relative;
        }
        header h1, header h2 {
            margin: 5px 0;
        }
        footer a {
            color: #ffffff;
            font-weight: bold;
            text-decoration: none;
            margin: 0 10px;
        }
        /* Navigation */
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
            transition: background-color 0.3s;
        }
        .menu-btn:hover {
            background-color: #dfa96b;
        }
        /* Tables */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        th, td {
            border: 1px solid #ccc;
            padding: 10px;
            text-align: center;
        }
        th {
            background-color: #f0c38e;
        }
        /* Lists */
        ul, ol {
            line-height: 1.8;
        }
        /* --- FITUR BARU --- */
        /* Latar Lagu */
        .footer-controls {
            margin-top: 15px;
        }
        #music-toggle-btn {
            background-color: #f0c38e;
            border: none;
            border-radius: 12px;
            padding: 10px 15px;
            font-weight: bold;
            cursor: pointer;
        }
        /* Login Admin */
        .admin-login-btn {
            position: absolute;
            top: 15px;
            right: 20px;
            background-color: #f0c38e;
            border: none;
            border-radius: 8px;
            padding: 8px 12px;
            cursor: pointer;
            font-weight: bold;
        }
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.5);
        }
        .modal-content {
            background-color: #fffdf8;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #a0522d;
            width: 80%;
            max-width: 400px;
            border-radius: 12px;
            position: relative;
            text-align: center;
        }
        .modal-content input {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 8px;
            border: 1px solid #ccc;
        }
        .modal-content button {
            width: 95%;
            padding: 10px;
            background-color: #a0522d;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
        }
        .close-btn {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
        }
        /* Pesan & Komentar */
        #comment-form {
            margin-top: 20px;
            padding: 15px;
            background-color: #fff6ec;
            border-radius: 8px;
        }
        #comment-form input, #comment-form textarea {
            width: 95%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 8px;
        }
        #comment-form button {
            padding: 10px 20px;
            background-color: #a0522d;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
        }
        .comment-item {
            border: 1px solid #f5d5a1;
            background-color: #fffdf8;
            padding: 15px;
            margin-top: 15px;
            border-radius: 8px;
            position: relative;
        }
        .comment-item p {
            margin: 0;
        }
        .comment-item strong {
            color: #a0522d;
        }
        .admin-only {
            display: none; /* Tombol hapus disembunyikan secara default */
        }
        /* Tampilkan elemen .admin-only jika body memiliki class .admin-view */
        body.admin-view .admin-only {
            display: inline-block;
            position: absolute;
            top: 5px;
            right: 10px;
            background-color: #ff4d4d;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 3px 8px;
            cursor: pointer;
            font-size: 12px;
        }
    </style>
</head>
<body>
    <div id="login-modal" class="modal">
        <div class="modal-content">
            <span class="close-btn">&times;</span>
            <h2>Login Admin</h2>
            <form id="login-form">
                <input type="text" id="username" placeholder="Username" required>
                <input type="password" id="password" placeholder="Password" required>
                <button type="submit">Login</button>
            </form>
        </div>
    </div>
    <header>
        <h1>SMPN 1 PANGKALAN LADA</h1>
        <h2>Website Kelas 9B</h2>
        <button id="login-btn-header" class="admin-login-btn">Login Admin</button>
    </header>
    <nav>
        <button class="menu-btn" data-menu="struktur">Struktur Kelas</button>
        <button class="menu-btn" data-menu="anggota">Anggota Siswa</button>
        <button class="menu-btn" data-menu="tata">Tata Tertib</button>
        <button class="menu-btn" data-menu="kebersihan">Peraturan Kebersihan</button>
        <button class="menu-btn" data-menu="pelajaran">Jadwal Pelajaran</button>
        <button class="menu-btn" data-menu="piket">Jadwal Piket</button>
        <button class="menu-btn" data-menu="pr">Tugas / PR</button>
        <button class="menu-btn" data-menu="galeri">Galeri Foto</button>
        <button class="menu-btn" data-menu="pesan">Pesan & Komentar</button>
    </nav>
    <div id="content">
        <h2>Selamat datang di Website Kelas 9B!</h2>
        <p>Klik menu di atas untuk melihat informasi penting dan seru seputar kelas kita 😊</p>
    </div>
    <footer>
        <p>Website Kelas 9B | Designed by: APutraN</p>
        <p>
            <a href="https://www.instagram.com/onebraderclass?igsh=dmIydWc1aG50aWdy" target="_blank">Instagram</a> |
            <a href="https://www.tiktok.com/@asixxbee6?_t=ZS-8xULIQm8QXR&_r=1" target="_blank">TikTok</a>
        </p>
        <div class="footer-controls">
            <button id="music-toggle-btn">🎵 Putar Musik</button>
            <audio id="background-music" src="lagu-latar.mp3" loop></audio>
        </div>
    </footer>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // --- STATE MANAGEMENT ---
            let isAdmin = false;
            let comments = JSON.parse(localStorage.getItem('comments')) || [];
            // --- ELEMENT SELECTORS ---
            const contentDiv = document.getElementById('content');
            const musicToggleBtn = document.getElementById('music-toggle-btn');
            const backgroundMusic = document.getElementById('background-music');
            const loginModal = document.getElementById('login-modal');
            const loginBtnHeader = document.getElementById('login-btn-header');
            const closeModalBtn = document.querySelector('.close-btn');
            const loginForm = document.getElementById('login-form');
            // --- CONTENT DATA ---
            const contentData = {
                struktur: `
                    <h2>Struktur Kelas 9B</h2>
                    <ul>
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
                        <li>Adelia Ainun Zakia</li><li>Adinda Selmi Yusfita</li><li>Ahmad Putra Nurrohim</li>
                        <li>Alisia Jastin</li><li>Amelia Nur Rahmadani</li><li>Anita Sulfania</li>
                        <li>Cahya Nengrum Aulia Ulfah</li><li>Choliv Fuadiya</li><li>Dafi idriansyah</li>
                        <li>Devi Nur Maulidda</li><li>Dewi Audray Agdiningviar</li><li>Dimas Surya Irawan</li>
                        <li>Dira Hadi Erwanto</li><li>Dwi Irji Febiana</li><li>Edo Hariyadi</li>
                        <li>Erwin Alfiromdoni</li><li>Imana Pungky Mavano</li><li>Micko Maulana</li>
                        <li>Muhamad Azriel Ardianta</li><li>Muhamad Fahmy Ferdiansyah</li><li>Muhamad Farras Ahsanul Huda</li>
                        <li>Muhammad Arjuna Muarif Salam</li><li>Muhammad Rishad Tabatala Arsodiq</li><li>Mutiara Dwi Febrianti</li>
                        <li>Nabila Azzahra</li><li>Nur Sabrina</li><li>Putri Nur Ainiyyah Zahraa</li>
                        <li>Riyo Ramadhani</li><li>Silda Simatus Zahro</li><li>Sintia Nabila</li>
                        <li>Yogik Aditiyono</li><li>Zaky Sofyan</li>
                    </ol>
                `,
                tata: `
                    <h2>Tata Tertib Kelas</h2>
                    <ol>
                        <li>Datang tepat waktu sebelum jam pelajaran dimulai.</li>
                        <li>Berpakaian rapi dan sesuai peraturan sekolah.</li>
                        <li>Berperilaku sopan terhadap guru dan teman.</li>
                        <li>Menjaga kebersihan dan kerapihan kelas.</li>
                    </ol>
                `,
                kebersihan: `
                    <h2>Peraturan Kebersihan Kelas</h2>
                    <ul>
                        <li>Buang sampah pada tempatnya.</li>
                        <li>Dilarang makan/minum di dalam kelas saat pelajaran berlangsung.</li>
                        <li>Petugas piket wajib menyapu dan merapikan kelas setiap pagi dan sebelum pulang sekolah.</li>
                    </ul>
                `,
                pelajaran: `
                    <h2>Jadwal Pelajaran Kelas 9B</h2>
                    <table>
                        <tr><th>Hari</th><th>Mata Pelajaran</th></tr>
                        <tr><td>Senin</td><td>Segera Hadir</td></tr>
                        <tr><td>Selasa</td><td>Segera Hadir</td></tr>
                        <tr><td>Rabu</td><td>Segera Hadir</td></tr>
                        <tr><td>Kamis</td><td>Segera Hadir</td></tr>
                        <tr><td>Jumat</td><td>Segera Hadir</td></tr>
                        <tr><td>Sabtu</td><td>P5,P5,P5</td></tr>
                    </table>
                `,
                piket: `
                    <h2>Jadwal Piket Mingguan</h2>
                    <table>
                        <tr><th>Hari</th><th>Nama Petugas</th></tr>
                        <tr><td>Senin</td><td>Segera Hadir</td></tr>
                        <tr><td>Selasa</td><td>Segera Hadir</td></tr>
                        <tr><td>Rabu</td><td>Segera Hadir</td></tr>
                        <tr><td>Kamis</td><td>Segera Hadir</td></tr>
                        <tr><td>Jumat</td><td>Segera Hadir</td></tr>
                        <tr><td>Sabtu</td><td>Segera Hadir</td></tr>
                    </table>
                `,
                pr: `
                    <h2>Tugas / PR Terbaru</h2>
                    <ul>
                        <li>Matematika: segera hadir</li>
                        <li>IPA: segera hadir</li>
                        <li>PKN: segera hadir</li>
                    </ul>
                `,
                galeri: `
                    <h2>Galeri Foto & Kenangan</h2>
                    <img src="fotoulangan.jpg" alt="Foto Ulangan" style="width:100%; border-radius:10px;">
                    <p>📸 foto ulangan hari ke 2 😍</p>
                    <img src="persiapanupacara.jpg" alt="Persiapan Upacara" style="width:100%; border-radius:10px;">
                    <p>📸 foto persiapan upacara 😍</p>
                    <img src="upacara1.jpg" alt="Setelah Upacara" style="width:100%; border-radius:10px;">
                    <p>📸 fotbar setelah upacara 😍</p>
                    <img src="upacara2.jpg" alt="Setelah Upacara" style="width:100%; border-radius:10px;">
                    <p>📸 fotbar setelah upacara 😍</p>
                    <img src="upacara3.jpg" alt="Setelah Upacara" style="width:100%; border-radius:10px;">
                    <p>📸 fotbar setelah upacara 😍</p>
                    <img src="kemah1.jpg" alt="Kegiatan Kemah" style="width:100%; border-radius:10px;">
                    <p>📸 fotbar cewek cantik 8b 😍</p>
                    <img src="kemah2.jpg" alt="Kegiatan Kemah" style="width:100%; border-radius:10px;">
                    <p>📸 Arjuna kecapean makan 🤣🤣</p>
                    <img src="kemah3.jpg" alt="Kegiatan Kemah" style="width:100%; border-radius:10px;">
                    <p>📸 foto bapak" ngerumpi😍</p>
                    <img src="kemah4.jpg" alt="Kegiatan Kemah" style="width:100%; border-radius:10px;">
                    <p>📸 cewek nya makan, cowok nya yang masak 😅</p>
                    <img src="tarian1.jpg" alt="Setelah Menari" style="width:100%; border-radius:10px;">
                    <p>📸 fotbar setelah tampil menari 😍</p>
                    <img src="ibul.jpg" alt="Bersama Ibu Laila" style="width:100%; border-radius:10px;">
                    <p>📸 foto bersama Ibu Laila 😍😍</p>
                `,
                pesan:  `
                    <h3>Pesan & Komentar</h3>
                    <textarea id="commentInput" rows="4" placeholder="Tulis komentar..."></textarea><br>
                    <button onclick="addComment()">Kirim</button>
                    <ul id="commentList"></ul>
                `;
            };
            // --- FUNCTIONS ---
            function showContent(menuKey) {
                contentDiv.innerHTML = contentData[menuKey] || "<p>Menu belum tersedia.</p>";
                if (menuKey === 'pesan') {
                    renderComments();
                    // Add event listener for the new form
                    const newCommentForm = document.getElementById('comment-form');
                    if (newCommentForm) {
                        newCommentForm.addEventListener('submit', handleCommentSubmit);
                    }
                }
            }
            function renderComments() {
                const commentList = document.getElementById('comment-list');
                if (!commentList) return;
                commentList.innerHTML = ''; // Clear existiitem';
                    commentDiv.innerHTML = `
                        <p><strong>${escapeHTML(comment.name)}:</strong></p>
                        <p>${escapeHTML(comment.text)}</p>
                        <button class="admin-only delete-comment-btn" data-index="${index}">Hapus</button>
                    `;
                    commentList.appendChild(commentDiv);
                });               
                // Add event listeners for delete buttons
                document.querySelectorAll('.delete-comment-btn').forEach(btn => {
                    btn.addEventListener('click', (e) => {
                        const indexToDelete = e.target.getAttribute('data-index');
                        deleteComment(indexToDelete);
                    });
                });
            }         
            function handleCommentSubmit(event) {
                event.preventDefault();
                const nameInput = document.getElementById('comment-name');
                const textInput = document.getElementById('comment-text');            
                const newComment = {
                    name: nameInput.value,
                    text: textInput.value
                };                
                comments.push(newComment);
                localStorage.setItem('comments', JSON.stringify(comments));           
                renderComments();              
                nameInput.value = '';
                textInput.value = '';
            }        
            function deleteComment(index) {
                if (!isAdmin) {
                    alert('Anda harus login sebagai admin untuk menghapus komentar.');
                    return;
                }
                comments.splice(index, 1);
                localStorage.setItem('comments', JSON.stringify(comments));
                renderComments();
            }
            function toggleMusic() {
                if (backgroundMusic.paused) {
                    backgroundMusic.play().catch(e => console.log("Autoplay ditolak oleh browser. Interaksi user diperlukan."));
                    musicToggleBtn.textContent = '⏸️ Jeda Musik';
                } else {
                    backgroundMusic.pause();
                    musicToggleBtn.textContent = '🎵 Putar Musik';
                }
            }
            function handleLogin(event) {
                event.preventDefault();
                const username = document.getElementById('username').value;
                const password = document.getElementById('password').value;
                // Ganti 'admin' dan '12345' dengan username & password yang Anda inginkan
                if (username === 'admin' && password === '12345') {
                    isAdmin = true;
                    document.body.classList.add('admin-view');
                    loginModal.style.display = 'none';
                    loginBtnHeader.textContent = 'Logout';
                    alert('Login berhasil!');
                    // Refresh content to show admin buttons if on comment page
                    const activeMenu = document.querySelector('.menu-btn.active')?.dataset.menu;
                    if (activeMenu === 'pesan') {
                       renderComments();
                    }
                } else {
                    alert('Username atau password salah!');
                }
            }
            function logout() {
                isAdmin = false;
                document.body.classList.remove('admin-view');
                loginBtnHeader.textContent = 'Login Admin';
                alert('Anda telah logout.');
                 // Refresh content to hide admin buttons if on comment page
                 const activeMenu = document.querySelector('.menu-btn.active')?.dataset.menu;
                 if (activeMenu === 'pesan') {
                    renderComments();
                 }
            }           
            // Simple HTML escaping function to prevent XSS
            function escapeHTML(str) {
                return str.replace(/[&<>'"]/g, 
                    tag => ({
                        '&': '&amp;',
                        '<': '&lt;',
                        '>': '&gt;',
                        "'": '&#39;',
                        '"': '&quot;'
                    }[tag] || tag)
                );
            }
            // --- EVENT LISTENERS ---
            document.querySelectorAll('.menu-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    document.querySelectorAll('.menu-btn').forEach(b => b.classList.remove('active'));
                    e.target.classList.add('active');
                    const menuKey = e.target.getAttribute('data-menu');
                    showContent(menuKey);
                });
            });
            musicToggleBtn.addEventListener('click', toggleMusic);
            loginBtnHeader.addEventListener('click', () => {
                if (isAdmin) {
                    logout();
                } else {
                    loginModal.style.display = 'block';
                }
            });
            closeModalBtn.addEventListener('click', () => {
                loginModal.style.display = 'none';
            });
            window.addEventListener('click', (event) => {
                if (event.target == loginModal) {
                    loginModal.style.display = 'none';
                }
            });
            loginForm.addEventListener('submit', handleLogin);
        });
    </script>
</body>
</html>

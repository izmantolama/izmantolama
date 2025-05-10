from zipfile import ZipFile
import os

# Klasör ve dosya yapısını oluşturma
project_dir = "/mnt/data/izmantolama_website"
os.makedirs(project_dir, exist_ok=True)

# index.html içeriği
index_html = """<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>İzmantolama Yapı Sistemleri</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>İzmantolama Yapı Sistemleri</h1>
        <p>İzmir'in her yerine profesyonel çözümler</p>
    </header>

    <nav>
        <a href="#hizmetler">Hizmetler</a>
        <a href="#hakkimizda">Hakkımızda</a>
        <a href="#iletisim">İletişim</a>
    </nav>

    <section id="hizmetler">
        <h2>Hizmetlerimiz</h2>
        <div class="hizmet">
            <h3>İç Cephe</h3>
            <img src="https://via.placeholder.com/300x200?text=İç+Cephe" alt="İç Cephe">
        </div>
        <div class="hizmet">
            <h3>Dış Cephe</h3>
            <img src="https://via.placeholder.com/300x200?text=Dış+Cephe" alt="Dış Cephe">
        </div>
        <div class="hizmet">
            <h3>Çatı</h3>
            <img src="https://via.placeholder.com/300x200?text=Çatı" alt="Çatı">
        </div>
        <div class="hizmet">
            <h3>Tadilat</h3>
            <img src="https://via.placeholder.com/300x200?text=Tadilat" alt="Tadilat">
        </div>
    </section>

    <section id="hakkimizda">
        <h2>Hakkımızda</h2>
        <p>İzmantolama Yapı Sistemleri olarak İzmir'in dört bir yanına iç cephe, dış cephe, çatı ve tadilat hizmetleri sunmaktayız. Kaliteli işçilik ve müşteri memnuniyeti bizim için ön plandadır.</p>
    </section>

    <section id="iletisim">
        <h2>İletişim</h2>
        <p>Vatan Çiftçi</p>
        <p>Telefon: 0542 488 93 67</p>
        <p>Email: vatan.exe@gmail.com</p>
    </section>

    <footer>
        <p>&copy; 2025 İzmantolama Yapı Sistemleri</p>
    </footer>
</body>
</html>
"""

# style.css içeriği
style_css = """body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #f4b400;
    color: black;
    text-align: center;
    padding: 40px 20px;
}

nav {
    background-color: #222;
    text-align: center;
    padding: 10px 0;
}

nav a {
    color: white;
    margin: 0 15px;
    text-decoration: none;
}

section {
    padding: 40px 20px;
}

.hizmet {
    margin-bottom: 20px;
}

.hizmet img {
    max-width: 100%;
    height: auto;
    display: block;
    margin-top: 10px;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 20px;
}
"""

# Dosyaları oluşturma
with open(os.path.join(project_dir, "index.html"), "w", encoding="utf-8") as f:
    f.write(index_html)

with open(os.path.join(project_dir, "style.css"), "w", encoding="utf-8") as f:
    f.write(style_css)

# Zip dosyası oluşturma
zip_path = "/mnt/data/izmantolama_website.zip"
with ZipFile(zip_path, 'w') as zipf:
    zipf.write(os.path.join(project_dir, "index.html"), arcname="index.html")
    zipf.write(os.path.join(project_dir, "style.css"), arcname="style.css")

zip_path

<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <title>Little Mushroom - Final Archive</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel+Decorative:wght@700&family=Playfair+Display:ital,wght@0,700;1,700&family=Dancing+Script:wght@600;700&display=swap" rel="stylesheet">
    
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            background: radial-gradient(circle at center, #1b1b4b 0%, #050510 100%);
            color: #e0e0ff;
            font-family:'Cinzel Decorative', serif; 
            overflow: hidden;
            height: 100vh;
            
          /* 1. LOGO, TIÊU ĐỀ CHÍNH (h1), MỤC LỤC - Phông Cinzel uốn lượn nghệ thuật */
h1, .logo, nav ul li a, h2 {
    font-family: 'Cinzel Decorative', 'Playfair Display', serif !important;
    text-transform: none !important;
}

/* 2. CÂU NÓI NHÂN VẬT & TIÊU ĐỀ PHỤ - Phông "Viết chữ đẹp" uốn lượn */
.char-quote, .sub-title, .quote-main {
    font-family: 'Dancing Script', cursive !important;
    font-size: 1.8rem !important; /* Chỉnh to lên cho dễ nhìn */
    color: #d8b4fe !important; /* Màu tím nhạt mộng mơ */
    font-style: normal !important; /* Phông này bản thân nó đã nghiêng rồi */
    text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
}

/* 3. MÔ TẢ - Phông giống Times New Roman nhưng sang trọng hơn */
p, li, span, div, .story-text {
    font-family: 'Playfair Display', serif !important;
    font-weight: 400;
    line-height: 1.8;
    letter-spacing: 0.3px;
    color: #e0e0ff;
}

/* Tinh chỉnh tiêu đề chính Cây Nấm Nhỏ */
h1 {
    font-size: 5.5rem !important;
    margin-bottom: 5px;
}

/* Tinh chỉnh tiêu đề phụ ngay dưới h1 */
.sub-title {
    margin-top: -15px;
    display: block;
} 
}
        }

        /* --- HIỆU ỨNG NỀN --- */
        #fx-layer { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 0; pointer-events: none; }
        .star { position: absolute; background: white; border-radius: 50%; animation: twinkle var(--d) infinite; }
        .graphic-mushroom {
            position: absolute; background: rgba(216, 180, 254, 0.5); border-radius: 50% 50% 20% 20%;
            animation: floatUp var(--d) infinite ease-in-out; filter: blur(1px);
        }
        @keyframes floatUp { 0% { transform: translateY(110vh) scale(0.7); opacity: 0; } 100% { transform: translateY(-20vh) scale(1.3); opacity: 0; } }
        @keyframes shoot { 0% { transform: translateX(100vw) translateY(-20vh) rotate(-45deg); opacity: 0; } 10% { opacity: 1; } 30% { transform: translateX(20vw) translateY(60vh) rotate(-45deg); opacity: 0; } }
        .comet { position: absolute; width: 2px; height: 100px; background: linear-gradient(to bottom, transparent, #fff); animation: shoot 3s infinite linear; opacity: 0; }

        /* Navigation */
        header {
            position: fixed; top: 0; width: 100%; padding: 1.2rem 5%; z-index: 1000;
            background: rgba(13, 13, 43, 0.8); backdrop-filter: blur(15px);
            display: flex; justify-content: space-between; align-items: center;
            border-bottom: 1px solid rgba(106, 90, 205, 0.3);
        }
        .logo { font-family: 'Playfair Display'; font-size: 1.5rem; color: #a29bfe; font-weight: bold; }
        nav ul { display: flex; list-style: none; }
        nav ul li a { color: #fff; text-decoration: none; margin-left: 2rem; font-size: 0.8rem; text-transform: uppercase; cursor: pointer; transition: 0.3s; }
        nav ul li a:hover { color: #1e90ff; }

        /* Pages */
        .page {
            height: 100vh; width: 100vw; display: none; flex-direction: column;
            justify-content: center; align-items: center; padding-top: 80px;
            position: relative; z-index: 10; animation: fadeIn 0.8s;
        }
        .page.active { display: flex; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* --- THẾ GIỚI --- */
        .world-box { width: 100%; max-width: 1000px; padding: 0 20px; }
        .map-gallery { display: flex; gap: 15px; height: 230px; margin-bottom: 20px; }
        .map-card { flex: 1; border-radius: 20px; overflow: hidden; position: relative; cursor: pointer; transition: 0.6s; border: 1px solid rgba(255,255,255,0.1); }
        .map-card img { width: 100%; height: 100%; object-fit: cover; filter: brightness(0.4); }
        .map-card.active-map { flex: 4; border-color: #1e90ff; }
        .map-card.active-map img { filter: brightness(1); }
        .map-title { position: absolute; bottom: 10px; left: 15px; font-size: 1rem; font-family: 'Playfair Display'; }

        .desc-panel { background: rgba(255, 255, 255, 0.05); padding: 25px; border-radius: 20px; min-height: 120px; border-left: 4px solid #1e90ff; }
        .desc-content { display: none; animation: fadeIn 0.5s; line-height: 1.6; font-size: 0.85rem; }
        .desc-content.active-desc { display: block; }

        /* --- NHÂN VẬT (CỐ ĐỊNH THANH CUỘN) --- */
        .char-scroll {
            display: flex; gap: 25px; overflow-x: auto; padding: 30px 5% 50px; width: 100%;
            scroll-behavior: smooth;
        }
        
        /* HIỆN THANH CUỘN ĐỂ BẠN DỄ DÙNG */
        .char-scroll::-webkit-scrollbar { height: 8px; }
        .char-scroll::-webkit-scrollbar-track { background: rgba(255,255,255,0.05); border-radius: 10px; }
        .char-scroll::-webkit-scrollbar-thumb { background: #6a5acd; border-radius: 10px; }
        .char-scroll::-webkit-scrollbar-thumb:hover { background: #1e90ff; }

        .char-card {
            min-width: 280px; background: rgba(255, 255, 255, 0.07);
            backdrop-filter: blur(10px); border-radius: 25px; padding: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1); transition: 0.4s;
        }
        .char-card:hover { transform: translateY(-10px); border-color: #1e90ff; background: rgba(255, 255, 255, 0.12); }
        .char-img { width: 100%; height: 280px; object-fit: cover; border-radius: 15px; margin-bottom: 15px; }
        .char-job { color: #1e90ff; font-size: 0.7rem; font-weight: bold; text-transform: uppercase; margin-bottom: 5px; }
        .char-quote { font-family: 'Dancing Script'; font-size: 1.3rem; color: #d8b4fe; margin-top: 10px; border-top: 1px solid rgba(255,255,255,0.1); padding-top: 10px; }

        /* --- CỐT TRUYỆN --- */
        .story-box { background: rgba(13, 13, 43, 0.7); padding: 40px; border-radius: 35px; max-width: 850px; border: 1px solid rgba(106, 90, 205, 0.2); }
        .story-text { max-height: 350px; overflow-y: auto; padding-right: 15px; line-height: 1.8; font-size: 0.9rem; }
        .story-text::-webkit-scrollbar { width: 5px; }
        .story-text::-webkit-scrollbar-thumb { background: #6a5acd; border-radius: 5px; }

        .quote-main { font-family: 'Dancing Script'; font-size: 2.8rem; color: #d8b4fe; margin-top: 15px; text-align: center; }
    </style>
</head>
<body>

    <div id="fx-layer"></div>

    <header>
        <div class="logo">LITTLE MUSHROOM</div>
        <nav>
            <ul>
                <li><a onclick="showPage('home')">Trang Chủ</a></li>
                <li><a onclick="showPage('world')">Thế Giới</a></li>
                <li><a onclick="showPage('chars')">Nhân Vật</a></li>
                <li><a onclick="showPage('story')">Cốt Truyện</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="page active">
        <h1 style="font-size: 4.5rem; font-family: 'Playfair Display'; text-shadow: 0 0 20px #6a5acd;">Cây Nấm Nhỏ</h1>
        <p class="quote-main">"Con người là một sinh vật vĩ đại."</p>
    </section>

    <section id="world" class="page">
        <div class="world-box">
            <h2 style="font-family: 'Playfair Display'; color: #1e90ff; margin-bottom: 20px; text-align: center;">Bản Đồ Tận Thế</h2>
            <div class="map-gallery">
                <div class="map-card active-map" onclick="setWorld(0)"><img src="https://i.pinimg.com/736x/0a/f4/ca/0af4ca7b66c507c1f4024ea7a5fbe0f2.jpg"><div class="map-title">Vực Thẳm</div></div>
                <div class="map-card" onclick="setWorld(1)"><img src="https://i.pinimg.com/736x/fd/c2/25/fdc225f3f7b157339d5c0024fa573c93.jpg"><div class="map-title">Căn Cứ</div></div>
                <div class="map-card" onclick="setWorld(2)"><img src="https://i.pinimg.com/736x/0d/c3/dd/0dc3dd01d63d6314c3e3bfc3588436d0.jpg"><div class="map-title">Bầu Trời</div></div>
                <div class="map-card" onclick="setWorld(3)"><img src="https://i.pinimg.com/736x/ca/83/6e/ca836e317abadc28b2fbb0cb1d34df1e.jpg"><div class="map-title">Trạm Quan Sát</div></div>
            </div>
            <div class="desc-panel">
                <div class="desc-content active-desc" id="d-0"><h3>Vực Thẳm (The Abyss)</h3><p>Nơi bắt nguồn của An Chiết. Một hệ sinh thái kỳ ảo và tàn khốc, nơi sự sống sinh ra từ sự đột biến gen mạnh nhất của mẹ thiên nhiên.</p></div>
                <div class="desc-content" id="d-1"><h3>Căn Cứ Phương Bắc</h3><p>Pháo đài thép của loài người. Nơi quy tắc và luật thẩm phán trị vì nghiêm ngặt để bảo vệ dòng gen thuần khiết cuối cùng.</p></div>
                <div class="desc-content" id="d-2"><h3>Bầu Trời Cực Quang</h3><p>Vẻ đẹp chết chóc. Những dải màu rực rỡ báo hiệu từ trường Trái Đất đã sụp đổ hoàn toàn.</p></div>
                <div class="desc-content" id="d-3"><h3>Trạm Hải Đăng</h3><p>Biểu tượng ý chí nhân loại. Nơi các nhà khoa học miệt mài chiến đấu để khôi phục lại "hành lang từ trường".</p></div>
            </div>
        </div>
    </section>

    <section id="chars" class="page">
        <h2 style="font-family: 'Playfair Display'; font-size: 2rem; color: #1e90ff; margin-bottom: 5px;">Hồ Sơ Nhân Vật</h2>
        <div class="char-scroll">
            <div class="char-card">
                <img src="https://i.pinimg.com/originals/5a/33/7b/5a337b833c149eab621a3f79066ee75c.jpg" class="char-img">
                <p class="char-job">Dị chủng / Cây nấm</p>
                <h3>An Chiết</h3>
                <p style="font-size: 0.8rem; opacity: 0.8;">Cây nấm nhỏ hóa người để đi tìm bào tử, mang trái tim thiện lương giữa tận thế.</p>
                <p class="char-quote">"Tôi chỉ là một cây nấm thôi."</p>
            </div>
            <div class="char-card">
                <img src="https://i.pinimg.com/1200x/bc/fe/cf/bcfecf3d0a7e80aa1cadfab26ca80ac8.jpg" class="char-img">
                <p class="char-job">Thẩm Phán Giả</p>
                <h3>Lục Phong</h3>
                <p style="font-size: 0.8rem; opacity: 0.8;">Thượng tá lạnh lùng, bảo vệ loài người bằng đôi bàn tay nhuốm máu dị chủng.</p>
                <p class="char-quote">"Tôi có tội với nhân loại, nhưng không hổ thẹn."</p>
            </div>
            <div class="char-card">
                <img src="https://i.pinimg.com/736x/d7/15/ef/d715ef5005a24bb7177dafbf819b1ee7.jpg" class="char-img">
                <p class="char-job">Tiến sĩ / Vườn Eden</p>
                <h3>Polly</h3>
                <p style="font-size: 0.8rem; opacity: 0.8;">Nhà khoa học lỗi lạc tìm kiếm lối thoát cho gen của con người.</p>
                <p class="char-quote">"Hy vọng luôn nảy mầm từ tuyệt vọng."</p>
             </div>
            <div class="char-card">
                <img src="https://i.pinimg.com/736x/e2/46/be/e246be2cb1390ec05c6a7a56376d96a0.jpg" class="char-img">
                <p class="char-job">Lính đánh thuê</p>
                <h3>Colin</h3>
                <p style="font-size: 0.8rem; opacity: 0.8;">Hiện thân của những con người bình thường trong thời tận thế: thô lỗ, thực dụng nhưng bản chất rất tốt bụng và trân trọng những điều tốt đẹp.</p>
                <p class="char-quote">"Ở đây, đừng bao giờ tin người khác."</p>   
            </div>
            <div class="char-card">
                <img src="https://i.pinimg.com/736x/44/20/c9/4420c92b583604843045ce278c323105.jpg" class="char-img">
                <p class="char-job">Con người</p>
                <h3>An Trạch</h3>
                <p style="font-size: 0.8rem; opacity: 0.8;">Người hiến gen, người đã cho An Chiết hình hài và tình người đầu tiên.</p>
                <p class="char-quote">"Cảm ơn em đã đi cùng anh."</p>
            </div>
        </div>
        <p style="margin-top: 5px; font-size: 0.75rem; color: #a29bfe;">Dùng thanh trượt ở trên hoặc giữ phím Shift + cuộn chuột để xem hết</p>
    </section>

    <section id="story" class="page">
        <div class="story-box">
            <h2 style="font-family: 'Playfair Display'; color: #1e90ff; text-align: center; margin-bottom: 20px;">Hành Trình Bào Tử</h2>
            <div class="story-text">
                <p>Năm 2020, từ trường Trái Đất sụp đổ, đẩy nhân loại vào thời đại đen tối của sự đột biến gen. Giữa Vực Thẳm chết chóc, một cây nấm nhỏ đã hấp thụ gen của một con người để hóa hình thành <b>An Chiết</b>.</p>
                <p style="margin-top:15px">Hành trình bắt đầu khi An Chiết tiến về Căn cứ Phương Bắc để tìm lại bào tử bị mất. Tại đây, cậu gặp <b>Lục Phong</b> - vị Thẩm phán giả nắm giữ quyền sinh sát. Giữa sự tàn khốc của tận thế, một tình yêu dịu dàng nảy nở, đặt ra câu hỏi về ý nghĩa thực sự của "con người".</p>
                <p style="margin-top:15px">Câu chuyện là một bản thánh ca về sự tồn tại, nơi mỗi sinh mệnh đều đấu tranh để giữ lại bản ngã dưới bầu trời cực quang vĩnh cửu. "Hóa ra ngày cuối cùng của nhân loại lại dịu dàng đến thế."</p>
            </div>
        </div>
    </section>

    <script>
        const fxLayer = document.getElementById('fx-layer');
        for(let i=0; i<200; i++){
            let s = document.createElement('div'); s.className='star';
            s.style.width=s.style.height=Math.random()*2+1+'px';
            s.style.top=Math.random()*100+'%'; s.style.left=Math.random()*100+'%';
            s.style.setProperty('--d', Math.random()*3+2+'s'); fxLayer.appendChild(s);
        }
        for(let i=0; i<50; i++){
            let m = document.createElement('div'); m.className='graphic-mushroom';
            let size = Math.random()*10+5+'px'; m.style.width=size; m.style.height=size;
            m.style.left=Math.random()*100+'%'; 
            m.style.setProperty('--d', Math.random()*10+5+'s');
            m.style.animationDelay = Math.random()*10+'s';
            fxLayer.appendChild(m);
        }
        setInterval(()=>{
            let c = document.createElement('div'); c.className='comet';
            c.style.top = Math.random()*40+'%'; fxLayer.appendChild(c);
            setTimeout(()=>c.remove(), 3000);
        }, 4500);

        function setWorld(index) {
            document.querySelectorAll('.map-card').forEach((c, i) => c.classList.toggle('active-map', i === index));
            document.querySelectorAll('.desc-content').forEach((d, i) => d.classList.toggle('active-desc', i === index));
        }

        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
        }
    </script>
</body>
</html>

<style>
  .spore { position: fixed; bottom: -10px; border-radius: 50%; pointer-events: none; animation: floatUp var(--d) infinite linear; filter: blur(2px); opacity: 0; z-index: 999; }
  @keyframes floatUp { 0% { transform: translateY(0); opacity: 0; } 20% { opacity: 0.6; } 100% { transform: translateY(-110vh); opacity: 0; } }
</style>

<script>
  setInterval(() => {
    const s = document.createElement('div');
    s.className = 'spore';
    const size = Math.random() * 4 + 2 + 'px';
    s.style.cssText = `width:${size}; height:${size}; left:${Math.random()*100}vw; background:${['#d8b4fe','#fff'][Math.round(Math.random())]}; --d:${Math.random()*5+10}s;`;
    document.body.appendChild(s);
    setTimeout(() => s.remove(), 15000);
  }, 300);
</script>

<style>
  /* Hiệu ứng lấp lánh theo chuột */
  .mouse-trail {
    position: fixed;
    width: 6px;
    height: 6px;
    background: #d8b4fe; /* Màu tím nhạt */
    border-radius: 50%;
    pointer-events: none;
    z-index: 9999;
    animation: fadeTrail 0.8s ease-out forwards;
    box-shadow: 0 0 8px #a29bfe;
  }

  @keyframes fadeTrail {
    0% { transform: scale(1); opacity: 1; }
    100% { transform: scale(2.5); opacity: 0; filter: blur(2px); }
  }
</style>

<script>
  // Lắng nghe sự kiện di chuyển chuột
  document.addEventListener('mousemove', function(e) {
    const trail = document.createElement('div');
    trail.className = 'mouse-trail';
    
    // Đặt vị trí đốm sáng ngay tại con trỏ chuột
    trail.style.left = e.clientX + 'px';
    trail.style.top = e.clientY + 'px';
    
    // Ngẫu nhiên màu trắng hoặc tím cho đa dạng
    const colors = ['#d8b4fe', '#ffffff', '#a29bfe', '#c4b5fd'];
    trail.style.background = colors[Math.floor(Math.random() * colors.length)];
    
    document.body.appendChild(trail);
    
    // Xóa dấu vết sau 0.8 giây để nhẹ máy
    setTimeout(() => {
      trail.remove();
    }, 800);
  });
</script>

<audio id="bgMusic" loop>
  <source src="https://www.bensound.com/bensound-music/bensound-slowmotion.mp3" type="audio/mpeg">
  </audio>

<div id="music-btn" onclick="toggleMusic()">
  <span id="music-icon">🎵</span>
</div>

<style>
  /* Style cho cái nút nhạc lơ lửng */
  #music-btn {
    position: fixed;
    bottom: 20px;
    right: 20px;
    width: 50px;
    height: 50px;
    background: rgba(162, 155, 254, 0.3);
    border: 1px solid #d8b4fe;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    z-index: 10000;
    backdrop-filter: blur(5px);
    transition: 0.3s;
    box-shadow: 0 0 10px rgba(162, 155, 254, 0.5);
  }

  #music-btn:hover {
    transform: scale(1.1);
    background: rgba(162, 155, 254, 0.5);
    box-shadow: 0 0 20px #d8b4fe;
  }

  /* Hiệu ứng xoay khi đang phát nhạc */
  .playing {
    animation: rotateMusic 3s linear infinite;
  }

  @keyframes rotateMusic {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }
</style>

<script>
  function toggleMusic() {
    const music = document.getElementById('bgMusic');
    const btn = document.getElementById('music-btn');
    const icon = document.getElementById('music-icon');

    if (music.paused) {
      music.play();
      btn.classList.add('playing');
      icon.innerText = '⏸️';
    } else {
      music.pause();
      btn.classList.remove('playing');
      icon.innerText = '🎵';
    }
  }
</script>

<div style="
    display: block !important;
    text-align: center !important; 
    padding: 30px 0 !important; 
    color: #888 !important; /* Màu xám trung tính, nền nào cũng thấy */
    font-size: 13px !important; 
    font-family: sans-serif !important;
    opacity: 0.5; /* Độ mờ nhạt nhạt */
    clear: both !important;
    border-top: 1px solid rgba(128,128,128,0.1); /* Một đường kẻ siêu mờ để phân cách */
    margin-top: 20px;">
    Copyright © 2026 littlemushroomfandom
</div>
</body>

</html>

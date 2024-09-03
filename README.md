<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Momen's account</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #1e1b1b;
            text-align: center;
            overflow: hidden;
        }

        .profile-container {
            position: relative;
            display: inline-block;
            background-color: #b8c7d1;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            padding: 20px;
            max-width: 600px;
            width: 100%;
            z-index: 1;
        }

        .profile-pic {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            overflow: hidden;
            box-shadow: 0 0 0 8px #090082;
            transition: transform 0.3s, box-shadow 0.3s;
            margin: 0 auto;
            cursor: pointer;
        }

        .profile-pic img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .profile-pic:hover {
            transform: scale(1.05);
            box-shadow: 0 0 0 10px #020202;
        }

        .name {
            font-size: 28px;
            font-weight: bold;
            color: #000000;
            margin: 10px 0;
        }

        .info {
            font-size: 18px;
            color: #555;
            margin-bottom: 20px;
        }

        .initial-scale {
            font-size: 18px;
            color: #555;
            margin-bottom: 20px;
        }

        .social-section {
            background: linear-gradient(135deg, #21118d, #92b01b);
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .social-title {
            font-size: 22px;
            font-weight: bold;
            color: #000000;
            margin-bottom: 15px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            max-width: 100%;
        }

        .social-links a {
            text-decoration: none;
            color: #000000;
            text-align: center;
            transition: transform 0.3s, opacity 0.3s;
        }

        .social-links a:hover {
            transform: scale(1.1);
            opacity: 0.8;
        }

        .social-links img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            margin-bottom: 5px;
        }

        .social-links .icon-text {
            display: block;
            font-size: 14px;
            color: #333;
        }

        /* تراكب الصورة المكبرة */
        .overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .overlay img {
            max-width: 90%;
            max-height: 90%;
            object-fit: contain;
            border-radius: 10px;
        }

        /* لون النص العنوان */
        .profile-title {
            font-size: 32px;
            font-weight: bold;
            color: #ffffff; /* تغيير لون النص إلى الأبيض */
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="profile-title">simple personal profile</div> <!-- تغيير العنوان -->

    <div class="profile-container">
        <div class="profile-pic" id="profilePic">
            <img src="img/WhatsApp Image 2024-09-03 at 20.30.08_2cb95bae.jpg" alt="صورتي الشخصية">
        </div>
        <p>
            <p>
                
            </p>
        </p>
        <div class="name">My name is : 𝑀𝑜𝓂𝑒𝓃 𝒮𝒶𝓁𝓂𝒶𝓃</div>
        <div class="info">𝙄 𝙎𝙏𝙐𝘿𝙔 : 𝘾𝙊𝙈𝙋𝙐𝙏𝙀𝙍 𝙀𝙉𝙂𝙄𝙉𝙀𝙀𝙍𝙄𝙉𝙂 (هندسة الحاسوب)</div>
        <div class="initial-scale">I live in : the Red Sea (Hurghada).</div>

        <!-- قسم حساباتي الخاصة -->
        <div class="social-section">
            <div class="social-title">My private accounts</div>
            <div class="social-links">
                <a href="https://www.facebook.com/profile.php?id=100016023308962&mibextid=LQQJ4d" target="_blank">
                    <img src="img/download.png" alt="فيسبوك">
                    <span class="icon-text">Facebook</span>
                </a>
                <a href="https://api.whatsapp.com/send/?phone=201060782406&text&type=phone_number&app_absent=0" target="_blank">
                    <img src="img/download.jpeg" alt="واتساب">
                    <span class="icon-text">WhatsApp</span>
                </a>
                <a href="https://www.instagram.com/eng_momen_hassan?igsh=MXh4aG4zbXlvMnVscA%3D%3D&utm_source=qr" target="_blank">
                    <img src="img/download (1).jpeg" alt="إنستجرام">
                    <span class="icon-text">Instagram</span>
                </a>
                <!-- إضافة حساب تيكتوك -->
                <a href="https://www.tiktok.com/@eng_momen1?_t=8pQ3rgImPR4&_r=1" target="_blank">
                    <img src="img/download (2).png" alt="تيكتوك">
                    <span class="icon-text">TikTok</span>
                </a>
            </div>
        </div>
    </div>

    <!-- تراكب الصورة المكبرة -->
    <div class="overlay" id="overlay">
        <img id="overlayImage" src="" alt="تكبير الصورة">
    </div>

    <script>
        // الحصول على عناصر DOM
        const profilePic = document.getElementById('profilePic');
        const overlay = document.getElementById('overlay');
        const overlayImage = document.getElementById('overlayImage');
        
        // عرض الصورة المكبرة عند الضغط
        profilePic.addEventListener('click', function() {
            overlay.style.display = 'flex';
            overlayImage.src = profilePic.querySelector('img').src;
        });

        // إخفاء الصورة المكبرة عند الضغط على التراكب
        overlay.addEventListener('click', function() {
            overlay.style.display = 'none';
        });
    </script>
</body>
</html>

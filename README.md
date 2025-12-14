# My-location-
موقع او مود خاص بأدوات مجانية 
pro<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أدواتي - منصة الأدوات المجانية</title>
    <script src="https://cdn.jsdelivr.net/npm/qrcode@1.5.3/build/qrcode.min.js"></script>
    <style>
        :root {
            --primary: #4361ee;
            --secondary: #3a0ca3;
            --accent: #7209b7;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4cc9f0;
            --warning: #f48c06;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fb;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-left: 10px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-right: 20px;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 5px 10px;
            border-radius: 4px;
        }
        
        nav ul li a:hover {
            background-color: rgba(255,255,255,0.2);
        }
        
        /* Hero Section */
        .hero {
            padding: 4rem 0;
            text-align: center;
            background: linear-gradient(rgba(255,255,255,0.9), rgba(255,255,255,0.9));
            background-size: cover;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--secondary);
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            color: #555;
        }
        
        /* Tools Grid */
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
            padding: 2rem 0;
        }
        
        .tool-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }
        
        .tool-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        
        .tool-icon {
            height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }
        
        .qr-icon {
            background: linear-gradient(135deg, #4cc9f0, #4361ee);
        }
        
        .faq-icon {
            background: linear-gradient(135deg, #f72585, #7209b7);
        }
        
        .osint-icon {
            background: linear-gradient(135deg, #38b000, #2d7d46);
        }
        
        .password-icon {
            background: linear-gradient(135deg, #f48c06, #dc2f02);
        }
        
        .support-icon {
            background: linear-gradient(135deg, #6a4c93, #3a0ca3);
        }
        
        .tool-content {
            padding: 1.5rem;
        }
        
        .tool-content h3 {
            margin-bottom: 0.5rem;
            color: var(--dark);
        }
        
        .tool-content p {
            color: #666;
            font-size: 0.95rem;
        }
        
        /* Tool Pages */
        .tool-page {
            display: none;
            padding: 2rem 0;
            min-height: 60vh;
        }
        
        .active {
            display: block;
        }
        
        .page-header {
            margin-bottom: 2rem;
            text-align: center;
        }
        
        .page-header h2 {
            color: var(--secondary);
            font-size: 2rem;
            margin-bottom: 0.5rem;
        }
        
        .page-header p {
            color: #666;
            max-width: 700px;
            margin: 0 auto;
        }
        
        .back-btn {
            background: #e9ecef;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
            transition: background 0.3s;
        }
        
        .back-btn:hover {
            background: #dee2e6;
        }
        
        /* Tool Specific Styles */
        .tool-container {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            max-width: 800px;
            margin: 0 auto;
        }
        
        .input-group {
            margin-bottom: 1.5rem;
        }
        
        .input-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .input-group input, .input-group textarea, .input-group select {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border 0.3s;
        }
        
        .input-group input:focus, .input-group textarea:focus, .input-group select:focus {
            border-color: var(--primary);
            outline: none;
        }
        
        .btn {
            background: var(--primary);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 500;
            transition: background 0.3s;
        }
        
        .btn:hover {
            background: var(--secondary);
        }
        
        .btn-block {
            display: block;
            width: 100%;
        }
        
        /* QR Code Generator */
        #qrcode {
            margin: 1.5rem auto;
            text-align: center;
            display: none;
        }
        
        #qrcode canvas {
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 10px;
            background: white;
        }
        
        /* Password Generator */
        .password-options {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 1.5rem;
        }
        
        .option-group {
            display: flex;
            align-items: center;
        }
        
        .option-group input[type="checkbox"] {
            width: auto;
            margin-left: 10px;
        }
        
        .password-result {
            display: flex;
            margin-top: 1.5rem;
        }
        
        .password-result input {
            flex: 1;
            border-top-right-radius: 0;
            border-bottom-right-radius: 0;
        }
        
        .copy-btn {
            background: var(--accent);
            color: white;
            border: none;
            padding: 0 15px;
            border-top-right-radius: 5px;
            border-bottom-right-radius: 5px;
            cursor: pointer;
        }
        
        /* OSINT Tools */
        .osint-tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 20px;
            margin-top: 2rem;
        }
        
        .osint-tool {
            background: white;
            border-radius: 10px;
            padding: 1.5rem;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
            border: 1px solid #e9ecef;
        }
        
        .osint-tool h3 {
            color: var(--secondary);
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid #f0f0f0;
        }
        
        .result-box {
            background: #f8f9fa;
            border: 1px solid #dee2e6;
            border-radius: 5px;
            padding: 15px;
            margin-top: 1rem;
            min-height: 100px;
            max-height: 300px;
            overflow-y: auto;
            white-space: pre-wrap;
            font-family: monospace;
            font-size: 0.9rem;
        }
        
        .dork-list {
            list-style: none;
            margin-top: 10px;
        }
        
        .dork-list li {
            padding: 8px;
            margin-bottom: 5px;
            background: #e9ecef;
            border-radius: 4px;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .dork-list li:hover {
            background: #dee2e6;
        }
        
        /* FAQ Section */
        .faq-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .faq-category {
            margin-bottom: 2rem;
        }
        
        .faq-category h3 {
            color: var(--secondary);
            padding-bottom: 0.5rem;
            border-bottom: 2px solid #eee;
            margin-bottom: 1rem;
        }
        
        .faq-item {
            margin-bottom: 1rem;
            border: 1px solid #eee;
            border-radius: 5px;
            overflow: hidden;
        }
        
        .faq-question {
            padding: 1rem;
            background: #f8f9fa;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 500;
        }
        
        .faq-answer {
            padding: 0 1rem;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease, padding 0.3s ease;
        }
        
        .faq-item.active .faq-answer {
            padding: 1rem;
            max-height: 500px;
        }
        
        /* Contact Page Styles */
        .contact-methods {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .contact-card {
            background: white;
            border-radius: 10px;
            padding: 1.5rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s ease;
        }
        
        .contact-card:hover {
            transform: translateY(-5px);
        }
        
        .contact-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .telegram-icon {
            color: #0088cc;
        }
        
        .whatsapp-icon {
            color: #25D366;
        }
        
        .email-icon {
            color: #EA4335;
        }
        
        .contact-link {
            display: inline-block;
            margin-top: 1rem;
            padding: 8px 20px;
            background: var(--primary);
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: background 0.3s;
        }
        
        .contact-link:hover {
            background: var(--secondary);
        }
        
        .contact-info {
            margin-top: 1rem;
            color: #666;
        }
        
        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 3rem 0 1.5rem;
            margin-top: 3rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-section h3 {
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .footer-section ul {
            list-style: none;
        }
        
        .footer-section ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-section ul li a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-section ul li a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid #444;
            color: #aaa;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            .logo {
                margin-bottom: 1rem;
            }
            
            nav ul {
                justify-content: center;
                flex-wrap: wrap;
            }
            
            nav ul li {
                margin: 0 10px 10px;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .tools-grid {
                grid-template-columns: 1fr;
            }
            
            .osint-tools-grid {
                grid-template-columns: 1fr;
            }
            
            .contact-methods {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i>🛠️</i>
                    <span>أدواتي
                    ،Ameer</span>
                </div>
                <nav>
                    <ul>
                        <li><a href="#" class="nav-link" data-page="home">الرئيسية</a></li>
                        <li><a href="#" class="nav-link" data-page="support">التواصل معنا</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Home Page -->
    <section id="home-page" class="tool-page active">
        <div class="hero">
            <div class="container">
                <h1>منصة الأدوات المجانية على الإنترنت</h1>
                <p>استخدم أداتنا المجانية لإنشاء رموز QR، أدوات OSINT، توليد كلمات مرور قوية، وأكثر من ذلك</p>
            </div>
        </div>
        
        <div class="container">
            <div class="tools-grid">
                <!-- QR Code Generator -->
                <div class="tool-card" data-tool="qr">
                    <div class="tool-icon qr-icon">
                        🟢
                    </div>
                    <div class="tool-content">
                        <h3>مولد QR Code</h3>
                        <p>حول النصوص والروابط إلى رموز QR قابلة للمسح بسهولة</p>
                    </div>
                </div>
                
                <!-- FAQ -->
                <div class="tool-card" data-tool="faq">
                    <div class="tool-icon faq-icon">
                        ❓
                    </div>
                    <div class="tool-content">
                        <h3>الأسئلة الشائعة</h3>
                        <p>إجابات على أسئلة متكررة في الفيزياء ولغات البرمجة</p>
                    </div>
                </div>
                
                <!-- OSINT Tools -->
                <div class="tool-card" data-tool="osint">
                    <div class="tool-icon osint-icon">
                        🔍
                    </div>
                    <div class="tool-content">
                        <h3>أدوات OSINT</h3>
                        <p>أدوات الاستخبارات المفتوحة المصدر للبحث والتحليل</p>
                    </div>
                </div>
                
                <!-- Password Generator -->
                <div class="tool-card" data-tool="password">
                    <div class="tool-icon password-icon">
                        🔐
                    </div>
                    <div class="tool-content">
                        <h3>مولد كلمات المرور</h3>
                        <p>أنشئ كلمات مرور قوية وآمنة لحساباتك على الإنترنت</p>
                    </div>
                </div>
                
                <!-- Customer Support -->
                <div class="tool-card" data-tool="support">
                    <div class="tool-icon support-icon">
                        💬
                    </div>
                    <div class="tool-content">
                        <h3>التواصل معنا</h3>
                        <p>تواصل معنا عبر تليجرام، واتساب أو البريد الإلكتروني</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- QR Code Generator Page -->
    <section id="qr-page" class="tool-page">
        <div class="container">
            <button class="back-btn" onclick="showPage('home')">← العودة للرئيسية</button>
            <div class="page-header">
                <h2>مولد QR Code</h2>
                <p>حول النص أو الرابط إلى رمز QR يمكن استخدامه في الإعلانات والمواقع والتطبيقات</p>
            </div>
            
            <div class="tool-container">
                <div class="input-group">
                    <label for="qr-text">أدخل النص أو الرابط</label>
                    <textarea id="qr-text" rows="3" placeholder="https://example.com أو أي نص تريد تحويله"></textarea>
                </div>
                
                <button id="generate-qr" class="btn btn-block">إنشاء QR Code</button>
                
                <div id="qrcode"></div>
                
                <div id="download-section" style="display: none; text-align: center; margin-top: 1.5rem;">
                    <button id="download-qr" class="btn">تحميل QR Code</button>
                </div>
            </div>
        </div>
    </section>

    <!-- FAQ Page -->
    <section id="faq-page" class="tool-page">
        <div class="container">
            <button class="back-btn" onclick="showPage('home')">← العودة للرئيسية</button>
            <div class="page-header">
                <h2>الأسئلة الشائعة</h2>
                <p>إجابات على الأسئلة المتكررة في مجالي الفيزياء ولغات البرمجة</p>
            </div>
            
            <div class="faq-container">
                <!-- Physics FAQs -->
                <div class="faq-category">
                    <h3>أسئلة في الفيزياء</h3>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هي النظرية النسبية لأينشتاين؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            النظرية النسبية هي نظرية فيزيائية طرحها ألبرت أينشتاين، وتنقسم إلى قسمين: النسبية الخاصة (1905) التي تناولت الزمان والمكان وسرعة الضوء، والنسبية العامة (1915) التي تناولت الجاذبية كخاصية هندسية في الزمكان.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما الفرق بين الكتلة والوزن؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            الكتلة هي كمية المادة في الجسم وتقاس بالكيلوجرام، وهي ثابتة لا تتغير. أما الوزن فهو قوة جذب الأرض للجسم ويقاس بالنيوتن، ويتغير بتغير قوة الجاذبية.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هي ميكانيكا الكم؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            ميكانيكا الكم هي النظرية الفيزيائية التي تدرس سلوك المادة والطاقة على المستوى الذري ودون الذري. تختلف عن الفيزياء الكلاسيكية في أنها تعتمد على مبادئ مثل التراكب الكمي واللايقين.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هو الثقب الأسود؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            الثقب الأسود هو منطقة في الفضاء ذات جاذبية شديدة لدرجة أن لا شيء، ولا حتى الضوء، يمكنه الهروب منها. يتشكل عندما ينهار نجم ضخم في نهاية حياته.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هي الطاقة المظلمة؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            الطاقة المظلمة هي شكل افتراضي من الطاقة التي يعتقد أنها تشكل حوالي 68% من الكون وتسبب تسارع توسع الكون. طبيعتها غير معروفة حتى الآن.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هو مبدأ عدم اليقين لهايزنبرغ؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            مبدأ عدم اليقين ينص على أنه لا يمكن قياس كل من موضع الجسيم وكمية حركته بدقة في نفس الوقت. كلما زادت دقة قياس أحدهما، قلت دقة قياس الآخر.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            كيف يعمل القمر الصناعي؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            الأقمار الصناعية تتحرك في مدارات حول الأرض بسرعة معينة توازن بين قوة الجاذبية والقوة الطاردة المركزية. تستخدم في الاتصالات، الملاحة، والمراقبة.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هي الجسيمات الأولية؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            الجسيمات الأولية هي أصغر مكونات المادة التي لا يمكن تقسيمها إلى جسيمات أصغر. تشمل الكواركات، اللبتونات، والبوزونات مثل بوزون هيغز.
                        </div>
                    </div>
                </div>
                
                <!-- Programming FAQs -->
                <div class="faq-category">
                    <h3>أسئلة في لغات البرمجة</h3>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما الفرق بين JavaScript و Python؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            JavaScript هي لغة برمجة تستخدم principalmente لتطوير الويب (Front-end) ويمكن استخدامها أيضًا في Back-end عبر Node.js. Python هي لغة متعددة الاستخدامات تشتهر في مجالات مثل الذكاء الاصطناعي، تحليل البيانات، والتطوير الخلفي.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هي أفضل لغة برمجة للمبتدئين؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            Python تعتبر من أفضل اللغات للمبتدئين بسبب بساطة تركيبها وقربها من اللغة الإنجليزية. بدائل جيدة تشمل JavaScript إذا كان الاهتمام في تطوير الويب، أو Scratch للصغار والمبتدئين تمامًا.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما الفرق بين Front-end و Back-end开发؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            Front-end development يتعلق بكل ما يراه المستخدم ويتفاعل معه في المتصفح (HTML, CSS, JavaScript). Back-end development يتعلق بالخوادم وقواعد البيانات والمنطق الخفي الذي يعمل خلف الكواليس (مثل Python, Java, PHP).
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هو Git ولماذا نستخدمه؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            Git هو نظام تحكم في النسخ يسمح للمطورين بتتبع التغييرات في الكود المصدري، والعمل التعاوني، واستعادة الإصدارات السابقة. GitHub وGitLab هما منصتان مشهورتان تستخدمان Git.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هي قواعد البيانات SQL وNoSQL؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            قواعد البيانات SQL (مثل MySQL، PostgreSQL) تستخدم جداول علائقية وهيكل مخطط مسبقًا. قواعد البيانات NoSQL (مثل MongoDB، Redis) أكثر مرونة وتستخدم مستندات أو قيم مفتاحية وتكون مناسبة للبيانات غير المهيكلة.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هو الـAPI وكيف يعمل؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            API (واجهة برمجة التطبيقات) هي مجموعة من القواعد تسمح للتطبيقات بالتواصل مع بعضها البعض. تعمل كوسيط بين التطبيقات، مما يسمح بمشاركة البيانات والوظائف.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هو الذكاء الاصطناعي والتعلم الآلي؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            الذكاء الاصطناعي (AI) هو فرع من علوم الحاسوب يهدف لصنع آلات ذكية. التعلم الآلي (ML) هو جزء من الذكاء الاصطناعي يركز على تطوير خوارزميات تتعلم من البيانات وتتخذ قرارات.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هو Docker ولماذا يستخدم؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            Docker هو منصة تسمح بتطوير ونشر التطبيقات داخل حاويات. الحاويات توفر بيئة معزولة ومتسقة للتشغيل، مما يسهل نشر التطبيقات عبر بيئات مختلفة.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            كيف أبدأ تعلم البرمجة؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            ابدأ بلغة بسيطة مثل Python، تعلم الأساسيات أولاً، ثم تدرب على مشاريع صغيرة. استخدم منصات مثل freeCodeCamp، Codecademy، أو كورسات YouTube. الممارسة المستمرة هي المفتاح.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هي أفضل طريقة لتعلم البرمجة؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            أفضل طريقة هي الجمع بين: 1) تعلم النظرية 2) الممارسة العملية 3) بناء المشاريع 4) قراءة كود الآخرين 5) المشاركة في مجتمعات البرمجة. التنوع في المصادر يساعد في الفهم العميق.
                        </div>
                    </div>
                </div>
                
                <!-- OSINT FAQs -->
                <div class="faq-category">
                    <h3>أسئلة في OSINT والأمن السيبراني</h3>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هو OSINT؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            OSINT (الاستخبارات المفتوحة المصدر) هو جمع وتحليل المعلومات من مصادر مفتوحة ومتاحة للعامة مثل الإنترنت، وسائل الإعلام، والمنشورات العامة لأغراض استخباراتية.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            هل أدوات OSINT قانونية؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            نعم، أدوات OSINT قانونية عندما تستخدم لجمع معلومات متاحة للعامة فقط. غير قانوني استخدامها للوصول غير المصرح به، أو انتهاك خصوصية الآخرين، أو جمع معلومات محمية.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            ما هي Google Dorks؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            Google Dorks هي استعلامات بحث متقدمة تستخدم مشغلات بحث خاصة للعثور على معلومات محددة على الإنترنت. تستخدم في اختبار الاختراق الأخلاقي وأبحاث OSINT.
                        </div>
                    </div>
                    
                    <div class="faq-item">
                        <div class="faq-question">
                            كيف أحمي نفسي من OSINT؟
                            <span>+</span>
                        </div>
                        <div class="faq-answer">
                            لحماية نفسك: قلل المعلومات الشخصية على الإنترنت، استخدم إعدادات الخصوصية، تجنب نشر معلومات حساسة، استخدم كلمات مرور قوية، واحذف الحسابات غير المستخدمة.
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- OSINT Tools Page -->
    <section id="osint-page" class="tool-page">
        <div class="container">
            <button class="back-btn" onclick="showPage('home')">← العودة للرئيسية</button>
            <div class="page-header">
                <h2>أدوات OSINT (الاستخبارات المفتوحة المصدر)</h2>
                <p>أدوات بحث وتحليل تعمل بالكامل في المتصفح بدون الحاجة لخادم</p>
            </div>
            
            <div class="tool-container">
                <div class="osint-tools-grid">
                    <!-- Email Analyzer -->
                    <div class="osint-tool">
                        <h3>محلل البريد الإلكتروني</h3>
                        <div class="input-group">
                            <input type="email" id="email-input" placeholder="أدخل البريد الإلكتروني">
                        </div>
                        <button onclick="analyzeEmail()" class="btn">تحليل</button>
                        <div class="result-box" id="email-result"></div>
                    </div>
                    
                    <!-- IP Address Analyzer -->
                    <div class="osint-tool">
                        <h3>محلل عنوان IP</h3>
                        <div class="input-group">
                            <input type="text" id="ip-input" placeholder="أدخل عنوان IP (مثال: 192.168.1.1)">
                        </div>
                        <button onclick="analyzeIP()" class="btn">تحليل</button>
                        <div class="result-box" id="ip-result"></div>
                    </div>
                    
                    <!-- Username Generator -->
                    <div class="osint-tool">
                        <h3>مولد أسماء المستخدمين</h3>
                        <div class="input-group">
                            <input type="text" id="name-input" placeholder="أدخل الاسم">
                        </div>
                        <button onclick="generateUsernames()" class="btn">توليد</button>
                        <div class="result-box" id="username-result"></div>
                    </div>
                    
                    <!-- Google Dorks Generator -->
                    <div class="osint-tool">
                        <h3>مولد Google Dorks</h3>
                        <div class="input-group">
                            <input type="text" id="dork-input" placeholder="الكلمة المفتاحية">
                        </div>
                        <button onclick="generateDorks()" class="btn">توليد</button>
                        <div id="dork-result">
                            <ul class="dork-list" id="dork-list">
                                <!-- Dorks will be inserted here -->
                            </ul>
                        </div>
                    </div>
                    
                    <!-- Password Strength Checker -->
                    <div class="osint-tool">
                        <h3>مدقق قوة كلمة المرور</h3>
                        <div class="input-group">
                            <input type="text" id="check-password" placeholder="أدخل كلمة المرور">
                        </div>
                        <button onclick="checkPasswordStrength()" class="btn">تحليل القوة</button>
                        <div class="result-box" id="password-check-result"></div>
                    </div>
                    
                    <!-- URL Analyzer -->
                    <div class="osint-tool">
                        <h3>محلل الروابط</h3>
                        <div class="input-group">
                            <input type="text" id="url-input" placeholder="أدخل الرابط الكامل">
                            ject</div>
                        <button onclick="analyzeURL()" class="btn">تحليل</button>
                        <div class="result-box" id="url-result"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Password Generator Page -->
    <section id="password-page" class="tool-page">
        <div class="container">
            <button class="back-btn" onclick="showPage('home')">← العودة للرئيسية</button>
            <div class="page-header">
                <h2>مولد كلمات المرور</h2>
                <p>أنشئ كلمات مرور قوية وآمنة لحساباتك على الإنترنت</p>
            </div>
            
            <div class="tool-container">
                <div class="input-group">
                    <label for="password-length">طول كلمة المرور</label>
                    <input type="range" id="password-length" min="8" max="32" value="12">
                    <span id="length-value">12</span> حرف
                </div>
                
                <div class="password-options">
                    <div class="option-group">
                        <input type="checkbox" id="uppercase" checked>
                        <label for="uppercase">أحرف كبيرة (A-Z)</label>
                    </div>
                    <div class="option-group">
                        <input type="checkbox" id="lowercase" checked>
                        <label for="lowercase">أحرف صغيرة (a-z)</label>
                    </div>
                    <div class="option-group">
                        <input type="checkbox" id="numbers" checked>
                        <label for="numbers">أرقام (0-9)</label>
                    </div>
                    <div class="option-group">
                        <input type="checkbox" id="symbols">
                        <label for="symbols">رموز (!@#$%^&*)</label>
                    </div>
                </div>
                
                <button id="generate-password" class="btn btn-block">إنشاء كلمة مرور</button>
                
                <div class="password-result">
                    <input type="text" id="password-result" readonly>
                    <button class="copy-btn" id="copy-password">نسخ</button>
                </div>
                
                <div id="password-strength" style="margin-top: 1rem; text-align: center; font-weight: bold;"></div>
            </div>
        </div>
    </section>

    <!-- Contact Page -->
    <section id="support-page" class="tool-page">
        <div class="container">
            <button class="back-btn" onclick="showPage('home')">← العودة للرئيسية</button>
            <div class="page-header">
                <h2>التواصل معنا</h2>
                <p>تواصل معنا عبر منصات التواصل المختلفة</p>
            </div>
            
            <div class="tool-container">
                <h3 style="text-align: center; margin-bottom: 2rem; color: var(--secondary);">طرق التواصل المتاحة</h3>
                
                <div class="contact-methods">
                    <!-- Telegram -->
                    <div class="contact-card">
                        <div class="contact-icon telegram-icon">
                            📱
                        </div>
                        <h3>تيليجرام</h3>
                        <p>راسلنا على تيليجرام للرد السريع</p>
                        <div class="contact-info">
                            <strong>يوزر التليجرام:</strong><br>
                            @Rtum4
                        </div>
                        <a href="https://t.me/your_telegram_username" target="_blank" class="contact-link">
                            تواصل على تيليجرام
                        </a>
                    </div>
                    
                    <!-- WhatsApp -->
                    <div class="contact-card">
                        <div class="contact-icon whatsapp-icon">
                            💬
                        </div>
                        <h3>واتساب</h3>
                        <p>راسلنا على واتساب للدردشة المباشرة</p>
                        <div class="contact-info">
                            <strong>رقم الواتساب:</strong><br>
                            +07867698480
                        </div>
                        <a href="https://wa.me/1234567890" target="_blank" class="contact-link">
                            تواصل على واتساب
                        </a>
                    </div>
                    
                    <!-- Email -->
                    <div class="contact-card">
                        <div class="contact-icon email-icon">
                            📧
                        </div>
                        <h3>البريد الإلكتروني</h3>
                        <p>أرسل لنا بريدًا إلكترونيًا</p>
                        <div class="contact-info">
                            <strong>البريد الإلكتروني:</strong><br>
                            ameersec53@gmail.com
                        </div>
                        <a href="mailto:your.email@gmail.com" class="contact-link">
                            أرسل بريدًا إلكترونيًا
                        </a>
                    </div>
                </div>
                
                <div style="margin-top: 3rem; padding: 1.5rem; background: #f8f9fa; border-radius: 8px;">
                    <h4 style="color: var(--secondary); margin-bottom: 1rem;">معلومات التواصل</h4>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;">
                        <div>
                            <strong>تيليجرام:</strong>
                            <p>@Rtum4</p>
                        </div>
                        
                        <div>
                            <strong>الواتساب:</strong>
                            <p>07867698480</p>
                        </div>
                        
                        <div style="grid-column: span 2;">
                            <strong>البريد الإلكتروني (جي ميل فقط):</strong>
                            <p>ameersec53@gmail.com</p>
                        </div>
                    </div>
                </div>
                
                <div style="margin-top: 2rem; text-align: center;">
                    <p style="color: #666;">وقت الاستجابة المتوقع: خلال 24 ساعة</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>أدواتي</h3>
                    <p>منصة تقدم مجموعة من الأدوات المجانية المفيدة للمستخدمين العرب.</p>
                </div>
                
                <div class="footer-section">
                    <h3>الأدوات</h3>
                    <ul>
                        <li><a href="#" data-tool="qr">مولد QR Code</a></li>
                        <li><a href="#" data-tool="faq">الأسئلة الشائعة</a></li>
                        <li><a href="#" data-tool="osint">أدوات OSINT</a></li>
                        <li><a href="#" data-tool="password">مولد كلمات المرور</a></li>
                    </ul>
                </div>
                
                <div class="footer-section">
                    <h3>التواصل</h3>
                    <ul>
                        <li><a href="https://t.me/your_telegram_username" target="_blank">تيليجرام</a></li>
                        <li><a href="https://wa.me/1234567890" target="_blank">واتساب</a></li>
                        <li><a href="mailto:your.email@gmail.com">البريد الإلكتروني</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>© 2024 أدواتي. جميع الحقوق محفوظة.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Page Navigation
        function showPage(pageId) {
            document.querySelectorAll('.tool-page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId + '-page').classList.add('active');
        }
        
        // Tool Navigation
        document.querySelectorAll('.tool-card, .footer-section a[data-tool]').forEach(card => {
            card.addEventListener('click', function() {
                const tool = this.getAttribute('data-tool');
                showPage(tool);
            });
        });
        
        // Nav Link Navigation
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const page = this.getAttribute('data-page');
                showPage(page);
            });
        });
        
        // FAQ Toggle
        document.querySelectorAll('.faq-question').forEach(question => {
            question.addEventListener('click', function() {
                const faqItem = this.parentElement;
                faqItem.classList.toggle('active');
                
                const icon = this.querySelector('span');
                icon.textContent = faqItem.classList.contains('active') ? '-' : '+';
            });
        });
        
        // Password Generator
        document.getElementById('password-length').addEventListener('input', function() {
            document.getElementById('length-value').textContent = this.value;
        });
        
        document.getElementById('generate-password').addEventListener('click', function() {
            const length = document.getElementById('password-length').value;
            const uppercase = document.getElementById('uppercase').checked;
            const lowercase = document.getElementById('lowercase').checked;
            const numbers = document.getElementById('numbers').checked;
            const symbols = document.getElementById('symbols').checked;
            
            let charset = '';
            if (uppercase) charset += 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
            if (lowercase) charset += 'abcdefghijklmnopqrstuvwxyz';
            if (numbers) charset += '0123456789';
            if (symbols) charset += '!@#$%^&*()_+-=[]{}|;:,.<>?';
            
            if (charset === '') {
                alert('يرجى اختيار نوع واحد على الأقل من الأحرف!');
                return;
            }
            
            let password = '';
            for (let i = 0; i < length; i++) {
                const randomIndex = Math.floor(Math.random() * charset.length);
                password += charset[randomIndex];
            }
            
            document.getElementById('password-result').value = password;
            
            // Check password strength
            let strength = 'ضعيفة';
            let strengthColor = 'red';
            
            if (length >= 12 && uppercase && lowercase && numbers && symbols) {
                strength = 'قوية جدًا';
                strengthColor = 'green';
            } else if (length >= 10 && uppercase && lowercase && numbers) {
                strength = 'قوية';
                strengthColor = 'blue';
            } else if (length >= 8 && (uppercase || lowercase) && numbers) {
                strength = 'متوسطة';
                strengthColor = 'orange';
            }
            
            const strengthElement = document.getElementById('password-strength');
            strengthElement.textContent = `قوة كلمة المرور: ${strength}`;
            strengthElement.style.color = strengthColor;
        });
        
        // Copy Password
        document.getElementById('copy-password').addEventListener('click', function() {
            const passwordField = document.getElementById('password-result');
            passwordField.select();
            document.execCommand('copy');
            alert('تم نسخ كلمة المرور إلى الحافظة!');
        });
        
        // QR Code Generator
        document.getElementById('generate-qr').addEventListener('click', function() {
            const text = document.getElementById('qr-text').value.trim();
            if (!text) {
                alert('يرجى إدخال نص أو رابط أولاً!');
                return;
            }
            
            const qrCodeDiv = document.getElementById('qrcode');
            qrCodeDiv.innerHTML = '';
            qrCodeDiv.style.display = 'block';
            
            QRCode.toCanvas(qrCodeDiv, text, { width: 200 }, function(error) {
                if (error) {
                    console.error(error);
                    alert('حدث خطأ أثناء إنشاء QR Code');
                    return;
                }
                
                document.getElementById('download-section').style.display = 'block';
            });
        });
        
        // Download QR Code
        document.getElementById('download-qr').addEventListener('click', function() {
            const canvas = document.querySelector('#qrcode canvas');
            if (!canvas) {
                alert('يرجى إنشاء QR Code أولاً!');
                return;
            }
            
            const link = document.createElement('a');
            link.download = 'qrcode.png';
            link.href = canvas.toDataURL('image/png');
            link.click();
        });
        
        // ==========================================
        // OSINT TOOLS FUNCTIONS
        // ==========================================
        
        // Email Analyzer
        function analyzeEmail() {
            const email = document.getElementById('email-input').value.trim();
            if (!email) {
                alert('يرجى إدخال بريد إلكتروني');
                return;
            }
            
            // Basic email analysis
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailRegex.test(email)) {
                document.getElementById('email-result').textContent = '❌ صيغة البريد الإلكتروني غير صحيحة';
                return;
            }
            
            const [localPart, domain] = email.split('@');
            const domainParts = domain.split('.');
            const tld = domainParts[domainParts.length - 1];
            
    
 let result = `✅ تحليل البريد الإلكتروني:\n\n`;
            result += `البريد: ${email}\n`;
            result += `الجزء المحلي: ${localPart}\n`;
            result += `النطاق: ${domain}\n`;
            result += `امتداد النطاق: ${tld}\n`;
            result += `\n🔍 المعلومات:\n`;
            result += `- الطول الإجمالي: ${email.length} حرف\n`;
            result += `- طول الجزء المحلي: ${localPart.length} حرف\n`;
            result += `- عدد الأحرف الخاصة في الاسم: ${(localPart.match(/[^a-zA-Z0-9]/g) || []).length}\n`;
            result += `- هل يحتوي على أرقام: ${/\d/.test(localPart) ? 'نعم' : 'لا'}\n`;
            
            // Check common domains
            const commonDomains = ['gmail.com', 'yahoo.com', 'outlook.com', 'hotmail.com', 'protonmail.com'];
            if (commonDomains.includes(domain.toLowerCase())) {
                result += `\n⚠️ هذا النطاق شائع الاستخدام`;
            }
            
            document.getElementById('email-result').textContent = result;
        }
        
        // IP Address Analyzer
        function analyzeIP() {
            const ip = document.getElementById('ip-input').value.trim();
            if (!ip) {
                alert('يرجى إدخال عنوان IP');
                return;
            }
            
            // IP validation regex
            const ipv4Regex = /^(\d{1,3})\.(\d{1,3})\.(\d{1,3})\.(\d{1,3})$/;
            const match = ip.match(ipv4Regex);
            
            if (!match) {
                document.getElementById('ip-result').textContent = '❌ عنوان IP غير صالح';
                return;
            }
            
            // Check if each octet is between 0-255
            const isValid = match.slice(1).every(octet => {
                const num = parseInt(octet, 10);
                return num >= 0 && num <= 255;
            });
            
            if (!isValid) {
                document.getElementById('ip-result').textContent = '❌ عنوان IP غير صالح';
                return;
            }
            
            let result = `✅ تحليل عنوان IP:\n\n`;
            result += `العنوان: ${ip}\n`;
            
            // Check IP type
            const firstOctet = parseInt(match[1], 10);
            if (ip === '127.0.0.1') {
                result += `النوع: loopback (localhost)\n`;
            } else if (firstOctet === 10) {
                result += `النوع: خاص (Class A private)\n`;
            } else if (firstOctet === 172 && parseInt(match[2], 10) >= 16 && parseInt(match[2], 10) <= 31) {
                result += `النوع: خاص (Class B private)\n`;
            } else if (firstOctet === 192 && parseInt(match[2], 10) === 168) {
                result += `النوع: خاص (Class C private)\n`;
            } else if (firstOctet >= 224 && firstOctet <= 239) {
                result += `النوع: multicast\n`;
            } else if (firstOctet >= 240 && firstOctet <= 255) {
                result += `النوع: reserved\n`;
            } else {
                result += `النوع: عام (public)\n`;
            }
            
            result += `\n🔍 الأوكتتات:\n`;
            match.slice(1).forEach((octet, index) => {
                const num = parseInt(octet, 10);
                result += `الأوكتت ${index + 1}: ${num} (عشري) = ${num.toString(2).padStart(8, '0')} (ثنائي)\n`;
            });
            
            // Check if IP is in reserved ranges
            const isPrivate = ip.startsWith('10.') || 
                             ip.startsWith('172.16.') || 
                             ip.startsWith('172.17.') || 
                             ip.startsWith('172.18.') || 
                             ip.startsWith('172.19.') || 
                             ip.startsWith('172.20.') || 
                             ip.startsWith('172.21.') || 
                             ip.startsWith('172.22.') || 
                             ip.startsWith('172.23.') || 
                             ip.startsWith('172.24.') || 
                             ip.startsWith('172.25.') || 
                             ip.startsWith('172.26.') || 
                             ip.startsWith('172.27.') || 
                             ip.startsWith('172.28.') || 
                             ip.startsWith('172.29.') || 
                             ip.startsWith('172.30.') || 
                             ip.startsWith('172.31.') || 
                             ip.startsWith('192.168.');
            
            if (isPrivate) {
                result += `\n⚠️ هذا عنوان IP خاص (غير قابل للتوجيه على الإنترنت)\n`;
            }
            
            document.getElementById('ip-result').textContent = result;
        }
        
        // Username Generator
        function generateUsernames() {
            const name = document.getElementById('name-input').value.trim();
            if (!name) {
                alert('يرجى إدخال اسم');
                return;
            }
            
            const cleanedName = name.toLowerCase().replace(/[^a-z]/g, '');
            if (cleanedName.length < 2) {
                document.getElementById('username-result').textContent = '❌ الاسم قصير جدًا';
                return;
            }
            
            let usernames = [];
            const currentYear = new Date().getFullYear();
            const randomNum = Math.floor(Math.random() * 1000);
            
            // Generate different username patterns
            usernames.push(`${cleanedName}`);
            usernames.push(`${cleanedName}${randomNum}`);
            usernames.push(`${cleanedName}${currentYear}`);
            usernames.push(`${cleanedName}_${randomNum}`);
            usernames.push(`${cleanedName}.${randomNum}`);
            usernames.push(`the_${cleanedName}`);
            usernames.push(`${cleanedName}${currentYear.toString().slice(2)}`);
            usernames.push(`${cleanedName}${Math.floor(Math.random() * 100)}`);
            usernames.push(`${cleanedName}${Math.floor(Math.random() * 1000)}`);
            usernames.push(`real${cleanedName}`);
            
            // Add some variations with common patterns
            if (cleanedName.length > 3) {
                usernames.push(`${cleanedName.slice(0, 3)}${randomNum}`);
                usernames.push(`${cleanedName}${cleanedName.slice(0, 1)}`);
                usernames.push(`${cleanedName}${cleanedName.slice(-1)}`);
            }
            
            // Remove duplicates and limit to 15
            usernames = [...new Set(usernames)].slice(0, 15);
            
            let result = `🔍 أسماء المستخدمين المقترحة لـ "${name}":\n\n`;
            usernames.forEach((username, index) => {
                result += `${index + 1}. ${username}\n`;
            });
            
            result += `\n📝 نصائح:\n`;
            result += `- تجنب استخدام المعلومات الشخصية الحساسة\n`;
            result += `- استخدم مزيجًا من الأحرف والأرقام\n`;
            result += `- تجنب استخدام نفس اسم المستخدم في كل مكان\n`;
            
            document.getElementById('username-result').textContent = result;
        }
        
        // Google Dorks Generator
        function generateDorks() {
            const keyword = document.getElementById('dork-input').value.trim();
            if (!keyword) {
                alert('يرجى إدخال كلمة مفتاحية');
                return;
            }
            
            const dorks = [
                `site:${keyword}`,
                `inurl:${keyword}`,
                `intitle:"${keyword}"`,
                `filetype:pdf "${keyword}"`,
                `"${keyword}" site:gov`,
                `"${keyword}" site:edu`,
                `"${keyword}" filetype:doc OR filetype:docx`,
                `"${keyword}" filetype:xls OR filetype:xlsx`,
                `"${keyword}" filetype:ppt OR filetype:pptx`,
                `"${keyword}" filetype:txt`,
                `"${keyword}" -site:facebook.com -site:twitter.com`,
                `"${keyword}" intext:"password" OR intext:"username"`,
                `"${keyword}" "index of /"`,
                `"${keyword}" "login" OR "admin"`,
                `"${keyword}" "contact" OR "about"`,
                `"${keyword}" "confidential" OR "private"`,
                `"${keyword}" "report" OR "analysis"`,
                `"${keyword}" "draft" OR "preliminary"`,
                `"${keyword}" "backup" OR "archive"`,
                `"${keyword}" "database" OR "dump"`,
            ];
            
            const dorkList = document.getElementById('dork-list');
            dorkList.innerHTML = '';
            
            dorks.forEach(dork => {
                const li = document.createElement('li');
                li.textContent = dork;
                li.onclick = function() {
                    const url = `https://www.google.com/search?q=${encodeURIComponent(dork)}`;
                    window.open(url, '_blank');
                };
                dorkList.appendChild(li);
            });
        }
        
        // Password Strength Checker
        function checkPasswordStrength() {
            const password = document.getElementById('check-password').value;
            
            if (!password) {
                document.getElementById('password-check-result').textContent = '❌ يرجى إدخال كلمة المرور';
                return;
            }
            
            let score = 0;
            let feedback = [];
            
            // Length check
            if (password.length >= 12) score += 3;
            else if (password.length >= 8) score += 2;
            else if (password.length >= 6) score += 1;
            else feedback.push('⚠️ كلمة المرور قصيرة جدًا (أقل من 6 أحرف)');
            
            // Lowercase letters
            if (/[a-z]/.test(password)) score += 1;
            else feedback.push('⚠️ إضافة أحرف صغيرة (a-z)');
            
            // Uppercase letters
            if (/[A-Z]/.test(password)) score += 1;
            else feedback.push('⚠️ إضافة أحرف كبيرة (A-Z)');
            
            // Numbers
            if (/\d/.test(password)) score += 1;
            else feedback.push('⚠️ إضافة أرقام (0-9)');
            
            // Special characters
            if (/[^a-zA-Z0-9]/.test(password)) score += 2;
            else feedback.push('⚠️ إضافة رموز خاصة (!@#$%...)');
            
            // Common patterns check
            const commonPatterns = ['123456', 'password', 'qwerty', 'admin', 'welcome', '123456789'];
            if (commonPatterns.includes(password.toLowerCase())) {
                score = 0;
                feedback = ['❌ كلمة المرور شائعة جدًا وسهلة الاختراق'];
            }
            
            // Sequential characters check
            const sequentialRegex = /(abc|bcd|cde|def|efg|fgh|ghi|hij|ijk|jkl|klm|lmn|mno|nop|opq|pqr|qrs|rst|stu|tuv|uvw|vwx|wxy|xyz|012|123|234|345|456|567|678|789)/i;
            if (sequentialRegex.test(password)) {
                score -= 1;
                feedback.push('⚠️ تجنب التسلسلات المتتابعة');
            }
            
            // Calculate strength level
            let strength, strengthColor;
            if (score >= 8) {
                strength = 'قوية جدًا';
                strengthColor = '#38b000';
            } else if (score >= 6) {
                strength = 'قوية';
                strengthColor = '#4cc9f0';
            } else if (score >= 4) {
                strength = 'متوسطة';
                strengthColor = '#f48c06';
            } else {
                strength = 'ضعيفة';
                strengthColor = '#dc2f02';
            }
            
            let result = `🔐 تحليل قوة كلمة المرور:\n\n`;
            result += `الطول: ${password.length} حرف\n`;
            result += `النتيجة: ${score}/10\n`;
            result += `القوة: ${strength}\n`;
            result += `وقت الاختراق التقريبي: `;
            
            // Estimate cracking time
            if (score >= 8) result += 'قرون\n';
            else if (score >= 6) result += 'سنوات\n';
            else if (score >= 4) result += 'أشهر\n';
            else result += 'ثوانٍ إلى دقائق\n';
            
            if (feedback.length > 0) {
                result += `\n💡 اقتراحات للتحسين:\n`;
                feedback.forEach(item => {
                    result += `${item}\n`;
                });
            }
            
            const resultBox = document.getElementById('password-check-result');
            resultBox.textContent = result;
            resultBox.style.borderLeft = `5px solid ${strengthColor}`;
        }
        
        // URL Analyzer
        function analyzeURL() {
            const url = document.getElementById('url-input').value.trim();
            if (!url) {
                alert('يرجى إدخال رابط');
                return;
            }
            
            try {
                // Try to parse the URL
                const urlObj = new URL(url.includes('://') ? url : `http://${url}`);
                
                let result = `🔗 تحليل الرابط:\n\n`;
                result += `الرابط الكامل: ${urlObj.href}\n`;
                result += `النطاق: ${urlObj.hostname}\n`;
                result += `المسار: ${urlObj.pathname}\n`;
                result += `البروتوكول: ${urlObj.protocol}\n`;
                
                if (urlObj.port) {
                    result += `المنفذ: ${urlObj.port}\n`;
                }
                
                if (urlObj.search) {
                    result += `معاملات البحث: ${urlObj.search}\n`;
                    const params = urlObj.searchParams;
                    if (params.toString()) {
                        result += `المعلمات:\n`;
                        params.forEach((value, key) => {
                            result += `  ${key} = ${value}\n`;
                        });
                    }
                }
                
                if (urlObj.hash) {
                    result += `الجزء المقطع: ${urlObj.hash}\n`;
                }
                
                // Check for suspicious patterns
                const suspiciousPatterns = [
                    { pattern: /login|signin|auth/i, desc: 'صفحة تسجيل دخول' },
                    { pattern: /admin|dashboard|control/i, desc: 'لوحة تحكم' },
                    { pattern: /php|asp|jsp|cgi/i, desc: 'لغة برمجة خلفية' },
                    { pattern: /\.exe|\.zip|\.rar|\.7z/i, desc: 'ملف قابل للتنزيل' },
                    { pattern: /redirect|goto|url=/i, desc: 'إعادة توجيه' },
                    { pattern: /%[0-9a-f]{2}/i, desc: 'ترميز URL' },
                ];
                
                const foundPatterns = suspiciousPatterns.filter(p => p.pattern.test(url));
                if (foundPatterns.length > 0) {
                    result += `\n⚠️ ملاحظات:\n`;
                    foundPatterns.forEach(p => {
                        result += `- ${p.desc}\n`;
                    });
                }
                
                // Check if HTTPS
                if (urlObj.protocol === 'https:') {
                    result += `\n✅ يستخدم اتصال آمن (HTTPS)\n`;
                } else if (urlObj.protocol === 'http:') {
                    result += `\n⚠️ يستخدم اتصال غير آمن (HTTP)\n`;
                }
                
                document.getElementById('url-result').textContent = result;
                
            } catch (error) {
                document.getElementById('url-result').textContent = '❌ رابط غير صالح. مثال صحيح: https://example.com/path';
            }
        }
        
        // Initialize Google Dorks on page load
        window.addEventListener('DOMContentLoaded', function() {
            generateDorks();
        });
    </script>
</body>
</html>
```

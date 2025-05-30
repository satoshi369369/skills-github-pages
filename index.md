<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sound Souls ポータル開放会</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Noto Sans JP', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.8;
            color: #333;
            overflow-x: hidden;
        }
        
        .hero-section {
            min-height: 100vh;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><radialGradient id="g" cx="50%" cy="50%" r="50%"><stop offset="0%" stop-color="rgba(255,255,255,0.1)"/><stop offset="100%" stop-color="rgba(255,255,255,0)"/></radialGradient></defs><circle cx="20" cy="20" r="2" fill="url(%23g)"><animate attributeName="r" values="1;3;1" dur="4s" repeatCount="indefinite"/></circle><circle cx="80" cy="30" r="1.5" fill="url(%23g)"><animate attributeName="r" values="0.5;2.5;0.5" dur="3s" repeatCount="indefinite"/></circle><circle cx="40" cy="70" r="2.5" fill="url(%23g)"><animate attributeName="r" values="1.5;3.5;1.5" dur="5s" repeatCount="indefinite"/></circle></svg>') repeat;
            animation: float 20s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
        
        .hero-content {
            text-align: center;
            color: white;
            max-width: 900px;
            padding: 40px 20px;
            position: relative;
            z-index: 2;
        }
        
        .hero-title {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 700;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: fadeInUp 1s ease-out;
        }
        
        .hero-subtitle {
            font-size: clamp(1.3rem, 2.5vw, 2rem);
            margin-bottom: 40px;
            opacity: 0.95;
            font-weight: 600;
            animation: fadeInUp 1s ease-out 0.3s both;
        }
        
        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 18px 40px;
            font-size: 1.2rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 50px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease-out 0.6s both;
            position: relative;
            overflow: hidden;
        }
        
        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }
        
        .cta-button:hover::before {
            left: 100%;
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 35px rgba(0,0,0,0.3);
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .section {
            padding: 80px 20px;
            max-width: 1000px;
            margin: 0 auto;
        }
        
        .section-content {
            background: white;
            padding: 60px 50px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
        }
        
        .section-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 6px;
            background: linear-gradient(135deg, #667eea, #764ba2);
        }
        
        .section-title {
            font-size: clamp(1.8rem, 3vw, 2.5rem);
            font-weight: 700;
            margin-bottom: 30px;
            color: #333;
        }
        
        .section-text {
            font-size: 1.1rem;
            line-height: 2;
            color: #555;
        }
        
        .intro-section {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        }
        
        .intro-content {
            text-align: center;
            max-width: 900px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .intro-question {
            font-size: clamp(1.3rem, 2.5vw, 1.8rem);
            font-weight: 600;
            color: #444;
            margin-bottom: 40px;
            font-style: italic;
        }
        
        .final-cta {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
        }
        
        .final-cta-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .final-message {
            font-size: clamp(1.2rem, 2vw, 1.6rem);
            margin-bottom: 50px;
            line-height: 1.8;
        }
        
        .apply-section {
            background: white;
            padding: 50px 40px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            margin: 40px 0;
        }
        
        .apply-title {
            font-size: clamp(1.5rem, 3vw, 2rem);
            font-weight: 700;
            color: #333;
            margin-bottom: 20px;
            text-align: center;
        }
        
        .apply-text {
            font-size: 1.1rem;
            color: #666;
            margin-bottom: 30px;
            text-align: center;
        }
        
        .form-button {
            display: block;
            width: 100%;
            max-width: 400px;
            margin: 0 auto;
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 20px 30px;
            font-size: 1.2rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 50px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
            text-align: center;
        }
        
        .form-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 35px rgba(0,0,0,0.3);
        }
        
        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            color: white;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-10px);
            }
            60% {
                transform: translateX(-50%) translateY(-5px);
            }
        }
        
        @media (max-width: 768px) {
            .section {
                padding: 60px 20px;
            }
            
            .section-content {
                padding: 40px 30px;
            }
            
            .apply-section {
                padding: 40px 25px;
                margin: 30px 10px;
            }
        }
    </style>
</head>
<body>
    <section class="hero-section">
        <div class="hero-content">
            <h1 class="hero-title">Sound Souls<br>ポータル開放会</h1>
            <p class="hero-subtitle">思考 vs 魂からの声、どっちを選ぶ？<br>Sound Souls で本当の自分を知る</p>
            <a href="#intro" class="cta-button">詳細を見る</a>
        </div>
        <div class="scroll-indicator">
            <div style="font-size: 1.5rem;">↓</div>
        </div>
    </section>

    <section class="section intro-section" id="intro">
        <div class="intro-content">
            <p class="intro-question">「本当に自分が望んでいることは何だろう？」そんな風に思ったことはありませんか？</p>
            <p class="section-text">
                Sound Souls は、あなた自身の超意識を解放し、「本当は何を望んでいるのか」を体感覚ではっきりさせるツールです。外に答えを求めるのではなく、より内側へと意識を向け、自分自身の中に「こたえ」を探求していく時代です。思考（脳）からの声なのか、魂からの声（純粋な意識）なのかを見分けることができるようになります。
            </p>
        </div>
    </section>

    <section class="section">
        <div class="section-content">
            <h2 class="section-title">異なるフィルターを知れば知るほど、「違い」と「自己理解」が体感できる</h2>
            <p class="section-text">
                私たちは一人一人が固有のエネルギー体であり、一つの宇宙と言っても過言ではありません。Sound Souls では、人体にある14箇所のエネルギーの根源となる箇所「ポータル」を診断することで、自分が生まれ持っている物事の捉え方を理解しやすくなります。また、他の人がどのような「フィルター」（視点）を通して世界を見ているのかを知ることで、自分自身との「違い」を体感できます。あえて他者と自分を比較し、意識的に違いを感じることで、自己を深く分析できるようになります。Sound Souls は、深いところでのコミュニケーションをスムーズにするための相互理解を深めるツールとしても使用可能です。
            </p>
        </div>
    </section>

    <section class="section">
        <div class="section-content">
            <h2 class="section-title">Sound Soulsは「古いパターン」の気づきにとにかく強い</h2>
            <p class="section-text">
                ポータルのエネルギーが落ちている状態は、「古い信じ込み」で人や物事を見ていると言い換えられます。これは、「あなたがもっと力が発揮できるポイントが他にもありますよ」というヒントでもあります。Sound Souls を活用することは、これまでの古いパターンに氣付くチャンスとなります。
            </p>
        </div>
    </section>

    <section class="section">
        <div class="section-content">
            <h2 class="section-title">現在進行形でアップデートされ続ける、Sound Soulsは「変化への適応」の最高峰</h2>
            <p class="section-text">
                Sound Souls は、完成された統計学のような学問とは違い、現在進行形でアップデートされ続ける稀有なツールであり、次世代の体感型ツールです。それは、完成されたメソッドではなく、現在進行形で更新され続けている「健全な魂の響き合い」です。このような性質を持つ Sound Souls は、「変化への適応」に役立つと言えるでしょう。
            </p>
        </div>
    </section>

    <section class="section final-cta">
        <div class="final-cta-content">
            <p class="final-message">
                Sound Souls を活用して、自分の内側に眠る新しい世界の扉を開放し、共に Sound Souls を生きましょう。
            </p>
        </div>
    </section>

    <section class="section">
        <div class="apply-section">
            <h3 class="apply-title">申し込みはこちら</h3>
            <p class="apply-text">ポータル開放会への参加申し込みは、以下のフォームよりお願いいたします。</p>
            <a href="https://forms.gle/NVmqMLDrFUSyDYw96" target="_blank" class="form-button">参加申し込みフォームへ</a>
        </div>
    </section>

    <script>
        // スムーススクロール
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // スクロール時のアニメーション
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // 要素を監視（初期状態での非表示効果を削除）
        document.querySelectorAll('.section-content, .intro-content, .apply-section').forEach(el => {
            observer.observe(el);
        });

        // パララックス効果を削除
        // window.addEventListener('scroll', () => {
        //     const scrolled = window.pageYOffset;
        //     const heroSection = document.querySelector('.hero-section');
        //     if (heroSection) {
        //         heroSection.style.transform = `translateY(${scrolled * 0.5}px)`;
        //     }
        // });
    </script>
</body>
</html>

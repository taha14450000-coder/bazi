<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>📚 اپلیکیشن کتاب‌بازی | اصلاح الگوی مصرف | دوره انتقال سوادآموزی</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #0a5c2a, #063d18);
            font-family: 'Vazirmatn', 'Segoe UI', 'Tahoma', sans-serif;
            min-height: 100vh;
            padding: 15px;
        }

        .app-container {
            max-width: 1100px;
            width: 100%;
            margin: 0 auto;
            background: #fffef5;
            border-radius: 70px;
            box-shadow: 0 30px 45px rgba(0,0,0,0.4);
            overflow: hidden;
            padding: 20px 25px 35px;
            border: 5px solid #ffd966;
        }

        /* فرم ثبت نام */
        .register-card {
            background: linear-gradient(135deg, #1e5a2a, #2e8a3a);
            border-radius: 55px;
            padding: 40px 30px;
            text-align: center;
            color: white;
        }

        .register-card h2 {
            margin-bottom: 25px;
            font-size: 1.8rem;
        }

        .register-card input {
            width: 100%;
            max-width: 350px;
            padding: 15px 20px;
            margin: 10px auto;
            border: none;
            border-radius: 60px;
            font-size: 1rem;
            font-family: inherit;
            text-align: center;
            display: block;
        }

        .register-card button {
            background: #ffaa44;
            border: none;
            padding: 14px 35px;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            margin-top: 20px;
            color: #3d2a1a;
        }

        /* هدر بازی */
        .game-header {
            background: linear-gradient(95deg, #1e5a2a, #2e8a3a);
            padding: 12px 22px;
            border-radius: 55px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 20px;
        }

        .user-info {
            background: #ffefb9;
            padding: 6px 20px;
            border-radius: 50px;
            font-weight: bold;
            color: #6b3f1a;
        }

        .score-box {
            background: #ffefb9;
            padding: 6px 20px;
            border-radius: 50px;
            font-weight: bold;
        }

        .question-counter {
            background: #1e3a1e;
            padding: 6px 20px;
            border-radius: 50px;
            color: #ffdc97;
        }

        .progress-bar {
            flex: 2;
            background: #3d2a1a;
            border-radius: 30px;
            height: 18px;
            overflow: hidden;
        }

        .progress-fill {
            width: 0%;
            height: 100%;
            background: linear-gradient(90deg, #ffd966, #ffa500);
            border-radius: 30px;
            transition: width 0.4s;
        }

        .character-area {
            background: #fff0dc;
            border-radius: 55px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 18px;
            padding: 12px 25px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .avatar {
            font-size: 4rem;
            background: #ffe6b3;
            border-radius: 100px;
            padding: 8px 15px;
        }

        .speech {
            background: white;
            padding: 12px 25px;
            border-radius: 45px;
            font-weight: bold;
            color: #2c6e2c;
            max-width: 480px;
        }

        .teach-card {
            background: linear-gradient(120deg, #f3f8ec, #eef5e4);
            border-radius: 45px;
            padding: 25px;
            margin-bottom: 20px;
            border-right: 12px solid #ffaa33;
            line-height: 1.8;
            font-size: 1rem;
            max-height: 400px;
            overflow-y: auto;
        }

        .ref-tag {
            display: inline-block;
            background: #ffefcf;
            padding: 4px 16px;
            border-radius: 30px;
            font-size: 0.7rem;
            color: #b8621a;
            margin-bottom: 12px;
        }

        .question-card {
            background: #fff9ec;
            border-radius: 55px;
            padding: 28px 20px;
            text-align: center;
            font-size: 1.4rem;
            font-weight: 800;
            color: #2b4a22;
            margin: 15px 0;
            border: 3px dashed #ffbc5e;
        }

        .options-area {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 18px;
            margin: 25px 0;
        }

        .option-btn {
            background: #fff3df;
            border: none;
            padding: 16px 12px;
            border-radius: 60px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 7px 0 #b9792a;
            transition: 0.05s linear;
        }

        .option-btn:active {
            transform: translateY(4px);
            box-shadow: 0 2px 0 #b9792a;
        }

        .feedback-area {
            background: #fcf3e0;
            border-radius: 45px;
            padding: 18px;
            margin: 15px 0;
            text-align: center;
            font-weight: bold;
        }

        .feedback-correct {
            background: #c8e6c9;
            border-right: 10px solid #2e7d32;
        }

        .feedback-wrong {
            background: #ffded5;
            border-right: 10px solid #c62828;
        }

        .buttons-row {
            display: flex;
            gap: 20px;
            margin-top: 20px;
        }

        .btn-next, .btn-reset {
            flex: 1;
            background: #ffaa44;
            border: none;
            padding: 14px;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 5px 0 #8b5a2b;
        }

        .btn-reset {
            background: #9b7a58;
            color: white;
        }

        button:active {
            transform: translateY(3px);
            box-shadow: 0 2px 0 #8b5a2b;
        }

        button:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .result-card {
            background: linear-gradient(135deg, #1e5a2a, #2e8a3a);
            border-radius: 55px;
            padding: 30px;
            text-align: center;
            color: white;
            margin-top: 20px;
        }

        .result-stats {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin: 25px 0;
            flex-wrap: wrap;
        }

        .stat-circle {
            background: #ffefb9;
            color: #6b3f1a;
            border-radius: 100px;
            width: 100px;
            height: 100px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
        }

        .wrong-answers-list {
            background: #fff3e0;
            border-radius: 40px;
            padding: 20px;
            margin-top: 20px;
            text-align: right;
            color: #3d2a1a;
            max-height: 300px;
            overflow-y: auto;
        }

        .wrong-item {
            background: #ffded5;
            padding: 12px;
            margin: 8px 0;
            border-radius: 25px;
            border-right: 5px solid #c62828;
        }

        .correct-item {
            background: #c8e6c9;
            padding: 12px;
            margin: 8px 0;
            border-radius: 25px;
            border-right: 5px solid #2e7d32;
        }

        .share-btn, .again-btn {
            background: #ffaa44;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            margin: 10px 5px;
        }

        .again-btn {
            background: #2e7d32;
            color: white;
        }

        .hidden {
            display: none;
        }

        footer {
            text-align: center;
            font-size: 0.7rem;
            margin-top: 25px;
            color: #a57848;
        }
    </style>
</head>
<body>
<div class="app-container" id="appContainer">
    <!-- بخش ثبت نام -->
    <div id="registerSection">
        <div class="register-card">
            <div class="avatar" style="font-size: 5rem; background: none; display: inline-block;">🦉</div>
            <h2>📚 به کتاب‌بازی خوش آمدی!</h2>
            <p style="margin-bottom: 20px;">لطفاً نام و نام خانوادگی خود را وارد کن تا بازی شروع بشه</p>
            <input type="text" id="firstName" placeholder="نام" autocomplete="off">
            <input type="text" id="lastName" placeholder="نام خانوادگی" autocomplete="off">
            <button id="startGameBtn">🎮 شروع بازی</button>
        </div>
    </div>

    <!-- بخش اصلی بازی (ابتدا پنهان) -->
    <div id="gameSection" class="hidden">
        <div class="game-header">
            <div class="user-info" id="userNameDisplay">👤 کاربر</div>
            <div class="score-box">⭐ <span id="scoreValue">0</span> / <span id="totalValue">0</span></div>
            <div class="progress-bar"><div class="progress-fill" id="progressFill"></div></div>
            <div class="question-counter">📖 سوال <span id="currentQNumber">1</span> از <span id="totalQNumber"></span></div>
        </div>

        <div class="character-area">
            <div class="avatar">🦉 دانا</div>
            <div class="speech" id="speechBubble">سلام! امروز با هم کتاب «اصلاح الگوی مصرف» رو میخونیم. اول آموزش میبینیم، بعد سوال میپرسیم! 🌟</div>
        </div>

        <div id="teachSection">
            <div><span id="refTag" class="ref-tag"></span></div>
            <div id="teachText" class="teach-card"></div>
        </div>

        <div id="quizSection" class="hidden">
            <div id="questionText" class="question-card"></div>
            <div id="optionsContainer" class="options-area"></div>
            <div id="feedbackMsg" class="feedback-area">✨ گزینه مناسب رو انتخاب کن ✨</div>
        </div>

        <div id="resultSection" class="hidden result-card"></div>

        <div class="buttons-row">
            <button id="nextButton" class="btn-next">➡ ادامه</button>
            <button id="resetButton" class="btn-reset">🔄 شروع دوباره</button>
        </div>
    </div>
    <footer>📖 کتاب «اصلاح الگوی مصرف» - دوره انتقال سوادآموزی | دیتابیس داخلی - ذخیره اطلاعات</footer>
</div>

<script>
    // ============================================================
    // دیتابیس داخلی (localStorage) - ذخیره اطلاعات کاربر و پاسخ‌ها
    // ============================================================
    
    // تمام سوالات کتاب (۳۵ سوال از کل مباحث)
    const allLessons = [
        { teach: "اسراف در لغت به معنی زیاده‌روی و از حد گذشتن است. اسراف شامل زیاده‌روی در خوراک، پوشاک، آب، برق، گاز است. امام صادق(ع) می‌فرماید: «هرکسی نعمت خدا را در غیر اطاعت خدا مصرف کند، اسراف کرده است.»", q: "اسراف در لغت به چه معناست؟", opts: ["میانه روی و تعادل", "زیاده روی و از حد گذشتن", "صرفه جویی", "قناعت"], correct: 1, ref: "صفحه 6" },
        { teach: "خداوند در قرآن از اسراف‌کاران به عنوان «برادران شیطان» نام برده است. (سوره اسراء آیه 27)", q: "خداوند در قرآن اسراف کاران را چه نامیده است؟", opts: ["بندگان صالح", "برادران شیطان", "یاران پیامبر", "مؤمنان راستین"], correct: 1, ref: "صفحه 7" },
        { teach: "پیامبر اکرم(ص) می‌فرماید: «در هر کاری حتی کار خیر، نباید اسراف و زیاده‌روی کرد.»", q: "پیامبر(ص) درباره اسراف در کار خیر چه فرمودند؟", opts: ["اسراف در خیر اشکال ندارد", "هرچه بیشتر بهتر", "حتی در کار خیر نباید اسراف کرد", "فقط در گناه اسراف بد است"], correct: 2, ref: "صفحه 7" },
        { teach: "حضرت علی(ع) می‌فرماید: «میانه روی موجب فراوانی مال و اسراف موجب نابودی آن است.»", q: "به فرموده حضرت علی(ع) اسراف چه نتیجه‌ای دارد؟", opts: ["افزایش مال", "نابودی مال", "برکت بیشتر", "ثروت زیاد"], correct: 1, ref: "صفحه 7" },
        { teach: "عوامل ایجاد اسراف: ۱- یادگیری از اطرافیان ۲- ناآگاهی ۳- چشم و هم‌چشمی ۴- تجمل‌گرایی.", q: "کدام یک از موارد زیر از عوامل اسراف نیست؟", opts: ["چشم و هم چشمی", "قناعت", "ناآگاهی", "تجمل گرایی"], correct: 1, ref: "صفحه 8" },
        { teach: "آثار منفی اسراف: کم شدن برکت، گرفته شدن نعمت، افزایش بی‌عدالتی و فخر فروشی.", q: "اولین اثر منفی اسراف در دنیا چیست؟", opts: ["افزایش برکت", "کم شدن برکت", "بیشتر شدن ثروت", "طولانی شدن عمر"], correct: 1, ref: "صفحه 9" },
        { teach: "مهم‌ترین راه مبارزه با اسراف: میانه‌روی. میانه‌روی یعنی از هر چیزی درست و به اندازه استفاده کنیم.", q: "مهم‌ترین راه مبارزه با اسراف چیست؟", opts: ["چشم و هم چشمی", "میانه روی", "تجمل گرایی", "ریخت و پاش"], correct: 1, ref: "صفحه 11" },
        { teach: "الگو در لغت به معنی نمونه و سرمشق است. اصلاح الگوی مصرف یعنی روش صحیح استفاده از منابع کشور.", q: "«اصلاح الگوی مصرف» یعنی چه؟", opts: ["روش صحیح استفاده از منابع", "بیشتر مصرف کردن", "اسراف کردن", "ذخیره نکردن"], correct: 0, ref: "صفحه 13" },
        { teach: "بهترین الگوی مصرف، میانه‌روی است. امام صادق(ع): «ضمانت می‌کنم کسی که میانه‌روی کند فقیر نشود.»", q: "بهترین الگوی مصرف برای زندگی سعادتمند چیست؟", opts: ["تجمل", "میانه روی", "اسراف", "چشم و هم چشمی"], correct: 1, ref: "صفحه 13-14" },
        { teach: "امام خمینی(ره) می‌فرمود: خود را به ساده‌زیستی عادت دهید. مقام معظم رهبری سال ۱۳۸۸ را سال «اصلاح الگوی مصرف» نامیدند.", q: "مقام معظم رهبری سال ۱۳۸۸ را سال چه نامیدند؟", opts: ["تولید ملی", "اصلاح الگوی مصرف", "جهاد اقتصادی", "صرفه جویی"], correct: 1, ref: "صفحه 16-17" },
        { teach: "خانواده کوچک‌ترین نهاد اجتماعی است که بیشترین نقش را در تربیت و اصلاح الگوی مصرف دارد. زنان نقش بیشتری دارند.", q: "بیشترین نقش در اصلاح الگوی مصرف بر عهده کدام نهاد است؟", opts: ["مدرسه", "خانواده", "صدا و سیما", "بازار"], correct: 1, ref: "صفحه 19" },
        { teach: "کشور ما کم‌آب است. هنگام شامپو زدن شیر آب را ببندید. شیر چکه‌کننده سالانه ۶ هزار لیتر آب هدر می‌دهد.", q: "شیر چکه کننده سالانه چند لیتر آب هدر می‌دهد؟", opts: ["۱۰۰۰ لیتر", "۶۰۰۰ لیتر", "۱۰۰۰۰ لیتر", "۵۰۰ لیتر"], correct: 1, ref: "صفحه 23-25" },
        { teach: "صرفه‌جویی در برق: از لامپ کم مصرف استفاده کنید. برفک زدن یخچال مصرف برق را کم می‌کند.", q: "برفک زدن یخچال چه فایده‌ای دارد؟", opts: ["کاهش مصرف برق", "افزایش مصرف", "تخریب یخچال", "هیچ"], correct: 0, ref: "صفحه 26-27" },
        { teach: "صرفه‌جویی در گاز: در زمستان لباس گرم بپوشید. قابلمه باید اندازه شعله باشد.", q: "برای صرفه جویی در گاز زمستان چه کنیم؟", opts: ["شعله را زیاد کنیم", "لباس گرم بپوشیم", "بخاری را خاموش کنیم", "پنجره باز کنیم"], correct: 1, ref: "صفحه 28-29" },
        { teach: "در خرید مواد غذایی: در زمان گرسنگی خرید نکنید. از ظرف یکبار مصرف استفاده نکنید.", q: "چه زمانی برای خرید مواد غذایی مناسب نیست؟", opts: ["سیر", "گرسنه", "صبح", "عصر"], correct: 1, ref: "صفحه 31" },
        { teach: "اسراف در لباس یعنی لباس با ارزش را در کار روزانه بپوشید و زود خراب کنید.", q: "اسراف در لباس یعنی چه؟", opts: ["داشتن دو دست لباس", "پوشیدن لباس خوب در کار روزانه", "خرید لباس ارزان", "شستن لباس"], correct: 1, ref: "صفحه 32" },
        { teach: "کشور ما دومین کشور مصرف‌کننده نان در جهان است. نان داغ را در پلاستیک نگذارید (کپک می‌زند).", q: "کشور ما در مصرف نان رتبه چندم جهان است؟", opts: ["اول", "دوم", "سوم", "چهارم"], correct: 1, ref: "صفحه 33" },
        { teach: "مصرف زیاد گوشت قرمز باعث نقرس و سکته قلبی می‌شود. می‌توان به جای گوشت از سویا استفاده کرد.", q: "مصرف زیاد گوشت قرمز چه بیماری ایجاد می‌کند؟", opts: ["نقرس", "سرماخوردگی", "تب", "کرونا"], correct: 0, ref: "صفحه 35" },
        { teach: "هر هفته سه وعده سبزی بخورید. میوه‌هایی که پوست خوردنی دارند با پوست خورده شوند.", q: "هر هفته چند وعده سبزی بخوریم؟", opts: ["یک وعده", "سه وعده", "پنج وعده", "هیچ"], correct: 1, ref: "صفحه 36" },
        { teach: "عدس می‌تواند جایگزین گوشت شود. برنج را به صورت کته بپزید.", q: "عدس چه خاصیتی دارد؟", opts: ["جایگزین گوشت", "جایگزین میوه", "جایگزین نان", "جایگزین آب"], correct: 0, ref: "صفحه 37" },
        { teach: "وقت از باارزش‌ترین سرمایه‌هاست. از کارت عابر بانک برای جلوگیری از اتلاف وقت استفاده کنید.", q: "برای جلوگیری از اتلاف وقت در بانک چه کنیم؟", opts: ["کارت عابر بانک", "صبح زود برویم", "با دوست حرف بزنیم", "کتاب بخوانیم"], correct: 0, ref: "صفحه 38" },
        { teach: "صحبت تلفنی را کوتاه کنید. زباله‌ها را جداسازی کنید. از باتری‌های قابل شارژ استفاده کنید.", q: "برای بازیافت زباله چه باید کرد؟", opts: ["همه را قاطی کنیم", "جدا کنیم", "آتش بزنیم", "بریزیم رودخانه"], correct: 1, ref: "صفحه 39" }
    ];

    // متغیرهای بازی
    let gameLessons = [];
    let currentIndex = 0;
    let userResults = [];      // آرایه ذخیره true/false برای هر سوال
    let userAnswersDetail = []; // ذخیره جزئیات پاسخ‌ها (سوال، پاسخ کاربر، پاسخ صحیح)
    let currentStage = "teach";
    let quizLocked = false;
    let totalCount = 0;
    let currentUser = { firstName: "", lastName: "" };

    // عناصر DOM
    const registerSection = document.getElementById('registerSection');
    const gameSection = document.getElementById('gameSection');
    const startBtn = document.getElementById('startGameBtn');
    const firstNameInput = document.getElementById('firstName');
    const lastNameInput = document.getElementById('lastName');
    const userNameDisplay = document.getElementById('userNameDisplay');
    const teachSection = document.getElementById('teachSection');
    const quizSection = document.getElementById('quizSection');
    const resultSection = document.getElementById('resultSection');
    const nextBtn = document.getElementById('nextButton');
    const resetBtn = document.getElementById('resetButton');
    const speechBubble = document.getElementById('speechBubble');
    const scoreSpan = document.getElementById('scoreValue');
    const totalSpan = document.getElementById('totalValue');
    const progressFill = document.getElementById('progressFill');
    const currentQSpan = document.getElementById('currentQNumber');
    const totalQSpan = document.getElementById('totalQNumber');
    const refTag = document.getElementById('refTag');
    const teachText = document.getElementById('teachText');
    const questionText = document.getElementById('questionText');
    const optionsContainer = document.getElementById('optionsContainer');
    const feedbackMsg = document.getElementById('feedbackMsg');

    // ذخیره اطلاعات در دیتابیس داخلی
    function saveToDatabase() {
        const db = {
            user: currentUser,
            totalQuestions: totalCount,
            userResults: userResults,
            answersDetail: userAnswersDetail,
            date: new Date().toLocaleString('fa-IR'),
            completed: currentStage === "result" || userResults.length === totalCount
        };
        localStorage.setItem('bookGame_data', JSON.stringify(db));
        localStorage.setItem('bookGame_user', JSON.stringify(currentUser));
    }

    // بارگذاری اطلاعات قبلی (اگر کاربر قبلاً بازی کرده باشد)
    function loadFromDatabase() {
        const savedUser = localStorage.getItem('bookGame_user');
        const savedData = localStorage.getItem('bookGame_data');
        if (savedUser) {
            const user = JSON.parse(savedUser);
            firstNameInput.value = user.firstName || '';
            lastNameInput.value = user.lastName || '';
        }
    }

    function shuffleArray(arr) {
        for (let i = arr.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [arr[i], arr[j]] = [arr[j], arr[i]];
        }
        return arr;
    }

    function updateDisplay() {
        let correctCount = userResults.filter(r => r === true).length;
        scoreSpan.innerText = correctCount;
        totalSpan.innerText = totalCount;
        let answered = userResults.length;
        let percent = (answered / totalCount) * 100;
        progressFill.style.width = `${percent}%`;
        currentQSpan.innerText = Math.min(answered + 1, totalCount);
        totalQSpan.innerText = totalCount;
        saveToDatabase();
    }

    function loadTeach() {
        currentStage = "teach";
        teachSection.classList.remove('hidden');
        quizSection.classList.add('hidden');
        resultSection.classList.add('hidden');
        
        const lesson = gameLessons[currentIndex];
        refTag.innerHTML = `📌 مرجع: ${lesson.ref}`;
        teachText.innerHTML = `<strong>📘 متن کتاب:</strong><br><br> ${lesson.teach}`;
        speechBubble.innerHTML = "📚 این قسمت رو با دقت بخون! بعدش ازت سوال می‌پرسم.";
        nextBtn.innerHTML = "📖 خوندم! بریم سراغ سوال ➡";
        nextBtn.disabled = false;
        updateDisplay();
    }

    function loadQuiz() {
        currentStage = "quiz";
        quizLocked = false;
        teachSection.classList.add('hidden');
        quizSection.classList.remove('hidden');
        resultSection.classList.add('hidden');
        
        const lesson = gameLessons[currentIndex];
        questionText.innerHTML = lesson.q;
        
        let mixedOpts = [...lesson.opts];
        for (let i = mixedOpts.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [mixedOpts[i], mixedOpts[j]] = [mixedOpts[j], mixedOpts[i]];
        }
        
        optionsContainer.innerHTML = '';
        mixedOpts.forEach(opt => {
            const btn = document.createElement('button');
            btn.className = 'option-btn';
            btn.innerText = opt;
            btn.onclick = () => checkAnswer(opt, lesson, btn);
            optionsContainer.appendChild(btn);
        });
        
        feedbackMsg.innerHTML = "✨ گزینه مناسب رو انتخاب کن ✨";
        feedbackMsg.className = "feedback-area";
        speechBubble.innerHTML = "🤔 کدوم گزینه درسته؟ با دقت فکر کن!";
        nextBtn.innerHTML = "➡ سوال بعدی";
        nextBtn.disabled = true;
        updateDisplay();
    }

    function checkAnswer(selected, lesson, btnElement) {
        if (quizLocked) return;
        const isCorrect = (selected === lesson.opts[lesson.correct]);
        quizLocked = true;
        
        userResults[currentIndex] = isCorrect;
        userAnswersDetail[currentIndex] = {
            question: lesson.q,
            userAnswer: selected,
            correctAnswer: lesson.opts[lesson.correct],
            isCorrect: isCorrect,
            teach: lesson.teach,
            ref: lesson.ref
        };
        
        const allBtns = document.querySelectorAll('.option-btn');
        allBtns.forEach(btn => btn.style.pointerEvents = 'none');
        
        if (isCorrect) {
            feedbackMsg.innerHTML = `<div style="padding:12px;">✅ آفرین! پاسخ درست است! 🎉</div>`;
            feedbackMsg.className = "feedback-area feedback-correct";
            speechBubble.innerHTML = "🎉 عالی! پاسخ تو درست بود. آفرین!";
            allBtns.forEach(btn => {
                if (btn.innerText === lesson.opts[lesson.correct]) {
                    btn.style.background = "#b9f6ca";
                    btn.style.boxShadow = "0 2px 0 #2e7d32";
                }
            });
        } else {
            feedbackMsg.innerHTML = `<div style="padding:12px;">❌ پاسخ صحیح: «${lesson.opts[lesson.correct]}»<br>📖 ${lesson.teach.substring(0, 100)}...</div>`;
            feedbackMsg.className = "feedback-area feedback-wrong";
            speechBubble.innerHTML = "😊 اشکال نداره! دفعه بعد درست جواب میدی. جواب رو یاد بگیر.";
            allBtns.forEach(btn => {
                if (btn.innerText === lesson.opts[lesson.correct]) {
                    btn.style.background = "#b9f6ca";
                    btn.style.boxShadow = "0 2px 0 #2e7d32";
                }
                if (btn.innerText === selected && !isCorrect) {
                    btn.style.background = "#ffcdb0";
                    btn.style.boxShadow = "0 2px 0 #c62828";
                }
            });
        }
        
        updateDisplay();
        nextBtn.disabled = false;
        saveToDatabase();
    }

    function loadResult() {
        currentStage = "result";
        teachSection.classList.add('hidden');
        quizSection.classList.add('hidden');
        resultSection.classList.remove('hidden');
        
        const correctCount = userResults.filter(r => r === true).length;
        const wrongCount = userResults.filter(r => r === false).length;
        const percent = Math.round((correctCount / totalCount) * 100);
        
        // ساخت لیست سوالات غلط و درست
        let wrongListHtml = "";
        let correctListHtml = "";
        
        userAnswersDetail.forEach((detail, idx) => {
            if (detail && !detail.isCorrect) {
                wrongListHtml += `
                    <div class="wrong-item">
                        <strong>❌ سوال ${idx+1}:</strong> ${detail.question}<br>
                        <span style="color:#c62828;">پاسخ شما: ${detail.userAnswer}</span><br>
                        <span style="color:#2e7d32;">✅ پاسخ صحیح: ${detail.correctAnswer}</span><br>
                        <small>📖 ${detail.teach.substring(0, 80)}...</small>
                    </div>
                `;
            } else if (detail && detail.isCorrect) {
                correctListHtml += `
                    <div class="correct-item">
                        <strong>✅ سوال ${idx+1}:</strong> ${detail.question}<br>
                        پاسخ شما: ${detail.userAnswer} (درست)
                    </div>
                `;
            }
        });
        
        let message = "";
        let emoji = "";
        if (percent === 100) {
            message = "قهرمان کامل! 🎓 تو تمام کتاب رو عالی یاد گرفتی!";
            emoji = "🏆🌟🎉";
        } else if (percent >= 80) {
            message = "خیلی خوب! 🌟 با یک بار دیگه عالی می‌شی.";
            emoji = "👍📚⭐";
        } else if (percent >= 60) {
            message = "خوب بود! 💪 دوباره بازی کن تا قوی‌تر شی.";
            emoji = "📖🌱✨";
        } else {
            message = "نگران نباش! 😊 دوباره تلاش کن و کتاب رو کامل یاد بگیر.";
            emoji = "💪🌸🍃";
        }
        
        resultSection.innerHTML = `
            <div style="font-size: 2rem; margin-bottom: 15px;">${emoji}</div>
            <h2 style="margin-bottom: 15px;">📊 کارنامه یادگیری ${currentUser.firstName} ${currentUser.lastName}</h2>
            <div class="result-stats">
                <div class="stat-circle">
                    <div class="stat-number">${correctCount}</div>
                    <div>✅ درست</div>
                </div>
                <div class="stat-circle">
                    <div class="stat-number">${wrongCount}</div>
                    <div>❌ غلط</div>
                </div>
                <div class="stat-circle">
                    <div class="stat-number">${percent}%</div>
                    <div>📈 نمره</div>
                </div>
            </div>
            <p style="font-size: 1.2rem; margin: 20px 0;">${message}</p>
            
            ${wrongCount > 0 ? `
                <div class="wrong-answers-list">
                    <h3>❌ سوالاتی که غلط جواب دادی (${wrongCount} سوال)</h3>
                    ${wrongListHtml}
                </div>
            ` : '<p style="background:#c8e6c9; padding:15px; border-radius:30px;">🎉 تبریک! هیچ سوالی رو غلط جواب ندادی!</p>'}
            
            ${correctCount > 0 ? `
                <div class="wrong-answers-list" style="margin-top:15px; background:#e8f5e9;">
                    <h3>✅ سوالاتی که درست جواب دادی (${correctCount} سوال)</h3>
                    ${correctListHtml.substring(0, 800)}${correctListHtml.length > 800 ? '...' : ''}
                </div>
            ` : ''}
            
            <button id="shareResultBtn" class="share-btn">📤 اشتراک‌گذاری نتیجه</button>
            <button id="playAgainBtn" class="again-btn">🎮 بازی دوباره</button>
        `;
        
        speechBubble.innerHTML = `🎉 کارنامه تو: ${correctCount} درست، ${wrongCount} غلط! ${message}`;
        
        document.getElementById('shareResultBtn')?.addEventListener('click', () => {
            const text = `📚 ${currentUser.firstName} ${currentUser.lastName} عزیز!\nمن در بازی کتاب «اصلاح الگوی مصرف» به ${correctCount} سوال از ${totalCount} سوال درست جواب دادم!\nنمره من ${percent}% شد.\n${wrongCount} سوال رو غلط جواب دادم که دوباره تمرین میکنم.\n\n#سوادآموزی #اصلاح_الگوی_مصرف`;
            if (navigator.share) {
                navigator.share({ title: 'نتیجه بازی کتاب اصلاح الگوی مصرف', text: text });
            } else {
                navigator.clipboard.writeText(text);
                alert("✅ متن نتیجه کپی شد! می‌تونی برای دوستات بفرستی.");
            }
        });
        
        document.getElementById('playAgainBtn')?.addEventListener('click', () => fullReset());
        
        nextBtn.disabled = true;
        saveToDatabase();
    }

    function nextStep() {
        if (currentStage === "teach") {
            loadQuiz();
        } 
        else if (currentStage === "quiz") {
            if (!quizLocked) {
                speechBubble.innerHTML = "🤔 لطفاً اول یک گزینه رو انتخاب کن!";
                return;
            }
            if (currentIndex + 1 >= totalCount) {
                loadResult();
            } else {
                currentIndex++;
                loadTeach();
            }
        }
    }

    function fullReset() {
        gameLessons = shuffleArray([...allLessons]);
        currentIndex = 0;
        userResults = [];
        userAnswersDetail = [];
        currentStage = "teach";
        quizLocked = false;
        totalCount = gameLessons.length;
        loadTeach();
        nextBtn.disabled = false;
        speechBubble.innerHTML = "سلام! بیا دوباره از اول کتاب رو کامل یاد بگیریم 🌟";
        saveToDatabase();
    }

    function startGame() {
        const firstName = firstNameInput.value.trim();
        const lastName = lastNameInput.value.trim();
        if (!firstName || !lastName) {
            alert("لطفاً نام و نام خانوادگی خود را وارد کنید!");
            return;
        }
        currentUser = { firstName, lastName };
        userNameDisplay.innerHTML = `👤 ${firstName} ${lastName}`;
        
        registerSection.classList.add('hidden');
        gameSection.classList.remove('hidden');
        
        fullReset();
    }

    startBtn.onclick = startGame;
    resetBtn.onclick = fullReset;
    nextBtn.onclick = nextStep;
    
    firstNameInput.addEventListener('keypress', (e) => { if (e.key === 'Enter') startGame(); });
    lastNameInput.addEventListener('keypress', (e) => { if (e.key === 'Enter') startGame(); });
    
    loadFromDatabase();
</script>
</body>
</html>

<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>میراث فرهنگی ایران</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Vazirmatn', sans-serif; /* اعمال فونت وزیر */
            background-color: #f8f8f8; /* پس‌زمینه روشن‌تر */
            color: #333;
            line-height: 1.7; /* افزایش فاصله خطوط برای خوانایی بهتر در متن فارسی */
        }
        .container {
            max-width: 700px; /* عرض کمتر برای تمرکز بیشتر */
            margin: 30px auto; /* فاصله بیشتر از بالا و پایین */
            padding: 0 20px; /* پدینگ بیشتر در کناره‌ها */
        }
        .card {
            background-color: #fff;
            border-radius: 8px; /* گوشه‌های کمی گرد */
            padding: 25px; /* پدینگ داخلی بیشتر */
            margin-bottom: 25px; /* فاصله بیشتر بین کارت‌ها */
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05); /* سایه بسیار ملایم */
            transition: transform 0.2s ease-in-out;
            border: 1px solid #eee; /* حاشیه بسیار نازک */
        }
        .card:hover {
            transform: translateY(-3px); /* افکت شناور شدن ملایم‌تر */
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.08); /* سایه کمی بیشتر هنگام هاور */
        }
        .card-title {
            font-size: 1.3rem; /* اندازه عنوان کمی کوچکتر */
            font-weight: 700; /* وزن فونت بولد */
            margin-bottom: 15px;
            color: #222; /* رنگ تیره‌تر برای عنوان */
            border-bottom: 1px solid #eee; /* خط زیر عنوان نازک و ملایم */
            padding-bottom: 10px;
        }
        .card-section-title {
            font-weight: 700; /* وزن فونت بولد */
            margin-top: 15px; /* فاصله بیشتر از بالا */
            margin-bottom: 8px; /* فاصله بیشتر از پایین */
            color: #444; /* رنگ کمی تیره‌تر */
            font-size: 0.95rem; /* اندازه کمی کوچکتر */
        }
        .card-text {
            line-height: 1.8; /* افزایش فاصله خطوط برای متن اصلی */
            color: #555; /* رنگ متن کمی روشن‌تر */
        }
        .details-content {
            margin-top: 20px; /* فاصله بیشتر از بالا */
            padding-top: 20px; /* پدینگ داخلی بیشتر */
            border-top: 1px solid #eee; /* خط جداکننده ملایم */
        }
        .search-box {
            margin-bottom: 30px;
            padding: 15px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
            border: 1px solid #eee;
        }
        .search-input {
            width: 100%;
            padding: 10px 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-family: 'Vazirmatn', sans-serif;
            font-size: 1rem;
        }
        .search-input:focus {
            outline: none;
            border-color: #007bff;
            box-shadow: 0 0 5px rgba(0, 123, 255, 0.25);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="text-2xl font-bold text-center my-10 text-gray-800">اطلاعات میراث فرهنگی ایران</h1>

        <div class="search-box">
            <input type="text" id="search-input" class="search-input" placeholder="جستجو بر اساس موضوع، مکان، دوره یا جزئیات...">
        </div>

        <div id="content-area">
            </div>
    </div>

    <script>
        // داده‌های جدول به صورت یک آرایه از اشیاء
        const culturalData = [
            {
                topic: "معیارهای میراث فرهنگی",
                description: "معیارهای اصلی برای در نظر گرفتن یک پدیده به عنوان میراث فرهنگی.",
                location: "نامشخص",
                period: "نامشخص",
                details: "قدمت تاریخی، پیام انسانی."
            },
            {
                topic: "کهن‌ترین پدیده فرهنگی",
                description: "ابزارهای سنگی، کهن‌ترین پدیده فرهنگی در ایران محسوب می‌شوند.",
                location: "کشفرود، خراسان",
                period: "حدود ۸۰۰ هزار سال",
                details: "شاهدی بر فعالیت‌های اولیه انسان."
            },
            {
                topic: "تپه زاغه",
                description: "یک محوطه باستانی شامل بقایای سازه‌های قدیمی.",
                location: "قزوین",
                period: "دوره نوسنگی",
                details: "شناسایی شده به عنوان یکی از مکان‌های معابد کشف شده در ایران از این دوره."
            },
            {
                topic: "عصر نوسنگی",
                description: "یک دوره تاریخی اولیه که با پیشرفت‌هایی مانند کشاورزی و سفالگری مشخص می‌شود.",
                location: "ایران (بافت کلی)",
                period: "۴۵۰۰-۳۰۰۰ پ.م.",
                details: "به دو دوره پیش از سفال و پس از سفال تقسیم می‌شود. قدیمی‌ترین ظرف سفالین کشف شده در ایران در ایران ۹۰۰۰ سال قدمت دارد."
            },
            {
                topic: "عصر مفرغ",
                description: "دوره تاریخی پس از نوسنگی.",
                location: "ایران (بافت کلی)",
                period: "۳۰۰۰-۱۵۰۰ پ.م.",
                details: "پس از دوره نوسنگی آغاز شد."
            },
            {
                topic: "نقش برجسته سرپل ذهاب",
                description: "اولین نقش برجسته ایران.",
                location: "سرپل ذهاب، کرمانشاه",
                period: "(زمان آنوبانینی)",
                details: "توسط آنوبانینی، حاکم قوم مهاجر لولوبی (یک گروه عشایر دامدار آسیایی)، ایجاد شده است."
            },
            {
                topic: "نقش برجسته بیستون",
                description: "یک نقش برجسته و کتیبه سنگی مهم باستانی.",
                location: "بیستون",
                period: "(دوره هخامنشی)",
                details: "از نقش برجسته سرپل ذهاب الهام گرفته شده است."
            },
            {
                topic: "شهر سوخته",
                description: "یک شهر باستانی بزرگ با ساختار پیچیده و مناطق مختلف.",
                location: "استان سیستان و بلوچستان",
                period: "۳۲۰۰-۱۸۰۰ پ.م.",
                details: "۱۵۰ هکتار وسعت داشت. شامل مناطق مسکونی، صنعتی و قبرستان بود. واحدهای مسکونی ۹۰-۱۰۰ متر مربع مساحت داشتند. ساختار سیاسی پیچیده شهر مسئول نگهداری غلات بود."
            },
            {
                topic: "یافته‌های مهم شهر سوخته",
                description: "یافته‌های فرهنگی کلیدی از شهر که نشان‌دهنده تمدن پیشرفته آن است.",
                location: "شهر سوخته",
                period: "۳۲۰۰-۱۸۰۰ پ.م. (بافت کلی)",
                details: "جام سفالین (اولین انیمیشن جهان)، قدیمی‌ترین شواهد جراحی روی جمجمه، کامل‌ترین مجموعه پارچه ایرانی، قدیمی‌ترین نمونه معرق‌کاری/کاربندی، قدیمی‌ترین بازی دنیا (تخته نرد)، و قدیمی‌ترین چشم مصنوعی."
            },
            {
                topic: "گل نبشته عیلامی کهن / دوره تاریخی",
                description: "کشفی که نقطه عطفی مهم در تاریخ ایران محسوب می‌شود و نشان‌دهنده آغاز دوره تاریخی است.",
                location: "نامشخص (مکان در متن اصلی مشخص نشده بود)",
                period: "۱۸۰۰-۱۶۰۰ پ.م.",
                details: "یک گل نبشته به خط عیلامی کهن. این دوره (که با کشف مکتوبات مشخص می‌شود) آغاز ورود ایران به دوره تاریخی محسوب می‌گردد."
            }
        ];

        // تابعی برای ایجاد یک کارت HTML برای هر آیتم داده
        function createCard(item) {
            const cardDiv = document.createElement('div');
            cardDiv.classList.add('card');

            const titleDiv = document.createElement('div');
            titleDiv.classList.add('card-title');
            titleDiv.textContent = item.topic;
            cardDiv.appendChild(titleDiv);

            const descriptionDiv = document.createElement('div');
            descriptionDiv.classList.add('card-text');
            descriptionDiv.textContent = item.description;
            cardDiv.appendChild(descriptionDiv);

            // محتوای جزئیات که همیشه نمایش داده می‌شود
            const detailsContentDiv = document.createElement('div');
            detailsContentDiv.classList.add('details-content');
            detailsContentDiv.innerHTML = `
                <div class="card-section-title">مکان:</div>
                <div class="card-text">${item.location}</div>
                <div class="card-section-title">دوره/قدمت:</div>
                <div class="card-text">${item.period}</div>
                <div class="card-section-title">جزئیات کلیدی/یافته‌ها:</div>
                <div class="card-text">${item.details}</div>
            `;
            cardDiv.appendChild(detailsContentDiv);

            return cardDiv;
        }

        // تابعی برای نمایش کارت‌ها
        function displayCards(dataToDisplay) {
            const contentArea = document.getElementById('content-area');
            contentArea.innerHTML = ''; // پاک کردن محتوای قبلی
            if (dataToDisplay.length === 0) {
                contentArea.innerHTML = '<p class="text-center text-gray-600">هیچ نتیجه‌ای یافت نشد.</p>';
            } else {
                dataToDisplay.forEach(item => {
                    const card = createCard(item);
                    contentArea.appendChild(card);
                });
            }
        }

        // تابعی برای فیلتر کردن داده‌ها بر اساس ورودی جستجو
        function filterData(searchTerm) {
            const lowerCaseSearchTerm = searchTerm.toLowerCase();
            return culturalData.filter(item => {
                // جستجو در تمام فیلدهای متنی
                return item.topic.toLowerCase().includes(lowerCaseSearchTerm) ||
                       item.description.toLowerCase().includes(lowerCaseSearchTerm) ||
                       item.location.toLowerCase().includes(lowerCaseSearchTerm) ||
                       item.period.toLowerCase().includes(lowerCaseSearchTerm) ||
                       item.details.toLowerCase().includes(lowerCaseSearchTerm);
            });
        }

        // پس از بارگذاری کامل صفحه
        window.onload = function() {
            // نمایش تمام کارت‌ها در ابتدا
            displayCards(culturalData);

            // اضافه کردن ایونت لیسنر به فیلد جستجو
            const searchInput = document.getElementById('search-input');
            searchInput.addEventListener('input', (event) => {
                const searchTerm = event.target.value;
                const filteredResults = filterData(searchTerm);
                displayCards(filteredResults);
            });
        };

    </script>
</body>
</html>

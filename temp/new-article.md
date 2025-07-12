---
order: 2
---



<html>

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Библейские тексты с детальными толкованиями</title>
  
  
  <link href="https://fonts.googleapis.com/css2?family=Noto+Serif:ital,wght@0,400;0,700;1,400;1,700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=New+Athena+Unicode&display=swap" rel="stylesheet">
  
  <style>
    /* Основные стили */
    * {

      margin: 0;
      padding: 0;
    }
    
    body {
      font-family: 'Noto Serif', serif;
      line-height: 1.6;
      background-color: #f8f5f0;
      color: #333;
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
      background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" opacity="0.05"><path d="M20,20 L80,20 L80,80 L20,80 Z" fill="none" stroke="%232c3e50" stroke-width="2"/></svg>');
      background-size: 100px;
    }
    
    /* Стиль для библейского текста */
    .scripture {
      background-color: #2c3e50;
      color: #ecf0f1;
      padding: 20px;
      border-radius: 8px;
      margin-bottom: 20px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      font-size: 18px;
    }
    
    .verse-container {
      margin-bottom: 25px;
      border-bottom: 1px dashed rgba(236, 240, 241, 0.3);
      padding-bottom: 15px;
    }
    
    .verse-header {
      display: flex;
      align-items: center;
      margin-bottom: 10px;
    }
    
    .verse-number {
     
      color: white;
      width: 32px;
      height: 32px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      margin-right: 10px;
      font-family: 'Playfair Display', serif;
    }
    
    sup {
      font-size: 0.8em;
      vertical-align: super;
      margin-right: 3px;
      color: #f1c40f;
    }
    
    /* Стили для кнопок */
    .toggle-btn {
      background-color: #3498db;
      color: white;
      border: none;
      padding: 8px 12px;
      margin: 5px 3px;
      border-radius: 4px;
      cursor: pointer;
      font-family: 'Noto Serif', serif;
      transition: all 0.3s;
      font-size: 14px;
    }
    
    .toggle-btn:hover {
      background-color: #2980b9;
      transform: translateY(-2px);
    }
    
    .toggle-btn.active {
      background-color: #1a5276;
      box-shadow: 0 2px 4px rgba(0,0,0,0.2);
    }
    
    /* Стили для скрываемого контента */
    .hidden-content {
      display: none;
      background-color: #fff;
      padding: 15px;
      border-radius: 8px;
      margin-top: 10px;
      border-left: 4px solid #3498db;
      color: #333;
      animation: fadeIn 0.4s;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-10px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .authors-container {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 10px;
    }
    
    .author-btn {
      background-color: #9b59b6;
      color: white;
      border: none;
      padding: 6px 10px;
      border-radius: 4px;
      cursor: pointer;
      transition: background-color 0.3s;
      font-size: 13px;
    }
    
    .author-btn:hover {
      background-color: #8e44ad;
    }
    
    .author-btn.active {
      background-color: #6c3483;
    }
    
    .author-content {
      display: none;
      padding: 10px;
      background-color: #f9f9f9;
      border-radius: 4px;
      margin-top: 10px;
      border-left: 2px solid #9b59b6;
    }
    
    .author-content.show {
      display: block;
      animation: fadeIn 0.3s;
    }
    
    .author-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 5px;
    }
    
    .author-name {
      font-weight: bold;
      color: #6c3483;
      font-family: 'Playfair Display', serif;
    }
    
    .author-date {
      font-size: 0.85em;
      color: #7f8c8d;
      font-style: italic;
    }
    
    .history-content, .map-content {
      padding: 15px;
    }
    
    .map-image {
      max-width: 100%;
      border-radius: 4px;
      margin-top: 10px;
      border: 1px solid #ddd;
    }
    
    /* Стили для переключателя языка */
    .language-switcher {
      margin-bottom: 20px;
      text-align: right;
      background-color: white;
      padding: 10px;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }
    
    .lang-btn {
      background: none;
      border: none;
      color: #2c3e50;
      cursor: pointer;
      padding: 5px 10px;
      font-family: 'Noto Serif', serif;
      transition: all 0.3s;
    }
    
    .lang-btn:hover {
      color: #3498db;
    }
    
    .lang-btn.active {
      font-weight: bold;
      border-bottom: 2px solid #3498db;
    }
    
    /* Специальные стили для разных языков */
    .cs {
      font-family: 'Ponomar Unicode', 'Noto Serif', serif;
      font-size: 1.1em;
    }
    
    .grc {
      font-family: 'New Athena Unicode', 'Noto Serif', serif;
      font-size: 1.2em;
    }
    
    .lat {
      font-style: italic;
    }
    
    /* Адаптивность */
    @media (max-width: 600px) {
      body {
        padding: 10px;
      }
      
      .scripture {
        padding: 15px;
        font-size: 16px;
      }
      
      .toggle-btn, .author-btn {
        font-size: 12px;
        padding: 6px 8px;
      }
    }
  </style>
</head>

<body>
  
  <div class="language-switcher">
    <button class="lang-btn active" data-lang="ru">Русский</button>
    <button class="lang-btn" data-lang="en">English</button>
    <button class="lang-btn" data-lang="cs">ЦСЯ</button>
  </div>
  
  
  <div class="scripture">
    
    <div class="verse-container" data-verse="1">
      <div class="verse-header">
        <div class="verse-number">1</div>
        <div class="verse-text">
          <span class="ru">В начале сотворил Бог небо и землю.</span>
          <span class="en" style="display:none;">In the beginning, God created the heavens and the earth.</span>
          <span class="cs" style="display:none;">Въ нача́тъкы сотвори́ Бо́гъ нб҃о и зе́млю.</span>
        </div>
      </div>
      
      <div class="verse-controls">
        <button class="toggle-btn" data-verse="1" data-type="commentary">Толкование</button>
        <button class="toggle-btn" data-verse="1" data-type="history">История</button>
        <button class="toggle-btn" data-verse="1" data-type="map">Карта</button>
        <button class="toggle-btn" data-verse="1" data-type="all">Раскрыть все</button>
      </div>
      
      
      <div class="verse-content">
        
        <div id="verse1-commentary" class="hidden-content" data-type="commentary">
          <div class="authors-container">
            <button class="author-btn" data-author="chrysostom" data-verse="1">Златоуст</button>
            <button class="author-btn" data-author="augustine" data-verse="1">Августин</button>
            <button class="author-btn" data-author="theophylact" data-verse="1">Феофилакт</button>
          </div>
          
          <div class="author-content" id="verse1-chrysostom">
            <div class="author-header">
              <span class="author-name">Святитель Иоанн Златоуст</span>
              <span class="author-date">IV век</span>
            </div>
            <p>"Слова «в начале» указывают, что мир имеет временное начало своего бытия. Не думай, будто бы что-либо из видимого безначально!"</p>
            <p>"Слово «сотворил» здесь означает создание из ничего, а не из готовой материи."</p>
          </div>
          
          <div class="author-content" id="verse1-augustine">
            <div class="author-header">
              <span class="author-name">Блаженный Августин</span>
              <span class="author-date">IV-V век</span>
            </div>
            <p>"Под «небом и землей» разумеется вся тварь, духовная и телесная. Начало здесь -- Слово Божие, через Которое всё сотворено."</p>
          </div>
          
          <div class="author-content" id="verse1-theophylact">
            <div class="author-header">
              <span class="author-name">Феофилакт Болгарский</span>
              <span class="author-date">XI век</span>
            </div>
            <p>"Началом называет Сына, как и евангелист Иоанн: «В начале было Слово». Сотворение неба и земли означает создание всей видимой и невидимой твари."</p>
          </div>
        </div>
        
        
        <div id="verse1-history" class="hidden-content" data-type="history">
          <h3>Исторический контекст</h3>
          <p>Космогонические представления Древнего Востока: в отличие от языческих мифов о борьбе богов, библейское повествование подчеркивает:</p>
          <ul>
            <li>Монотеизм - один Бог-Творец</li>
            <li>Сотворение из ничего (ex nihilo)</li>
            <li>Порядок и целесообразность творения</li>
          </ul>
          <p>Египетские и вавилонские космогонии описывали возникновение мира из хаоса через борьбу богов.</p>
        </div>
        
        
        <div id="verse1-map" class="hidden-content" data-type="map">
          <h3>Регион Ближнего Востока</h3>
          <p>Географический контекст книги Бытия</p>
          <img src="https://via.placeholder.com/600x300?text=Карта+Ближнего+Востока" 
               alt="Карта Ближнего Востока" 
               class="map-image">
          <p class="map-caption">Местоположение древних цивилизаций Месопотамии и Египта</p>
        </div>
      </div>
    </div>
    
    
    <div class="verse-container" data-verse="2">
      <div class="verse-header">
        <div class="verse-number">2</div>
        <div class="verse-text">
          <span class="ru">Земля же была безвидна и пуста, и тьма над бездною, и Дух Божий носился над водою.</span>
          <span class="en" style="display:none;">The earth was without form and void, and darkness was over the face of the deep. And the Spirit of God was hovering over the face of the waters.</span>
          <span class="cs" style="display:none;">Земля́ же бѣ неви́дима и неустро́ена, и тма́ верху́ бездны, и Дýхъ Бо́жій ноша́шеся верху́ воды́.</span>
        </div>
      </div>
      
      <div class="verse-controls">
        <button class="toggle-btn" data-verse="2" data-type="commentary">Толкование</button>
        <button class="toggle-btn" data-verse="2" data-type="history">История</button>
        <button class="toggle-btn" data-verse="2" data-type="map">Карта</button>
        <button class="toggle-btn" data-verse="2" data-type="all">Раскрыть все</button>
      </div>
      
      
      <div class="verse-content">
        
        <div id="verse2-commentary" class="hidden-content" data-type="commentary">
          <div class="authors-container">
            <button class="author-btn" data-author="basil" data-verse="2">Василий Великий</button>
            <button class="author-btn" data-author="ambrose" data-verse="2">Амвросий</button>
          </div>
          
          <div class="author-content" id="verse2-basil">
            <div class="author-header">
              <span class="author-name">Святитель Василий Великий</span>
              <span class="author-date">IV век</span>
            </div>
            <p>"Дух Божий носился как птица над яйцами, согревая их и пробуждая к жизни. Это образ животворящей силы Святого Духа, готовящей материю к последующему устроению."</p>
          </div>
          
          <div class="author-content" id="verse2-ambrose">
            <div class="author-header">
              <span class="author-name">Святитель Амвросий Медиоланский</span>
              <span class="author-date">IV век</span>
            </div>
            <p>"Тьма над бездною означает первичное состояние материи, еще не получившей формы. Дух Божий носился, оживотворяя и освящая водную стихию."</p>
          </div>
        </div>
        
        
        <div id="verse2-history" class="hidden-content" data-type="history">
          <h3>Исторический контекст</h3>
          <p>Представления о воде как первоэлементе:</p>
          <ul>
            <li>Вавилонский эпос "Энума элиш" - мир создан из водного хаоса</li>
            <li>Египетская мифология - Нун, первозданный океан</li>
            <li>Философия Фалеса Милетского - вода как начало всего</li>
          </ul>
          <p>Библейское повествование использует знакомые образы, но наполняет их монотеистическим смыслом.</p>
        </div>
        
        
        <div id="verse2-map" class="hidden-content" data-type="map">
          <h3>Древние ближневосточные цивилизации</h3>
          <img src="https://via.placeholder.com/600x300?text=Карта+древних+цивилизаций" 
               alt="Карта древних цивилизаций" 
               class="map-image">
          <p class="map-caption">Регионы Месопотамии, Египта и Леванта в древности</p>
        </div>
      </div>
    </div>
  </div>
  
  <script>
    // Функция для переключения языка
    function switchLanguage(lang) {
      // Скрываем все языковые блоки
      document.querySelectorAll('.verse-text > span').forEach(el => {
        el.style.display = 'none';
      });
      
      // Показываем выбранный язык
      document.querySelectorAll(`.verse-text .${lang}`).forEach(el => {
        el.style.display = 'block';
      });
      
      // Обновляем активную кнопку
      document.querySelectorAll('.lang-btn').forEach(btn => {
        btn.classList.remove('active');
      });
      document.querySelector(`.lang-btn[data-lang="${lang}"]`).classList.add('active');
    }
    
    // Функция для переключения контента
    function toggleContent(verse, type) {
      const contentId = `verse${verse}-${type}`;
      const content = document.getElementById(contentId);
      
      if (!content) return;
      
      // Если нажата кнопка "Раскрыть все"
      if (type === 'all') {
        // Находим все блоки контента для этого стиха
        const verseContainer = document.querySelector(`.verse-container[data-verse="${verse}"]`);
        const allContents = verseContainer.querySelectorAll('.hidden-content');
        
        // Переключаем отображение всех блоков
        const isAnyVisible = Array.from(allContents).some(el => el.style.display === 'block');
        
        allContents.forEach(el => {
          el.style.display = isAnyVisible ? 'none' : 'block';
        });
        
        // Обновляем текст кнопки
        const allBtn = verseContainer.querySelector('.toggle-btn[data-type="all"]');
        allBtn.textContent = isAnyVisible ? 'Раскрыть все' : 'Скрыть все';
        
        return;
      }
      
      // Для обычных кнопок
      content.style.display = content.style.display === 'none' ? 'block' : 'none';
      
      // Обновляем состояние кнопки
      const btn = document.querySelector(`.toggle-btn[data-verse="${verse}"][data-type="${type}"]`);
      if (content.style.display === 'block') {
        btn.classList.add('active');
      } else {
        btn.classList.remove('active');
      }
    }
    
    // Функция для показа толкования конкретного автора
    function showAuthorCommentary(verse, author) {
      // Скрываем все комментарии для этого стиха
      const verseContainer = document.querySelector(`.verse-container[data-verse="${verse}"]`);
      verseContainer.querySelectorAll('.author-content').forEach(el => {
        el.classList.remove('show');
      });
      
      // Показываем выбранного автора
      const authorContent = document.getElementById(`verse${verse}-${author}`);
      if (authorContent) {
        authorContent.classList.add('show');
      }
      
      // Обновляем состояние кнопки
      verseContainer.querySelectorAll('.author-btn').forEach(btn => {
        btn.classList.remove('active');
      });
      event.target.classList.add('active');
    }
    
    // Инициализация
    document.addEventListener('DOMContentLoaded', () => {
      // Обработчики для кнопок языка
      document.querySelectorAll('.lang-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          switchLanguage(btn.dataset.lang);
        });
      });
      
      // Обработчики для кнопок контента
      document.querySelectorAll('.toggle-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const verse = btn.dataset.verse;
          const type = btn.dataset.type;
          toggleContent(verse, type);
        });
      });
      
      // Обработчики для кнопок авторов
      document.querySelectorAll('.author-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const verse = btn.dataset.verse;
          const author = btn.dataset.author;
          showAuthorCommentary(verse, author);
        });
      });
      
      // По умолчанию показываем русский язык
      switchLanguage('ru');
    });
  </script>
</body>

</html>
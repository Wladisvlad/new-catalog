---
order: 3
---

<html>
<style>
/* Стили для компактных кнопок */
.small-btn {
  display: inline-block;
  padding: 2px 8px;
  margin-left: 10px;
  font-size: 0.85em;
  background: #f0f0f0;
  border: 1px solid #ddd;
  border-radius: 3px;
  cursor: pointer;
  text-decoration: none;
  color: #333;
}

.small-btn:hover {
  background: #e0e0e0;
}

/* Стили для сворачиваемых блоков */
.collapsible {
  display: none;
  padding: 10px;
  margin: 10px 0;
  border-left: 3px solid #3498db;
  background-color: #f8f9fa;
}

.collapsible-header {
  font-weight: bold;
  cursor: pointer;
  margin-bottom: 5px;
}

/* Стили для выбора перевода */
.translation-switcher {
  margin-bottom: 15px;
  padding: 8px;
  background: #f5f7f9;
  border-radius: 4px;
}

.translation-btn {
  padding: 4px 8px;
  margin-right: 5px;
  border: none;
  background: #e0e7ff;
  border-radius: 3px;
  cursor: pointer;
}

.translation-btn.active {
  background: #3498db;
  color: white;
}
</style>

<!-- Выбор перевода -->
<div class="translation-switcher">
  <button class="translation-btn active" data-lang="synodal">Синодальный</button>
  <button class="translation-btn" data-lang="csya">ЦСЯ</button>
  <button class="translation-btn" data-lang="lxx">LXX</button>
</div>

<!-- Стих 1 -->
<sup>1</sup> <span class="translation synodal">В начале сотворил Бог небо и землю.</span>
<span class="translation csya" style="display:none">Въ нача́тъкы сотвори́ Бо́гъ нб҃о и зе́млю.</span>
<span class="translation lxx" style="display:none">Ἐν ἀρχῇ ἐποίησεν ὁ θεὸς τὸν οὐρανὸν καὶ τὴν γῆν.</span>

<!-- Кнопки управления -->
<a href="javascript:void(0)" class="small-btn toggle-commentary" data-verse="1">Толкования</a>
<a href="javascript:void(0)" class="small-btn toggle-map" data-verse="1">Карты</a>

<!-- Блок с толкованиями -->
<div id="commentary-1" class="collapsible">
  <div class="collapsible-header">Автор 1</div>
  <div>Текст толкования...</div>
  
  <div class="collapsible-header">Автор 2</div>
  <div>Текст толкования...</div>
  
  <div class="collapsible-header">Автор 3</div>
  <div>Текст толкования...</div>
  <a href="./_index">[подробнее]</a>
</div>

<!-- Блок с картами -->
<div id="map-1" class="collapsible">
  <img src="./temp.jpeg" width="421" height="600" alt="Карта">
</div>

<script>
// Функция для переключения переводов
document.querySelectorAll('.translation-btn').forEach(btn => {
  btn.addEventListener('click', function() {
    // Убираем активный класс со всех кнопок
    document.querySelectorAll('.translation-btn').forEach(b => {
      b.classList.remove('active');
    });
    
    // Добавляем активный класс текущей кнопке
    this.classList.add('active');
    
    // Скрываем все переводы
    document.querySelectorAll('.translation').forEach(t => {
      t.style.display = 'none';
    });
    
    // Показываем выбранный перевод
    const lang = this.dataset.lang;
    document.querySelector(`.translation.${lang}`).style.display = 'inline';
  });
});

// Функция для переключения блоков
document.querySelectorAll('.small-btn').forEach(btn => {
  btn.addEventListener('click', function() {
    const verse = this.dataset.verse;
    const type = this.classList.contains('toggle-commentary') ? 'commentary' : 'map';
    const target = document.getElementById(`${type}-${verse}`);
    
    // Переключаем отображение блока
    if (target.style.display === 'block') {
      target.style.display = 'none';
      this.textContent = this.textContent.replace('Скрыть', 'Показать');
    } else {
      target.style.display = 'block';
      this.textContent = 'Скрыть ' + this.textContent.replace('Показать', '');
    }
  });
});

// Функция для сворачивания/разворачивания внутри блоков
document.querySelectorAll('.collapsible-header').forEach(header => {
  header.addEventListener('click', function() {
    const content = this.nextElementSibling;
    content.style.display = content.style.display === 'none' ? 'block' : 'none';
  });
});
</script>
</html>
ссылка на [генератор](http://dataurl.net/#dataurlmaker), способы работы и применения, [кенаюз](http://caniuse.com/datauri).

Загружать ли всю графику так? — Нет! Такой способ идеален для элементов интерфейса, для своевременной загрузки некоторых типов данных (шрифтов, распорок)

[Генератор спрайтов](http://spritegen.website-performance.org/)
[Создание спрайтов из командной строки](http://habrahabr.ru/post/110002/)

Оптимизировать изображения в ПНГ лучше всего при помощи [этого](http://tinypng.org/) сервиса. Уменьшение файлов до 80%! Проблема его в том, что он сокращает палитру и на некоторых градиентах может быть заметно резкое изменение цвета, а полупрозрачность, которая применяется в оптимизированных изображениях, неправильно отрисовывается фотошопом заливкой чёрного цвета.

Изображения для пользовательского интерфейса выгодно склеивать в один файл — не будет тратиться время на общение браузера с сервером, не будет загромождаться файловая система сайта. Проблема может возникнуть при кешировании этого объединённого изображения. Устранить её можно, указывая изменённый адрес к изображению при каждом изменении `url(../images/background.jpg?16549)`.

Проблемы с кешированием лишён другой способ загрузки графики — использование `data:url` — являющийся также отличным способом для своевременной отрисовки кодируемых данных. К примеру, если закодировать небольшие изображения (которые будут использоваться только один раз), то браузер не будет делать дополнительный запрос для их загрузки. В то же время, время до отображения страницы будет увеличено на нужное для раскодирования изображений.

то на их загрузку не будет тратиться дополнительное время, при этом они будут отрисовываться сразу.

В свою очередь, появляется проблема с необходимостью кодировать изображение заново всякий раз при изменении.

[Мнение Николаса Закаса про это](http://www.nczonline.net/blog/2010/07/06/data-uris-make-css-sprites-obsolete/)   
[Разбор от смешинмагазина](http://coding.smashingmagazine.com/2010/03/26/css-sprites-useful-technique-or-potential-nuisance/)   
[Исследование скорости загрузки датаюри (неактуальное)](http://habrahabr.ru/post/79262/)   
[Применение датаюри](http://habrahabr.ru/post/116538/)   
[Про кроссбарузерное использование](http://jonraasch.com/blog/css-data-uris-in-all-browsers)

ИЕ7 и старше не понимают данные в таком формате, им нужно отдавать обычные картинки:

```css
.element {
	/*background: url(/img/bg_element.png);*//* — чтобы не забыть расположение оригинального изображения */
	background: url('data:...');
}

.ie7 .element {
	background: url(/img/bg_element.png);
}
```

Чтобы реализовать работу с одним спрайтом, закодированном в цсс нужно выделить общий класс с пиктограммами, от него будет наследоваться фон, дополнительными классами настраивается положение фона.

## Всё подряд

[Какой тип документа выбирать для рассылок.](https://www.campaignmonitor.com/blog/post/4278/HTML5-vs-XHTML1-the-right-doctype-to-use-in-html-email)

Рекомендуется использовать `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional //EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">`, чтобы использовать устаревшие, но полезные элементы и их атрибуты.

[Общее о вёрстке рассылок](http://habrahabr.ru/post/157309/)

Каждая новая вложенная таблица **обнуляет стили родительской**, стили ей нужно задавать заново.

Обязательно проверять **правильность работы** всех ссылок. Тундербёрд неверно работал со ссылками, у которых были символы `%7С` == `|`, например.

Для больших изображений со ссылками следует использовать **карты ссылок**, их можно создавать при помощи [специальных редакторов](http://tools.samsonpost.ru/image-map/).

[Инструмент](http://backgrounds.cm/) для задания фоновых изображений и [красивых кнопок](http://buttons.cm/).

> Используйте только таблицы, встроенные стили, переопределяйте всё (например, `font-family` указывайте для каждого элемента). [#](https://twitter.com/devongovett/status/361603759878574080)

> Не пытайтесь использовать `margin` для всего, Оутлук будет игнорировать их. `color: #000001` вместо чёрного поможет сохранить чёрный в Гмайле. [#](https://twitter.com/devongovett/status/361603942473404416)

> Теги `style` вырезаются большинством почтовых клиентов. Используйте атрибут для стилизации. Прогрессивное улучшение для :active и прочего. [#](https://twitter.com/devongovett/status/361604328378740736)

> Another email protip: if you embed your images as attachments (using cid: links) instead of HTTP, you get around image blocking until click. [#](https://twitter.com/devongovett/status/361606975387205632)

> I used this Node module to automatically convert CSS files to inline styles. Works well. https://github.com/LearnBoost/juice [#](https://twitter.com/devongovett/status/361607442536202241)

Нельзя оставлять не закрытыми комментарии в блоке внутренних стилей на странице — **мейлру** не отображает страницу совсем.

**ГМэйл** устанавливает свой цвет для ссылок, его следует забивать импотентом и это не всегда работает. Можно применять цвет по принципу `#000001 == #000`.

В названиях файлов **нельзя использовать пробелы** — некоторые почтовики (Гмайл, например) — заменяют их на другие знаки (`+`), отчего этот файл не загрузится.

Не пишите код письма **в одну строку** — неоднократно сталкивались с ситуацией, когда почтовый клиент (_Тхундербирд_) разбивал её в неудачном месте, и в письме из-за этого появлялся текст `< p>` вместо нормального начала абзаца.

Высоту строки лучше задавать в процентах: `line-height: 1.3;` == `line-height: 130%;`, не все почтовики понимают. Также [почитать](http://stackoverflow.com/questions/8980956/line-height-not-working-in-outlook-2010-for-html-email).

Сделать отступ между несколькими элементами поможет такая конструкция:
```html
<table width="650" cellspacing="0" cellpadding="0" border="0">
	<tr>
		<td valign="top" height="10px" style="padding-top: 0;"></td>
	</tr>
</table>
```

Вообще, **любое выравнивание** лучше всего выполнять при помощи таблиц и их возможностей — `margin`, `padding`, `float` чаще всего будут вырезаны почтовыми клиентами.

Будьте внимательны при **написании свойств.** `margin: 10px;;` может игнорироваться.

Если первым тегом в документе идёт `<style/>`, МайлРу и Оутлук не отображают содержимое письма.


## Оутлук

[Про движок рендеринга в оутлуке 2010](http://stackoverflow.com/a/12019156)

Если требуется что-то скрыть в оутлуке, можно применять специальное объявление `mso-hide:all;`.

Слишком большие картинки следует **разделять на несколько небольших**, так как большие могут не загрузиться. Путём продолжительного тестирования было установлено, что относительно **безопасная высота** одиночного изображения для Оутлука 2010 (а именно в нём обнаружилась проблема с высотой) — `1600px`.

Нежелательно задавать значение свойства `display` отличное от стандартного для элемента.
[оутлуки, похоже, не поддерживают дисплей](http://msdn.microsoft.com/en-us/library/aa338201.aspx#Word2007MailHTMLandCSS_Core)

Если с какой-либо из сторон таблицы появилась **однопиксельная полоса**, выходящяя за пределы её заданной ширины, проверьте, нет ли лишнего `colspan`.

[Поддержка технологий почтовиками](http://www.campaignmonitor.com/css/)

Порядок указания значений свойств в оутлуке: слева, сверху, справа, снизу.

Атрибут `fillcolor` позволяет залить всю область `rect` цветом.

Чтобы отобразить фоновое изображение, нужно использовать специальную разметку векторных изображений — [ВМЛ](http://msdn.microsoft.com/en-us/library/bb264048%28v=vs.85%29.aspx)

[Фоновое изображение оутлука](http://stackoverflow.com/a/8914220)

[Про фоновые изображения с примерами](http://www.emailonacid.com/blog/details/C13/emailology_vector_markup_language_and_backgrounds)

[Фоновые изображения для оутлуков](http://www.campaignmonitor.com/blog/post/3363/updated-applying-a-background-image-to-html-email/)

Нужно добавить следующее объявление:
```html
<html xmlns:v="urn:schemas-microsoft-com:vml">
```

Если нужно добавить фоновое изображение для страницы:
```html
<body style="margin:0; padding:0; width:100% !important;">

<!--[if gte mso 9]>
<v:background fill="t">
   <v:fill type="tile" src="http://www.example.com/background_image.jpg" />
</v:background>
<![endif]-->

<table width="100%" cellpadding="0" cellspacing="0" border="0">
  <tr>
    <td align="center" background="http://www.example.com/background_image.jpg">
    <table width="600" cellpadding="0" cellspacing="0" border="0">
        <tr>
          <td>
             <p> If you can see this over the image, background images are successful. </p>
           </td>
        </tr>
      </table>
    </td>
  </tr>
</table>

</body> 
```

Если нужно добавить фоновое изображение для ячейки:
```html
...
<td background="http://www.example.ru/mail/bg.jpg" width="790" style="text-align: left;" valign="top">
	<!--[if gte mso 9]>
		<v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" fillcolor="#bada55" stroke="false" style="width:790px;height:572px;">
			<v:fill type="tile" src="http://www.example.ru/mail/bg.jpg" />
			<v:textbox style="mso-fit-shape-to-text:true" inset="245px,0,25px,60px">
	<![endif]-->
	<div style="padding-left: 245px;">
		<p style="display: block; font-family: 'arial'; font-size: 24px; line-height: 30px; font-weight: bold; margin: 95px 0 16px; color: #c5252a; padding: 0;">
			УВАЖАЕМЫЕ ДРУЗЬЯ,<br />КОЛЛЕГИ, ПАРТНЁРЫ!
		</p>
		<p style="display: block; font-family: 'arial'; font-size: 14px; line-height: 21px; margin: 0; padding: 0;">
			Поздравляем с наступающими майскими праздниками!
		</p>
	</div>
	<!--[if gte mso 9]>
			</v:textbox>
		</v:rect>
	<![endif]-->
</td>
...
```

[Генератор разметки фоновых изображений](http://backgrounds.cm/)

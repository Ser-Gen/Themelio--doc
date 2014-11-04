# Опыт разработки

## [Гитхаб](http://markdotto.com/2014/07/23/githubs-css/)

> As promised, here's a huge post on nearly everything you'd probably want to know about @github's CSS. [#](https://twitter.com/mdo/status/492062299725656064).

[Перевод](http://habrahabr.ru/post/235701/).

[Доклад](https://speakerdeck.com/jonrohan/githubs-css-performance) о производительности стилей Гитхаба

- `scss`;
- не используется автопрефиксер и карты кода;
- методология стремится к `OOCSS`;
- тесты стилей;
- стили разделены на два файла, чтобы не превышать [максимальное число селекторов ИЕ9](http://blogs.msdn.com/b/ieinternals/archive/2011/05/14/10164546.aspx);
- стили рассортированы по файлам, которые автоматически сливаются в один файл в алфавитном порядке, отчего должны быть независимыми;
- используют графики для анализа изменений в коде (объём, селекторы);
- [документация](https://github.com/styleguide/css/);
- собственный стилевой фреймворк — `Primer` (пока закрытый).


## [Лонли плэнет](http://ianfeather.co.uk/css-at-lonely-planet/)

> Inspired by @mdo’s Github CSS post, I wrote about CSS at Lonely Planet [#](https://twitter.com/ianfeather/status/492268399431782400).


## [Кодепэн](http://codepen.io/chriscoyier/blog/codepens-css)

> CodePen’s CSS (Inspired by @mdo and @ianfeather’s posts) [#](https://twitter.com/chriscoyier/status/494512481088180224).


## [Групон](http://mikeaparicio.com/2014/08/10/css-at-groupon/)

[Доклад про внутренний стилевой фреймворк](https://speakerdeck.com/peruvianidol/toolstrap-a-css-framework-for-groupon-internal-tools).


## [Платформатек](http://blog.plataformatec.com.br/2014/08/css-at-plataformatec/)


## [Буфер](http://blog.brianlovin.com/buffers-css/)


## [Медиум](https://medium.com/@fat/mediums-css-is-actually-pretty-fucking-good-b8e2a6c78b06)

> If you're into nerd shit, I wrote a thing about how Medium's CSS is actually pretty chill. [#](https://twitter.com/fat/status/505057253192249344)

> How to make your CSS less garbage. By @fat [#](https://twitter.com/Medium/status/505148326660935680)


## [Трело](http://blog.trello.com/refining-the-way-we-structure-our-css-at-trello/)

[Здесь](http://blog.fogcreek.com/how-we-make-trello/) про процесс разработки, [тут](http://blog.trello.com/how-we-made-our-new-landing-pages-fast-a-grand-journey/) про то, как они делали оптимизированными рекламные страницы, [там](http://blog.fogcreek.com/we-spent-a-week-making-trello-boards-load-extremely-fast-heres-how-we-did-it/) про оптимизацию интерфейса.

- `less`;
- [CSSShrink](http://cssshrink.com/)
- без гранта или галпа;
- стили разделены по файлам;
- модульные стили, отказ от каскада;
- классы с префиксом `js-` для добавления интерактивности;
- правила написания стилей;
- [пиктограммы выводятся шрифтом](http://blog.fogcreek.com/trello-uses-an-icon-font-and-so-can-you/);
- [не стараются](http://blog.fogcreek.com/project-asteroid-gracefully-dropping-support-for-dinosaur-browsers-in-trello/) поддерживать старые браузеры;
- не используют автопрефиксер, валидацию стилей, пиктограммы в свг (пусть и хотят), `normalize.css`;
- думают над внедрением множества префиксов для типов объявлений, вдохновившись [Медиумом](https://gist.github.com/fat/a47b882eb5f84293c4ed);
- изучают [селекторы по атрибутам](http://glenmaddern.com/articles/introducing-am-css) для модульности.


## Твитер

> I could write about CSS at Twitter, but I don't want to give children nightmares. [#](https://twitter.com/necolas/status/498575905057292289)

> One does not simply "refactor" 700kb of CSS. [#](https://twitter.com/necolas/status/498577671203209216)


## [Багзнэг](https://bugsnag.com/blog/bugsnags-css-architecture)

> SMACSS, Atomic Design, BEM? How about a little of each? Check out my post on Bugsnag's CSS Architecture [#](https://twitter.com/maxluster/status/510205605827452928)


## [Джост](http://dev.ghost.org/css-at-ghost/)

> I like that @TryGhost use $red over $error in their css. We do the same. Much simpler. [#](https://twitter.com/ianfeather/status/529627985088086016)

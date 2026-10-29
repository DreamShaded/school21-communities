---
layout: simple-slide
level: 1
contentAlign: center
contentPos: center
---

<div class="vote-chip" aria-hidden="true"><span class="vote-blink">●</span> VOTE</div>

## Поднимите руки

<p class="vote-q">Кто за последний год рассказывал о своей работе<br>кому-то <span class="hl">вне команды</span>?</p>

<div class="vote-opts">
  <div class="card" v-click><div class="ico"><tabler-presentation /></div>Доклад</div>
  <div class="card" v-click><div class="ico"><tabler-pencil /></div>Пост</div>
  <div class="card" v-click><div class="ico"><tabler-message-circle /></div>Ответ в чате</div>
  <div class="card" v-click><div class="ico"><tabler-coffee /></div>Разговор на митапе</div>
</div>

<p class="vote-all" v-click>Считается всё</p>

<style scoped>
/* голосование зала: вопрос крупно, варианты всплывают карточками, внизу вывод */
.vote-chip {
  position: absolute;
  top: 3.6rem;
  right: 3.5rem;
  font-family: var(--pa-font-display);
  font-size: 1rem;
  line-height: 1;
  color: var(--pa-yellow);
}
.vote-blink {
  color: var(--pa-red);
  animation: vote-blink 1s steps(1, end) infinite;
}
.vote-q {
  font-size: 1.75rem;
  line-height: 1.35;
  margin: 0.5rem 0 1.75rem;
}
.hl {
  color: var(--lvl-accent);
  text-shadow: 0 0 0.6rem color-mix(in srgb, var(--lvl-accent) 55%, transparent);
}
.vote-opts {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
  width: 100%;
}
.vote-opts .card {
  text-align: center;
}
.vote-all {
  margin-top: 1.5rem;
  font-family: var(--pa-font-pixel);
  font-weight: 600;
  font-size: 2rem;
  color: var(--pa-lime);
}
@keyframes vote-blink {
  0%,
  60% {
    opacity: 1;
  }
  61%,
  100% {
    opacity: 0.2;
  }
}
@media (prefers-reduced-motion: reduce) {
  .vote-blink {
    animation: none;
  }
}
</style>
---
layout: two-cols
level: 1
leftWidth: 50%
rightAlign: center
---

## WHOAMI

<div class="select-chip" aria-hidden="true">SELECT PLAYER</div>

<v-clicks>
  <ul class="perks">
    <li>Влюблён во фронтенд</li>
    <li>Senior FE =&gt; DSE в Сбере</li>
    <li>Студент магистратуры ИТМО</li>
    <li>Вхожу в ПК HolyJS, Сбера, MoscowCSS</li>
    <li>Орг MoscowCSS</li>
  </ul>
</v-clicks>

<PlayerStats :step="$clicks" class="stats" />

::right::

<WhoAmI :images="['/images/whoami/1.jpg', '/images/whoami/2.jpg', '/images/whoami/3.jpg']" alt="Рома Троицкий на митапах и конференциях" />

<style scoped>
/* экран выбора персонажа: перки открываются по кликам, каждая шкала статов
   заполняется сразу целиком на своём пункте */
.select-chip {
  position: absolute;
  top: 3.6rem;
  left: 13rem;
  font-family: var(--pa-font-display);
  font-size: 1rem;
  line-height: 1;
  color: var(--pa-yellow);
  animation: who-blink 1.1s steps(1, end) infinite;
}
.perks {
  margin: 0.2rem 0 0;
}
.perks li {
  padding: 0.05rem 0 0.05rem 1.5rem;
  margin-bottom: 0.2rem;
}
.perks li.slidev-vclick-current {
  color: var(--pa-yellow);
  text-shadow: 0 0 0.5rem rgba(255, 225, 62, 0.45);
}
.stats {
  margin-top: auto;
}
@keyframes who-blink {
  0%,
  60% {
    opacity: 1;
  }
  61%,
  100% {
    opacity: 0.25;
  }
}
@media (prefers-reduced-motion: reduce) {
  .select-chip {
    animation: none;
  }
}
</style>
---
layout: simple-slide
level: 1
---

## Как меня начали знать

<div class="road">
  <div class="stop" v-click="1">
    <span class="lvl">LV 1</span>
    <div class="card">Первая работа: Глеб Михеев выпытывает, чего я не знаю</div>
  </div>
  <span class="arrow" v-click="1" aria-hidden="true">▶</span>
  <div class="stop" v-click="2">
    <span class="lvl">LV 2</span>
    <div class="card">Совет: взял знания у сообщества — верни свой опыт</div>
  </div>
  <span class="arrow" v-click="2" aria-hidden="true">▶</span>
  <div class="stop" v-click="3">
    <span class="lvl">LV 3</span>
    <div class="card ok">Зовут на интересные проекты</div>
  </div>
</div>

<div class="hh" v-click="4">
  <span class="hh-url">hh.ru/resume/???</span>
  <span class="hh-code">404</span>
  <span class="sub">резюме нет, работу не ищу — зовут дальше</span>
</div>

<style scoped>
/* путь игрока: три остановки по кликам, внизу «битая ссылка» на резюме */
.road {
  display: grid;
  grid-template-columns: 1fr auto 1fr auto 1fr;
  align-items: end;
  gap: 0.75rem;
  width: 100%;
  margin-top: 1.5rem;
}
.stop {
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
}
.stop .card {
  min-height: 6.5rem;
  display: flex;
  align-items: center;
}
.lvl {
  font-family: var(--pa-font-display);
  font-size: 1rem;
  color: var(--lvl-accent);
}
.road .arrow {
  align-self: center;
  margin-top: 1.6rem;
  font-size: 1.5rem;
  color: var(--lvl-accent);
  text-shadow: 0 0 0.6rem var(--lvl-accent);
}
.hh {
  display: flex;
  align-items: baseline;
  gap: 1.25rem;
  margin-top: 2.5rem;
  padding: 0.9rem 1.2rem;
  background: rgba(7, 4, 15, 0.82);
  box-shadow:
    0 -3px 0 0 var(--pa-line),
    0 3px 0 0 var(--pa-line),
    -3px 0 0 0 var(--pa-line),
    3px 0 0 0 var(--pa-line);
}
.hh-url {
  font-size: 1.25rem;
  color: var(--pa-text-dim);
  text-decoration: line-through;
}
.hh-code {
  font-family: var(--pa-font-display);
  font-size: 2rem;
  line-height: 1;
  color: var(--pa-red);
  text-shadow: 0.1875rem 0.1875rem 0 #4a0f2c;
}
</style>

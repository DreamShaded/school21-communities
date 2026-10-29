---
layout: interjection
level: 5
transition: slide-up
---

<TextBig>
  Join game
</TextBig>
---
layout: two-cols
level: 5
leftWidth: 45%
rightAlign: center
---

## Слот в календаре

<v-clicks>

- Как под спорт: повторяющийся блок
- Хватит часа-двух в неделю
- Без слота «когда-нибудь» не наступает

</v-clicks>

::right::

<div class="week" aria-label="Неделя в календаре: в четверг вечером повторяющийся блок «сообщество»">
  <span v-for="d in ['ПН', 'ВТ', 'СР', 'ЧТ', 'ПТ']" :key="d" class="day">{{ d }}</span>
  <template v-for="r in 5" :key="r">
    <i v-for="d in 5" :key="d" class="slot" :class="{ busy: (r + d) % 3 === 0, mine: r === 4 && d === 4 }" />
  </template>
</div>
<p class="legend"><i class="sw" /> сообщество, 1–2 ч</p>

<style scoped>
/* неделя пиксельными клетками: занятые слоты тусклые, один — «сообщество», цветом уровня */
.week {
  display: grid;
  grid-template-columns: repeat(5, 3.5rem);
  gap: 0.4rem;
}
.day {
  font-family: var(--pa-font-pixel);
  font-weight: 600;
  font-size: 1.25rem;
  text-align: center;
  color: var(--pa-text-dim);
}
.slot {
  height: 2.75rem;
  background: rgba(28, 23, 48, 0.85);
}
.slot.busy {
  background: #3a3160;
}
.slot.mine {
  background: var(--lvl-accent);
  box-shadow: 0 0 1rem var(--lvl-accent);
}
.legend {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  margin-top: 1rem;
}
.sw {
  width: 1rem;
  height: 1rem;
  background: var(--lvl-accent);
}
</style>
---
layout: two-cols
level: 5
leftWidth: 55%
rightAlign: center
---

## Где искать своё

<v-clicks>

- Чаты по стеку, который вы и так используете
- Митапы в своём городе и онлайн
- Школа 21 — уже сообщество: начните с соседей
- Критерий: интересно читать, даже без пользы

</v-clicks>

::right::

<div class="qr-box">
  <span class="qr-tab" aria-hidden="true">MAP</span>
  <div class="qr-bezel">
    <img src="/images/qr/it-communities-light.svg" alt="QR-код статьи https://vzhyx.io/articles/how-to/it-communities/">
  </div>
  <p class="qr-cap">Мои любимые сообщества</p>
</div>
---
layout: simple-slide
level: 5
---

## Тема для первого доклада

<div class="quests">
  <div class="quest" v-click><span class="stars">★</span>Задача, на которой застряли и разобрались</div>
  <div class="quest" v-click><span class="stars">★</span>Ошибка, на которую ушёл день</div>
  <div class="quest" v-click><span class="stars">★★</span>Сравнение инструментов, которое вы уже сделали для себя</div>
  <div class="quest" v-click><span class="stars">★★</span>Пять минут lightning talk на внутреннем митапе</div>
</div>

<p class="after" v-click>Вы знаете то, чего не знает человек на год младше вас</p>

<style scoped>
/* доска квестов: от простого к посложнее, звёзды — сложность */
.quests {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  width: 100%;
  margin-top: 0.75rem;
}
.quest {
  display: flex;
  align-items: center;
  gap: 0.9rem;
  min-height: 5rem;
  padding: 0.75rem 1rem;
  background: var(--dd-card-bg);
  box-shadow:
    0 -3px 0 0 var(--dd-card-border),
    0 3px 0 0 var(--dd-card-border),
    -3px 0 0 0 var(--dd-card-border),
    3px 0 0 0 var(--dd-card-border);
}
.stars {
  flex: none;
  width: 2.5rem;
  color: var(--pa-yellow);
  text-shadow: 0 0 0.4rem rgba(255, 225, 62, 0.55);
}
.after {
  margin-top: 1.75rem;
  font-family: var(--pa-font-pixel);
  font-weight: 600;
  font-size: 1.875rem;
  line-height: 1.15;
  color: var(--lvl-accent);
}
</style>

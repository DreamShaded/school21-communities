---
layout: interjection
level: 4
transition: slide-up
---

<TextBig>
  Полигон
</TextBig>
---
layout: simple-slide
level: 4
---

## Что здесь качается

<div class="cards skills">
  <div class="card" v-click><div class="ico"><tabler-bulb /></div>Объяснять сложное просто</div>
  <div class="card" v-click><div class="ico"><tabler-mood-sad-dizzy /></div>Ошибаться публично</div>
  <div class="card" v-click><div class="ico"><tabler-message-question /></div>Отвечать на возражения из зала</div>
  <div class="card" v-click><div class="ico"><tabler-users-group /></div>Организовывать людей, которые вам не подчиняются</div>
</div>

<style scoped>
.skills {
  grid-template-columns: 1fr 1fr;
  gap: 1.25rem;
  width: 100%;
  margin-top: 1rem;
}
.skills .card {
  display: flex;
  align-items: center;
  gap: 1rem;
  min-height: 6rem;
  font-size: 1.25rem;
}
.skills .card .ico {
  margin: 0;
}
</style>
---
layout: simple-slide
level: 4
---

## Цена ошибки

<div class="cost">
  <div class="tile no" v-click="1">
    <div class="t-ico"><tabler-briefcase /></div>
    <h3>На работе</h3>
    <ul>
      <li>Проект</li>
      <li>Репутация</li>
      <li>Карьера</li>
    </ul>
  </div>
  <div class="tile ok" v-click="2">
    <div class="t-ico"><tabler-device-gamepad-2 /></div>
    <h3>В сообществе</h3>
    <ul>
      <li>Неловкий вопрос из зала</li>
      <li>Завтра следующий митап</li>
    </ul>
  </div>
</div>

<p class="respawn" v-click="3"><span class="tag">RESPAWN</span> облажаться можно, но дешевле</p>

<style scoped>
.cost {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.75rem;
  width: 100%;
  margin-top: 0.75rem;
}
.cost h3,
.cost ul {
  margin: 0;
}
.respawn {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-top: 1.75rem;
  font-size: 1.375rem;
}
.tag {
  padding: 0.35rem 0.6rem 0.3rem;
  font-family: var(--pa-font-display);
  font-size: 1rem;
  line-height: 1;
  color: #07040f;
  background: var(--lvl-accent);
}
</style>

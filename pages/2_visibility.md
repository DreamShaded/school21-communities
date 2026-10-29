---
layout: interjection
level: 2
transition: slide-up
---

<TextBig>
  Видимость
</TextBig>
---
layout: simple-slide
level: 2
---

## Кто влияет на вашу карьеру

<div class="cards judges">
  <div class="card" v-click><div class="ico"><tabler-user-search /></div>Нанимающий менеджер</div>
  <div class="card" v-click><div class="ico"><tabler-building /></div>Руководитель соседнего отдела</div>
  <div class="card" v-click><div class="ico"><tabler-microphone-2 /></div>Организатор конференции</div>
</div>

<div class="card no verdict" v-click>
  <div class="ico"><tabler-code-off /></div>
  <div><b>Ваш код никто из них не читал.</b><br><span class="sub">Они видят только то, что вы показали снаружи</span></div>
</div>

<style scoped>
.judges {
  grid-template-columns: repeat(3, 1fr);
  margin-top: 1rem;
}
.judges .card {
  min-height: 8rem;
}
.verdict {
  display: flex;
  align-items: center;
  gap: 1.25rem;
  margin-top: 2rem;
  padding: 1rem 1.25rem;
}
.verdict .ico {
  margin: 0;
  font-size: 2.5rem;
}
.verdict b {
  color: var(--pa-text);
  font-size: 1.375rem;
}
</style>
---
layout: simple-slide
level: 2
---

## Код пишет модель

<div class="duel">
  <div class="tile no" v-click="1">
    <div class="t-ico"><tabler-file-code /></div>
    <h3>Видно в коде</h3>
    <ul>
      <li>Что написано</li>
      <li>Модель пишет похоже</li>
    </ul>
  </div>
  <div class="vs" aria-hidden="true">VS</div>
  <div class="tile ok" v-click="2">
    <div class="t-ico"><tabler-bulb /></div>
    <h3>Видно снаружи</h3>
    <ul>
      <li>Как вы думаете</li>
      <li>Как объясняете</li>
      <li>Как решаете</li>
    </ul>
  </div>
</div>

<p class="after" v-click="3">Это видно только публично</p>

<style scoped>
.duel {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  align-items: stretch;
  gap: 1.5rem;
  width: 100%;
  margin-top: 0.75rem;
}
.duel h3 {
  margin: 0;
}
.duel ul {
  margin: 0;
}
.tile.no {
  opacity: 0.75;
}
.vs {
  align-self: center;
  font-family: var(--pa-font-display);
  font-size: 1.5rem;
  color: var(--pa-yellow);
  text-shadow: 0.1875rem 0.1875rem 0 #7a1f6a;
}
.after {
  margin-top: 1.75rem;
  font-family: var(--pa-font-pixel);
  font-weight: 600;
  font-size: 2rem;
  color: var(--lvl-accent);
}
</style>
---
layout: simple-slide
level: 2
clicks: 4
---

## Узнаваемость копится из мелочей

<div class="xp">
  <div class="xp-row" v-click="1"><span>Ответ в чате</span><b>+10 XP</b></div>
  <div class="xp-row" v-click="2"><span>Статья на профильном ресурсе</span><b>+25 XP</b></div>
  <div class="xp-row" v-click="3"><span>Помощь новичку</span><b>+15 XP</b></div>
  <div class="xp-bar" aria-hidden="true">
    <i v-for="c in 20" :key="c" :class="{ on: c <= [0, 4, 9, 12, 20][$clicks] }" />
  </div>
  <div class="xp-up" :class="{ on: $clicks >= 4 }">LEVEL UP! · регулярность важнее размера</div>
</div>

<style scoped>
/* мелкие действия начисляют опыт, полоса заполняется по кликам; на последнем — LEVEL UP */
.xp {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  width: 100%;
  margin-top: 0.75rem;
}
.xp-row {
  display: flex;
  justify-content: space-between;
  padding: 0.6rem 1rem;
  background: var(--dd-card-bg);
  box-shadow:
    0 -3px 0 0 var(--dd-card-border),
    0 3px 0 0 var(--dd-card-border),
    -3px 0 0 0 var(--dd-card-border),
    3px 0 0 0 var(--dd-card-border);
}
.xp-row b {
  font-family: var(--pa-font-display);
  font-size: 1rem;
  color: var(--pa-lime);
}
.xp-bar {
  display: grid;
  grid-template-columns: repeat(20, 1fr);
  gap: 3px;
  height: 1.5rem;
  margin-top: 1rem;
  padding: 3px;
  background: rgba(0, 0, 0, 0.55);
  box-shadow:
    0 -3px 0 0 var(--lvl-accent),
    0 3px 0 0 var(--lvl-accent),
    -3px 0 0 0 var(--lvl-accent),
    3px 0 0 0 var(--lvl-accent);
}
.xp-bar i {
  background: #1c1730;
  transition: background 0.3s steps(2, end);
}
.xp-bar i.on {
  background: var(--lvl-accent);
  box-shadow: 0 0 6px var(--lvl-accent);
}
.xp-up {
  font-family: var(--pa-font-pixel);
  font-weight: 600;
  font-size: 1.75rem;
  color: var(--pa-yellow);
  opacity: 0;
}
.xp-up.on {
  opacity: 1;
}
</style>

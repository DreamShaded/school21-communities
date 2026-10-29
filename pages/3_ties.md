---
layout: interjection
level: 3
transition: slide-up
---

<TextBig>
  Слабые связи
</TextBig>
---
layout: two-cols
level: 3
leftWidth: 46%
rightAlign: center
clicks: 3
---

## Сила слабых связей

<v-clicks>

- Близкий круг знает то же, что и вы
- Вакансии и идеи приходят от знакомых по касательной
- Сообщество — фабрика слабых связей

</v-clicks>

<p class="smart">Марк Грановеттер, «The Strength of Weak Ties», 1973</p>

::right::

<svg class="ties" viewBox="0 0 420 330" shape-rendering="crispEdges" role="img" aria-label="Плотный кластер «команда» и тонкие связи к другим кластерам: митап, чат, конференция">
  <!-- сильные связи: все со всеми внутри команды -->
  <g class="strong">
    <line x1="80" y1="140" x2="140" y2="110" /><line x1="80" y1="140" x2="150" y2="180" />
    <line x1="80" y1="140" x2="100" y2="210" /><line x1="140" y1="110" x2="150" y2="180" />
    <line x1="140" y1="110" x2="100" y2="210" /><line x1="150" y1="180" x2="100" y2="210" />
  </g>
  <!-- слабые связи наружу -->
  <g class="weak" :class="{ on: $clicks >= 2 }">
    <line x1="140" y1="110" x2="300" y2="50" />
    <line x1="150" y1="180" x2="320" y2="170" />
    <line x1="100" y1="210" x2="280" y2="280" />
  </g>
  <g class="others" :class="{ on: $clicks >= 2 }">
    <line x1="300" y1="50" x2="350" y2="30" /><line x1="300" y1="50" x2="360" y2="75" />
    <line x1="320" y1="170" x2="380" y2="150" /><line x1="320" y1="170" x2="375" y2="200" />
    <line x1="280" y1="280" x2="340" y2="300" /><line x1="280" y1="280" x2="345" y2="255" />
    <rect x="344" y="24" width="12" height="12" /><rect x="354" y="69" width="12" height="12" />
    <rect x="374" y="144" width="12" height="12" /><rect x="369" y="194" width="12" height="12" />
    <rect x="334" y="294" width="12" height="12" /><rect x="339" y="249" width="12" height="12" />
    <rect x="292" y="42" width="16" height="16" /><rect x="312" y="162" width="16" height="16" />
    <rect x="272" y="272" width="16" height="16" />
    <text x="250" y="22">МИТАП</text>
    <text x="232" y="140">ЧАТ</text>
    <text x="190" y="318">КОНФА</text>
  </g>
  <g class="team">
    <rect x="72" y="132" width="16" height="16" /><rect x="132" y="102" width="16" height="16" />
    <rect x="142" y="172" width="16" height="16" /><rect x="92" y="202" width="16" height="16" />
    <text x="40" y="90">КОМАНДА</text>
  </g>
  <!-- вакансия приходит по слабой связи -->
  <g class="offer" :class="{ on: $clicks >= 3 }">
    <rect x="290" y="150" width="24" height="18" />
    <path d="M290 150 L302 160 L314 150" />
  </g>
</svg>

<style scoped>
.ties {
  width: 100%;
  max-width: 27rem;
  overflow: visible;
}
.ties text {
  font-family: var(--pa-font-pixel);
  font-weight: 600;
  font-size: 20px;
  fill: var(--pa-text-dim);
}
.strong line {
  stroke: var(--lvl-accent);
  stroke-width: 5;
}
.team rect {
  fill: var(--lvl-accent);
}
.team text {
  fill: var(--lvl-accent);
}
.weak line {
  stroke: var(--lvl-accent2);
  stroke-width: 2;
  stroke-dasharray: 6 5;
}
.others line {
  stroke: var(--pa-line);
  stroke-width: 3;
}
.others rect {
  fill: var(--lvl-accent2);
}
.weak,
.others,
.offer {
  opacity: 0;
  transition: opacity 0.4s steps(4, end);
}
.weak.on,
.others.on,
.offer.on {
  opacity: 1;
}
.offer rect {
  fill: var(--pa-yellow);
}
.offer path {
  fill: none;
  stroke: #07040f;
  stroke-width: 3;
}
.offer.on {
  animation: offer-go 2.4s steps(12, end) infinite;
}
@keyframes offer-go {
  from {
    transform: translate(0, 0);
  }
  to {
    transform: translate(-150px, 10px);
  }
}
@media (prefers-reduced-motion: reduce) {
  .offer.on {
    animation: none;
  }
}
</style>
---
layout: simple-slide
level: 3
---

## Что говорят данные

<div class="data">
  <div class="tile" v-click="1">
    <h3>Грановеттер, 1973</h3>
    <p class="sub">Нашли работу через знакомого, 54 человека. Как часто виделись:</p>
    <div class="bars">
      <div class="bar"><span>часто</span><i style="--w: 16.7%" /><b>16,7%</b></div>
      <div class="bar"><span>иногда</span><i style="--w: 55.6%" /><b>55,6%</b></div>
      <div class="bar"><span>редко</span><i style="--w: 27.8%" /><b>27,8%</b></div>
    </div>
    <p class="total"><span class="gnum">84%</span> не близкий круг</p>
  </div>
  <div class="tile ok" v-click="2">
    <h3>LinkedIn, 2022</h3>
    <div class="stat"><span class="gnum">20 млн</span><span class="sub">пользователей, 5 лет</span></div>
    <div class="stat"><span class="gnum">600 тыс.</span><span class="sub">смен работы</span></div>
    <p>Лучше всех — умеренно слабые связи. Сильнее всего в цифровых отраслях</p>
  </div>
</div>

<style scoped>
.data {
  display: grid;
  grid-template-columns: 1.15fr 1fr;
  gap: 1.75rem;
  width: 100%;
  margin-top: 0.5rem;
}
.data h3,
.data p {
  margin: 0;
}
.bars {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
}
.bar {
  display: grid;
  grid-template-columns: 5.5rem 1fr 4.5rem;
  align-items: center;
  gap: 0.6rem;
}
.bar i {
  display: block;
  height: 1rem;
  width: var(--w);
  background: var(--lvl-accent);
  box-shadow: 0 0 6px var(--lvl-accent);
}
.bar b {
  font-weight: 500;
  text-align: right;
}
.total .gnum,
.stat .gnum {
  font-size: 2.5rem;
}
.total {
  display: flex;
  align-items: baseline;
  gap: 0.75rem;
}
</style>

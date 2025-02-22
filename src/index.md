---
toc: false
---

<div class="hero">
  <h1>Wiser Metrics for a Wiser World</h1>
  <h2>Tracking the metrics that matter for a radically wiser world.</h2>
  <h3>A project of<br /><a href="https://lifeitself.org/"><img src="https://lifeitself.org/assets/tao/horizontal-color-logo.png" width="150" /></a></h3>
</div>


```js
const plastics = FileAttachment("./data/plastics.csv").csv({typed: true});
const lpi = FileAttachment("./data/livingplanet.csv").csv({typed: true});
```

```js
// display(lpi)
```

<div class="grid grid-cols-2" style="grid-auto-rows: 504px;">
  <div class="card">${
    resize((width) => Plot.plot({
      title: "Global plastics production",
      subtitle: "Annual production of polymer resin and fibers.",
      width,
      y: {
        grid: true,
        label: "tonnes (millions)",
        transform: (f) => (f / 1000000)
        },
      marks: [
        Plot.ruleY([0]),
        Plot.lineY(plastics, {x: "Year", y: "plastic_production", tip: true})
      ]
    }))
  }</div>
  <div class="card">${
    resize((width) => Plot.plot({
      title: "Living Planet Index (LPI)",
      subtitle: "The average decline in 34,836  monitored wildlife populations across 5,495 native species relative to the year 1970 (i.e. 1970 = 100%)",
      width,
      y: {
        grid: true,
        label: "%"
      },
      marks: [
        Plot.ruleY([0]),
        Plot.lineY(lpi, {x: "Year", y: "lpi_final", tip: true})
      ]
    }))
  }</div>
</div>

---

<style>

.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: var(--sans-serif);
  margin: 4rem 0 8rem;
  text-wrap: balance;
  text-align: center;
}

.hero h1 {
  margin: 1rem 0;
  padding: 1rem 0;
  max-width: none;
  font-size: 14vw;
  font-weight: 900;
  line-height: 1;
  background: linear-gradient(30deg, var(--theme-foreground-focus), currentColor);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero h2 {
  margin: 0;
  max-width: 34em;
  font-size: 20px;
  font-style: initial;
  font-weight: 500;
  line-height: 1.5;
  color: var(--theme-foreground-muted);
}

@media (min-width: 640px) {
  .hero h1 {
    font-size: 90px;
  }
}

</style>

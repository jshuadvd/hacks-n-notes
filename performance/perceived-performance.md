# Perceived Performance

[Eli.wtf slideshow](http://assets.eli.wtf/talks/perceived-perf-perfmatters-2018/#/)

> Objective Time differences of 20% or less are imperceptible.
>
> – Steve Seow, Microsoft

Shoot for 30% speedup.

## Active phase vs Passive phase

> Humans tend to overestimate passive time by 36%
>
> – Richard Larson, MIT

Takes about 1 second to transition to passive state.

Keep users active.

You start to lose people from 1 - 4s of passive state.

### Wait indicators

| wait time | action |
| :--- | :--- |
| &lt; 1s | nothing |
| 1 - 2s | loading spinner |
| 2s - 4s | progress bar |
| 4s+ | entertain user. For example Slack uses animation, then shows inspirational quotes, then a screen preview, and finally loads. |

### Perception Hacks

* use optimistic updates on AJAX
* fire calls onMouseDown instead of onClick/touchStart \(gains 100-150ms\). Cancel on touchmove
* use `:active` animations. They encourage the user to hold the click longer.

### Progress bars

* Use quick bands animation

Measure requests to determine progress bar speed.

```js
const API_EXPECTED_TIME = 1000;
const SOME_OTHER_EXPECTED_TIME = 2000;

function getImage() {
    let t0 = performance.now();
    fetch(`${GET_IMAGE_API_URL}`).then(response => {
        const apiRoundtrip = performance.now() - t0;
        setPerformanceScalar(apiRoundtrip, API_EXPECTED_TIME);
        // Do stuff
    });
}

function setPerformanceScalar(observed, expected) {
    this.performanceScalar = observed / expected;
    // ...
    // tuck this away in app state, local storage, a global variable, etc
}
```

### Predictive Loading

> React as soon as the user signals intent.

Examples:

* Game devs like Duke Nukem that require user to shoot a door from a distance before opening it. Hinting the game to proactively upload the next level.
* In a login screen, start loading the dashboard JS bundle as soon as the user starts typing their username.




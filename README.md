# chronophoto-autosolver

A userscript that automatically scores the maximum 1000 points per round in
[Chronophoto](https://www.chronophoto.app), the "guess the year a photo was
taken" game.

This is a client-side exploit demo: the game exposes the correct answer
(`pictureDate`) to the page's JavaScript, so the script simply reads it,
converts it to the slider's scale, sets the slider, and submits.

## How it works

`app.js` polls for the global `pictureDate` variable the game defines for the
current photo. Once present, it maps the year onto the noUiSlider range
(`pictureDate / 29.234`), calls `pipsSlider.noUiSlider.set(...)`, and invokes
the game's own `submitAnswer()`.

## Install

1. Install a userscript manager such as
   [Tampermonkey](https://www.tampermonkey.net/).
2. Either:
   - **Manual:** create a new script and paste the contents of `app.js`, or
   - **Greasy Fork:** install from
     https://greasyfork.org/en/scripts/492681-chronophoto-cheat

Then play a round and press "next round".

## Disclaimer

Educational — it demonstrates why answer validation must happen server-side.
Don't use it on leaderboards or against other players.

## License

No license has been specified yet.

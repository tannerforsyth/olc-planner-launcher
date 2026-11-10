# OLC Planner launcher

A one-page home screen launcher for the OLC Planner. Apps Script can't set an iPhone home screen icon, so this page carries the bear icon and forwards straight to the planner.

- `index.html` forwards to the planner's `/exec` link. With `?setup` in the address, it shows the Add to Home Screen steps instead and removes `?setup` from the address, so the saved icon opens the planner.
- The planner only works for its owner, so this link is useless to anyone else.

Set up on iPhone: open `https://tannerforsyth.github.io/olc-planner-launcher/?setup` in Safari, tap Share, then Add to Home Screen.

The app's source lives in the private `olc-planner` repo; the icons come from its `assets/` folder.

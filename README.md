# FocusFlow Web

A Pomodoro application implemented with Rust and Leptos client-side rendering, compiled to WebAssembly. It runs in the browser; it is not a Rust backend service.

## Implemented

Timer controls, configurable focus/break intervals, project state, notifications, sound, theme and statistics, with browser LocalStorage persistence. Browser permissions and storage availability affect those features. WebAssembly uses browser JavaScript bindings; no native-speed or performance superiority claim is made without benchmarks.

## Run locally

Requires Rust, the WASM target and Trunk. No cloud account or backend service is required.

```bash
git clone https://github.com/matheussricardoo/focusflow-web.git
cd focusflow-web
rustup target add wasm32-unknown-unknown
cargo install trunk
cargo check --target wasm32-unknown-unknown --locked
trunk serve --address 127.0.0.1
```

Open the local URL printed by Trunk. To build: `trunk build --release`. The GitHub Pages workflow uses `/focusflow-web/` as its deployment base path; this does not establish that Pages is currently available.

## Manual validation

Start/pause/reset the timer, change intervals, create/update/delete a project, reload to inspect persistence, and test with notifications denied. Confirm that completing a focus session updates statistics once. Browser interaction is not covered by the build check.

## Limitations

All data is local to a browser profile; no server sync, accounts or shared persistence. Browser timing, permissions and background-tab behavior require manual validation. Automated browser tests are future work.

## Author and license

[Matheus Ricardo](https://github.com/matheussricardoo) · [LinkedIn](https://www.linkedin.com/in/matheussricardoo/)

See [LICENSE](LICENSE) for the repository license.

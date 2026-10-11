# Among Terminal

Native GTK4 tools for people who keep several terminals open at once.

| Repository | What it is |
|---|---|
| [among](https://github.com/Among-Terminal/among) | The terminal multiplexer. Rust, GTK4, libadwaita, VTE. |
| [Among-Terminal.github.io](https://github.com/Among-Terminal/Among-Terminal.github.io) | Documentation site. |

## About Among Terminal

A terminal multiplexer for GNOME. Split panes, named workspaces in a
collapsible sidebar, and a plugin pipeline that turns shell output into
interface content.

Terminal emulation is delegated to VTE (`libvte-2.91-gtk4`) through the
official GNOME World `vte4` crate — the same widget GNOME Terminal is built
on. Among Terminal owns the pane tree, workspace lifecycle, key routing and the
plugin pipeline, and does not reimplement terminal emulation.

Distributed as Snap, DEB and RPM for amd64 and arm64.

## Build from source

The project is three independent Cargo packages and needs a Rust toolchain:

```sh
cargo build --release --locked
cargo build --release --locked --manifest-path examples/plugins/Cargo.toml
cargo build --release --locked --manifest-path tools/among-tools/Cargo.toml
```

`cargo run --release` starts the application; `./target/release/among` is the
binary.

## Licence

Apache-2.0. Native libraries are dynamically linked and keep their own terms;
see [`LICENSE`](https://github.com/Among-Terminal/among/blob/main/LICENSE) and
the licensing notes in the documentation.
<p><img src="https://raw.githubusercontent.com/Among-Terminal/among/main/docs/media/logo.png" width="150" alt="Among Terminal logo"></p>

# Among Terminal

A native GNOME terminal multiplexer built with Rust, GTK4, libadwaita, and VTE.

Keep shells running in split panes and named, color-coded workspaces.
Resize and rearrange panes, work from the keyboard, restore layouts into fresh
shells, and add optional live status plugins.

[![Among Terminal in action](https://raw.githubusercontent.com/Among-Terminal/among/main/docs/media/among-terminal-preview.gif)](https://among-terminal.github.io/features/)

[Explore the features](https://among-terminal.github.io/features/) ·
[Installation guide](https://among-terminal.github.io/install/) ·
[Plugins](https://among-terminal.github.io/plugins/)

## Repositories

| Repository | What it is |
|---|---|
| [among](https://github.com/Among-Terminal/among) | The terminal. Build and contributor documentation live here |
| [among-plugins](https://github.com/Among-Terminal/among-plugins) | Official plugins: clock, system status, pane directory |
| [awesome-among-terminal](https://github.com/Among-Terminal/awesome-among-terminal) | Community list of plugins and resources. Add yours with a pull request |
| [among-plugin-template](https://github.com/Among-Terminal/among-plugin-template) | Start a plugin from this template. Holds the author guide and the API reference |
| [Among-Terminal.github.io](https://github.com/Among-Terminal/Among-Terminal.github.io) | Source of the user documentation site |
| [appimage-tools](https://github.com/Among-Terminal/appimage-tools) | Verified copies of the tools that build the AppImage |

## How plugins work

A plugin is a separate program. Among starts it, exchanges JSON with it over
standard input and output, and draws the result itself: text, icons and small
meters in the window, workspace, sidebar or a pane. A plugin cannot type into a
terminal, read its scrollback or create its own widgets.

Open Settings with `Ctrl+,` and select Plugins. Among downloads a ready-built
package from a GitHub release, checks its size and hashes, and leaves the plugin
disabled. Before it runs, you review the access it asks for and accept it. Each
plugin runs confined with Landlock and seccomp, with no network access. On a
kernel without Landlock a plugin starts only after you allow reduced protection.

The official plugins come from
[among-plugins](https://github.com/Among-Terminal/among-plugins). You can add
other sources, which are GitHub repositories that publish the same kind of
release. Community plugins listed in
[awesome-among-terminal](https://github.com/Among-Terminal/awesome-among-terminal)
are not reviewed by the project.

To write a plugin, create a repository from
[among-plugin-template](https://github.com/Among-Terminal/among-plugin-template).
It contains a working Rust plugin and a workflow that builds it for amd64 and
arm64 and publishes an immutable release that Among can install. The
[author guide](https://github.com/Among-Terminal/among-plugin-template/blob/main/docs/guide.md)
and the [API reference](https://github.com/Among-Terminal/among-plugin-template/blob/main/docs/api.md)
are in the same repository.

## Licence

Apache-2.0. Native libraries are dynamically linked and keep their own terms;
see [`LICENSE`](https://github.com/Among-Terminal/among/blob/main/LICENSE) and
the [licensing notes](https://among-terminal.github.io/licensing/).

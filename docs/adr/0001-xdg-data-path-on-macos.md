# The data directory on macOS is `~/.local/share/mess`, not Application Support

On macOS, the default data directory follows the XDG rule, as on Linux: `$XDG_DATA_HOME/mess`, else `~/.local/share/mess`. Apple's guidance points to `~/Library/Application Support` instead. We chose the XDG path because mess is a terminal app, and terminal users expect their tools' data in the same place on macOS and Linux.

## Consequences

- The data path function has its own macOS case. Do not "fix" it to use the platform's Application Support directory.
- A move later needs migration code for existing data, and it can break scripts that use the path.

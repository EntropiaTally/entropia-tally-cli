# Entropia-Tracker CLI

Simple command-line application whose sole purpose is to parse the `chat.log` generated by the
[Entropia Universe](https://www.entropiauniverse.com/) game client and output formatted events for use with
the [Entropia Tracker](https://github.com/Entropia-Tracker/entropia-tracker) client.

## Installing

Visit the [releases](https://github.com/Entropia-Tracker/entropia-tracker-cli/releases) section for pre-built
binaries, or you can build your own, see the [Developing](#developing) section.

bump

## Usage

```
$ entropia-tracker-cli parse -f /path/to/chat.log --watch
```

See a full list of available commands by using the `entropia-tracker-cli help` command.

## Events

Emitted in a common format where only the `values` content changes between the different
event types. See [Events](./EVENTS.md) for more information on the different events and which values
they can contain.

```json
{
    "event": "event_name",
    "date": "YYYY-MM-DD HH:mm:ss",
    "channel": "system",
    "values": {
      "key": "value"
    }
}
```


## Developing

```bash
make build
```
Will build a copy for your **current architecture** in `bin/entropia-tracker-cli`.


```bash
make release
```
Will create a version and checksums for all the available architectures and place them in `bin/`


## Testing

There are unit tests available for all the different events, run them with

```bash
make test
```
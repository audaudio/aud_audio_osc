# aud_audio_osc

English | [Deutsch](README.de.md)

[![CI](https://github.com/audaudio/aud_audio_osc/actions/workflows/quick_check.yaml/badge.svg)](https://github.com/audaudio/aud_audio_osc/actions/workflows/quick_check.yaml)

OSC adapter of the Audanika Audio Engine: address router, replies and notifications, UDP and WebSocket server.

Part of the Audanika Audio Engine; planned in
[aud_audio_pm](https://github.com/audaudio/aud_audio_pm). The package is a
scaffold so far: a pure Dart package that exports its version and nothing
else yet.

## Motivation

The engine of `aud_audio_graph` takes its commands as OSC messages; the
address model lives in `aud_audio_core`. What is still missing is the way
in from outside the process: a router from OSC addresses to the engine,
replies and notifications back to the sender, and servers over UDP and
WebSocket. This package is the place for that adapter. The repo was
created with the other repos of the engine and holds the boilerplate of a
Dart package; the adapter follows in later tickets.

## Installation

The package is not published to pub.dev. Add it as a git dependency,
resolved by its version tag:

```yaml
dependencies:
  aud_audio_osc:
    git:
      url: git@github.com:audaudio/aud_audio_osc.git
      tag_pattern: "{{version}}"
    version: ^0.0.3
```

Then run `dart pub get`.

## Usage

The library exports its version only:

```dart
import 'package:aud_audio_osc/aud_audio_osc.dart';

void main() {
  print('aud_audio_osc $audAudioOscVersion');
}
```

It prints:

```text
aud_audio_osc 0.0.3
```

## Limitations

- Router, replies, notifications and the UDP and WebSocket servers are
  not implemented yet; the library exports `audAudioOscVersion` only

## Documentation

- [Blog](doc/blog) — one post per change
- [aud_audio_pm](https://github.com/audaudio/aud_audio_pm) — the plans and
  decisions of the Audanika Audio Engine

## Status

Version 0.0.3, a scaffold. Before 1.0 — the API may change between minor
versions.

## Contributing

Follow the [develop guide](doc/guides/develop-guide.md), the
[code guide](doc/guides/code-guide.md) and the
[test guide](doc/guides/test-guide.md).

## License

MIT — see [LICENSE](LICENSE).

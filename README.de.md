# aud_audio_osc

[English](README.md) | Deutsch

[![CI](https://github.com/audaudio/aud_audio_osc/actions/workflows/quick_check.yaml/badge.svg)](https://github.com/audaudio/aud_audio_osc/actions/workflows/quick_check.yaml)

OSC-Adapter der Audanika Audio Engine: Adress-Router, Antworten und Benachrichtigungen, UDP- und WebSocket-Server.

Teil der Audanika Audio Engine; geplant in
[aud_audio_pm](https://github.com/audaudio/aud_audio_pm). Das Paket ist
bisher ein Gerüst: ein reines Dart-Paket, das seine Version exportiert und
sonst noch nichts.

## Motivation

Die Engine von `aud_audio_graph` nimmt ihre Befehle als OSC-Nachrichten
entgegen; das Adressmodell liegt in `aud_audio_core`. Was noch fehlt, ist
der Weg von außerhalb des Prozesses hinein: ein Router von OSC-Adressen
zur Engine, Antworten und Benachrichtigungen zurück an den Absender und
Server über UDP und WebSocket. Dieses Paket ist der Ort für diesen
Adapter. Das Repo wurde mit den anderen Repos der Engine angelegt und
enthält das Gerüst eines Dart-Pakets; der Adapter folgt in späteren
Tickets.

## Installation

Das Paket ist nicht auf pub.dev veröffentlicht. Füge es als
Git-Abhängigkeit hinzu, aufgelöst über seinen Versions-Tag:

```yaml
dependencies:
  aud_audio_osc:
    git:
      url: git@github.com:audaudio/aud_audio_osc.git
      tag_pattern: "{{version}}"
    version: ^0.0.3
```

Dann `dart pub get` ausführen.

## Verwendung

Die Bibliothek exportiert nur ihre Version:

```dart
import 'package:aud_audio_osc/aud_audio_osc.dart';

void main() {
  print('aud_audio_osc $audAudioOscVersion');
}
```

Es gibt aus:

```text
aud_audio_osc 0.0.3
```

## Grenzen

- Router, Antworten, Benachrichtigungen und die UDP- und WebSocket-Server
  sind noch nicht umgesetzt; die Bibliothek exportiert nur
  `audAudioOscVersion`

## Dokumentation

- [Blog](doc/de/blog) — ein Beitrag pro Änderung
- [aud_audio_pm](https://github.com/audaudio/aud_audio_pm) — die Pläne und
  Entscheidungen der Audanika Audio Engine

## Status

Version 0.0.3, ein Gerüst. Vor 1.0 — die API kann sich zwischen
Minor-Versionen ändern.

## Mitwirken

Folge dem [Develop-Guide](doc/guides/develop-guide.md), dem
[Code-Guide](doc/guides/code-guide.md) und dem
[Test-Guide](doc/guides/test-guide.md).

## Lizenz

MIT — siehe [LICENSE](LICENSE).

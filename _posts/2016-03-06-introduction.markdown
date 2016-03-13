---
layout: default
title: Einführung
permalink: introduction
---

# Erste Schritte in Ruby

Wir beginnen die Erforschung von Ruby in der interaktiven Ruby-Shell (irb).

Hierzu müssen wir im Startmenü den Eintrag `Start Command Prompt with Ruby` finden und öffnen.
Es öffnet sich die sogenannte `Eingabeaufforderung`, die noch zusätzlich mit Einstellungen für die Programmiersprache Ruby umkonfiguriert wurde.
Über die Eingabeaufforderung kann man Computerbefehle eingeben und ausführen.
Durch die Eingabe von Befehlen kann man Aufgaben auf dem Computer ohne Maus oder Toucheingabe ausführen.
Die Eingabeaufforderung wird in der Regel nur von erfahrenen Benutzern verwendet.

Einzelne Befehle werden mit der Taste `ENTER` abgeschlossen.
Wir möchten die interaktive Ruby-Shell starten.
Hierzu tippen wir `irb` ein und bestätigen mit `ENTER`.

![IRB](/images/irb-start.png "IRB")

# Ruby als Taschenrechner

Im einfachsten Fall kann man Ruby als Taschenrechner benutzen.
Ruby versteht das Rechnen mit den Zahlen.

Man kann z.B. folgende Rechnenoperationen nutzen:

| Symbol | Bedeutung      |
|--------|----------------|
| +      | Addition       |
| -      | Subtraktion    |
| *      | Multiplikation |
| /      | Division       |

* Probier es einfach mal in der interaktiven Ruby-Shell aus, indem du z.B. `1 + 2` eingibst oder andere Berechnungen anstellst!
* Was passiert, wenn du 3 durch 2 dividierst, also `3/2` ausführst?

# Zahlen in Ruby

Es stellt sich heraus, dass Ruby zwei verschiedene Klassen von Zahlen versteht:

## Integers

Ein Integer ist eine ganze Zahl, wie `1`, `2`, `-5`, usw.
Wenn du nur Integerwerte benutzt, wird dir Ruby auch ein Integer zurückliefern.

`3/2` ist `1.5`, aber das ist kein Integerwert, deshalb gibt Ruby `1` zurück.


## Fließkommazahlen (Floats)

Fließkommazahlen sind Zahlen mit Kommastellen, wie `3.14`, `1.5`, `3.0`, usw.
Wenn du Fließkommazahlen benutzt, wird dir Ruby auch einen Fließkommawert zurückgeben, z.B. im Fall von `3.0 / 2.0`.
Probier es aus!

## Mehr Operatoren

Bevor wir das Kapitel beenden, sehen wir uns zwei weitere Operatoren an:

| Symbol | Bedeutung          |
|--------|--------------------|
| **     | Exponent           |
| %      | Rest nach Division |

Probier in der interaktiven Ruby-Shell folgendes aus:

* `3 ** 2`
* `5 % 2`
* `5.1 % 2`

Schau dir an, wie der Operator `%` mit Dezimalzahlen umgeht.
In diesem Beispiel passt die Zahl 2 zweimal in 5.1 rein und 1.1 bleibt übrig.

# Übungen

* Wieviele Stunden hat ein Jahr?

* Was denkst du passiert, wenn du Fließkomma- und Integerwerte kombinierst? Versucht folgendes zu lösen:
  * `3.0 / 2`
  * `3 / 2.0`
  * `4 ** 2.0`
  * `4.1 % 2`

  Ist der Rückgabewert ein Integer- oder ein Fließkommawert?

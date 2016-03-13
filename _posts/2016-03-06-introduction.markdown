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

## Zahlen in Ruby

Es stellt sich heraus, dass Ruby zwei verschiedene Klassen von Zahlen versteht:

### Integers

Ein Integer ist eine ganze Zahl, wie `1`, `2`, `-5`, usw.
Wenn du nur Integerwerte benutzt, wird dir Ruby auch ein Integer zurückliefern.

`3/2` ist `1.5`, aber das ist kein Integerwert, deshalb gibt Ruby `1` zurück.


### Fließkommazahlen (Floats)

Fließkommazahlen sind Zahlen mit Kommastellen, wie `3.14`, `1.5`, `3.0`, usw.
Wenn du Fließkommazahlen benutzt, wird dir Ruby auch einen Fließkommawert zurückgeben, z.B. im Fall von `3.0 / 2.0`.
Probier es aus!

### Mehr Operatoren

Sehen wir uns zwei weitere Operatoren an:

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

## Übungen zu Zahlen

* Wieviele Stunden hat ein Jahr?

* Was denkst du passiert, wenn du Fließkomma- und Integerwerte kombinierst? Versucht folgendes zu lösen:
  * `3.0 / 2`
  * `3 / 2.0`
  * `4 ** 2.0`
  * `4.1 % 2`

  Ist der Rückgabewert ein Integer- oder ein Fließkommawert?

# Zeichenketten

Das waren also die Zahlen... aber was ist mit Buchstaben? Wörtern? Text?

Das Wort, das wir für eine Gruppe von Buchstaben verwenden, ist `Zeichenkette` oder `String`.

Wir werden beide Ausdrücke verwenden.

## Was man mit Zeichenketten machen kann
Hier sind Beispiele für Strings die man in `irb` ausprobieren kann:

* `"Hallo."`
* `"Ruby rocks."`
* `"5 ist meine Lieblingszahl... und deine?"`
* `"Snoopy sagt #%^?&*@!"`

Ruby kann elegante Dinge mit Zeichenketten machen.
Probier man folgendes aus:

* `"Hallo " + "Welt"`
* `"hi " * 3`
* `"1" + "2"`
* `"1" * 2`

Wenn Ruby `"1"` sieht, wird es als Zeichen und nicht als Zahl angesehen.

## Mehr Dinge, die man mit Zeichenketten machen kann

Hier einige elegante Operationen, die man mit Zeichenketten anstellen kann:

* `"hallo".capitalize`
* `"Hallo".swapcase`
* `"a".next`

## Übungen

* Was erwartest du wird folgendes zurückgeben: `"hallo".length + "welt".length`
* Versuch in der [Dokumentation von Ruby](http://ruby-doc.org/core-2.2.0/String.html) nachzuschlagen, wie man ein Wort umdreht oder in Großbuchstaben umwandelt und probier es aus.


# Neue Namen für alte Dinge

Ruby (und andere Programmiersprachen) benutzt spezielle Namen für Dinge, die wir bisher kennengelernt haben.
Zum Beispiel benutzt es das Wort `Float` für eine Fließkommazahl.

Hier mehr Definitionen:

* **Objekt**: Das ist irgendeine Menge an Daten. Wie die Zahl 3 oder die Zeichenkette 'hallo'.
* **Klasse**: Ruby spaltet alles in Klassen auf. Wie Integers, Fließkommazahlen und Zeichenketten.
* **Methode**: Dies sind Dinge, die man mit einem Objekt anstellen kann. Zum Beispiel kann man Integers addieren, also ist `+` eine Methode.

Wir haben bereits drei Klassen für Dinge gesehen:

| Alter Name       | Ruby Klasse |
|------------------|-------------|
| Integer          | **Integer** |
| Fließkommazahlen | **Float**   |
| Zeichenketten    | **String**  |

Wir haben auch schon einige Methoden kennengelernt:

| Ruby Klasse | Einige Methoden  |
|-------------|------------------|
| Integer     | + - / * % **|
| Float       | + - / * % **|
| String      | capitalize, reverse, length, upcase|


## Klassen im Vergleich zu Objekten

Mach dir den Unterschied zwischen Klassen und Objekten klar. Ein Objekt ist eine Menge von Daten. Eine Klasse sagt, um welche Art von Daten es sich handelt.

Zum Beispiel sind 3 und 5 verschiedene Zahlen.
Sie sind nicht dasselbe Objekt.
Aber sie sind beide Integerwerte, somit gehören sie zur selben Klasse.

Hier sind mehr Beispiele:

| Objekt  | Klasse  |
|---------|---------|
| 2       | Integer |
| -5      | Integer |
| 7.2     | Float   |
| 3.15    | Float   |
| 'hello' | String  |
| 'world' | String  |

## Die Klasse#Methode-Notation

Verschiedene Klassen haben unterschiedliche Methoden.
Du hast unter anderem schon folgende gesehen:

* Division (/) funktioniert nicht für ganze Zahlen und Fließkommazahlen gleich.
* Addition (+) macht mit Zeichenketten nicht das selbe wie mit ganzen Zahlen.
* Zeichenketten haben einige Methoden, die Integers und Fließkommazahlen nicht haben (z.B. `capitalize`, `length`, `upcase`, usw).

Aus diesem Grund verwenden wir die Notation/Schreibweise `Klasse#Methode` um klarzustellen, welche Methode wir meinen.
Z.B. werden wir `Integer#+` schreiben um es von `Float#+` und `String#+` zu unterscheiden.
Wir könnten z.B. auch schreiben, dass `String#upcase` existiert, aber `Integer#upcase` nicht.

## Konvertierung zwischen Klassen

Ruby hat Methoden, um zwischen Klassen zu konvertieren:

|Methode      | Konvertiert Von | Nach   |
|-------------|-----------------|--------|
|String#to_i  | String          |Integer |
|String#to_f  | String          |Float   |
|Integer#to_f | Integer         |Float   |
|Integer#to_s | Integer         |String  |
|Float#to_i   | Float           |Integer |
|Float#to_s   | Float           |String  |

Probier einige Methoden aus:

* `34.to_s`
* `"12".to_i`
* `"hallo".to_i`
* `27.2.to_i`
* `3.to_f`


## Übungen

* Ruby kann sagen, um welche Klasse es sich bei einem Objekt handelt. Probier folgendes aus:

{% highlight ruby %}
12.is_a?(Integer)
12.is_a?(Float)
12.is_a?(String)

'12'.is_a?(Integer)
'12'.is_a?(Float)
'12'.is_a?(String)

12.0.is_a?(Integer)
12.0.is_a?(Float)
12.0.is_a?(String)
{% endhighlight %}

  Welchen Unterschied siehst du?

* Gib folgendes in `irb` ein und prüfe, ob es das Ergebnis ist, das du erwarten würdest.

{% highlight ruby %}
12 + 12
'12' + '12'

'12'.to_i + 12
'12' + 12.to_s

12 * 12
'12' * 12
{% endhighlight %}

# Variablen

## Was ist eine Variable?

Eine `Variable` ist ein Name, den Ruby einem bestimmten `Objekt` zuordnet.
Zum Beispiel können wir in `irb` mal folgendes ausprobieren:

{% highlight ruby %}
stadt = "Berlin"
{% endhighlight %}

Hier ordnet Ruby der Zeichenkette "Berlin" den Namen (Variable) stadt zu.

Stell dir das so vor, als ob Ruby zwei Tabellen erstellt.
Eine Tabelle für Objekte und die andere Tabelle für Namen, die es jedem Objekt zuordnet.
Stell dir dann einen Pfeil vor, den Ruby von `stadt` nach `"Berlin"` zeichnet.

Jedesmal wenn Ruby auf `stadt` trifft, wird es dem Pfeil folgen und an der Zeichenkette `"Berlin"` ankommen.

Warnung: Variablennamen dürfen nicht mit einem Großbuchstaben beginnen.

## Mit Variablen arbeiten

Du kannst Variablen genauso manipulieren, wie du die Objekte manipulierst, die sie repräsentieren.
Probier folgendes aus:

{% highlight ruby %}
var1 = 7
var2 = 4
var3 = var1 + var 2
var4 = "hallo"
var4 = var4 * var2
{% endhighlight %}

Variablen erleichtern es Informationen einfacher im Auge zu behalten.

Stellen dir vor, du bekommst diese Anweisungen:

1. Addiere 2, 4, 6 und 8 zusammen.
1. Nimm das Ergebnis und dividieren es durch 5.
1. Nimm das Produkt von 2, 3 und 4.
1. Nimm das Ergebnis aus Zeile 2 und subtrahieren es vom Ergebnis von Zeile 3.

Du könntest einen langen Ausdruck schreiben, um das Ergebnis zu berechnen.
Es ist aber viel einfacher zu schreiben:

{% highlight ruby %}
num1 = 2 + 4 + 6 + 8
# => 20
num1 = num1/ 5
# => 4
num2 = 2 * 3 * 4
# => 24
num2 = num2 - num1
# => 20
{% endhighlight %}

# Bedingte Anweisung

Eine Bedingte Anweisung ist ein Programmabschnitt, der nur unter einer bestimmten Bedingung ausgeführt wird.
Eine Verzweigung legt fest, welcher von zwei (oder mehr) Programmabschnitten ausgeführt wird.

Die sogenannten `if`-Anweisungen inu Ruby erlauben es verschiedene Aktionen auszuführen, je nachdem welche Bedingung erfüllt wurde.
Zum Beispiel:

{% highlight ruby %}
if state == "Saarland"
   capital = "Saarbrücken
else
   capitel = "keine Ahnung :-("
end
{% endhighlight %}

Das sagt aus:

1. Wenn (`if`) das Bundesland (`state`) gleich (`==`) `"Saarbrücken"` ist, dann setze die Hauptstadt (`capital`) auf `Saarbrücken`.
1. Andernfalls (`else`) setze Hauptstadt (`capital`) auf `keine Ahnung :-(`.

## Wahr (**true**) und falsch (**false**)

Ruby hat eine Notation für `wahr` und `falsch`.
Dies wird am besten durch Beispiele aufgezeigt.
Probier einfach folgende Ausdrücke in `irb` aus:

{% highlight ruby %}
3 > 2
3 < 2

num = 4
num == 4

stadt = "Berlin"
stadt == "Berlin"
{% endhighlight %}

Die obige `if`-Anweisung wertet aus, ob der Ausdruck (z.B. `state == "Saarbrücken"`) **true** (wahr) oder **false** (falsch) ist und handelt dementsprechend.

Zu beachten ist der Unterschied zwischen `=` und `==`.

* `=` ist der Zuweisungsoperator.
* `==` ist ein Vergleichsoperator.

## Häufig genutzte Konditionale

Hier eine Liste der am häufigsten verwendeten Konditionale:

| == | gleich |
| != | ungleich |
| > | größer als|
| < | kleiner als |
| >= | größer als oder gleich |
| <= | kleiner als oder gleich |

## elsif

Das Schlüsselwort `elsif` erlaubt es mehr als eine Bedingung einzufügen.
Zum Beispiel:

{% highlight ruby %}
if alter >= 60
  puts "Seniorenpreis"
elsif alter >= 14
  puts "Erwachsenenpreis"
elsif alter > 2
  puts "Kinderpreis"
else
  puts "Frei"
end
{% endhighlight %}

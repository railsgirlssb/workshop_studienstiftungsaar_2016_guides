---
layout: default
title: Einführung Teil 2
permalink: introduction2
---

# Die nächsten Schritte in Ruby

# Arrays

Du bist schon vertraut mit einige Ruby-Klassen (`Integer` und `String` z.B.).
Die Klasse `Array` wird benutzt, um eine _Sammlung_ von Daten zu repräsentieren.

Dies ist am besten mit einem Beispiel zu verstehen:
{% highlight ruby %}
zahlen = [ "null", "eins", "zwei", "drei", "vier" ]
zahlen.class
{% endhighlight %}

Hier sagt uns die **Klassenmethode**, dass die Variable `zahlen` ein `Array` ist.

Man kann auf die einzelnen Elemente des Arrays folgendermaßen zugreifen:

{% highlight ruby %}
zahlen[0]
# => "null"

zahlen[1]
# => "eins"

zahlen[4]
# => "vier"
{% endhighlight %}

Man kann mehr mehr Einträge in das Array einfügen:

{% highlight ruby %}
numbers[5] = "fuenf"
# => "fuenf"
{% endhighlight %}

Beachten Sie, dass die Einträge der Reihe nach in das Array eingefügt werden, beginnend mit dem **Index** 0.
Ein Array kann eine beliebige Anzahl von Objekten enthalten.
Die Objekte in dem Array können wir wie zuvor manipuliert werden.

{% highlight ruby %}
zahlen[3].class
# => String

zahlen[3].upcase
# => "DREI"

zahlen[3].reverse
# => "ierd"
{% endhighlight %}

Welche Art von Dingen kann man in Arrays einfügen?
Nun, jedes Objekt.

Wie wärs mit Strings und Integers:

{% highlight ruby %}
adresse = [ 66113, "Saarbrücken" ]
{% endhighlight %}

Das ist alles sehr nett, aber kann man irgendwas cooles mit Arrays machen? Sicherlich kann man das.

## Array#sort

Du kannst Arrays mit der Methode Array#sort sortieren.

{% highlight ruby %}
primzahlen = [ 11, 5, 7, 2, 13, 3 ]
primzahlen.sort
{% endhighlight %}

{% highlight ruby %}
namen = [ "Melissa", "Daniel", "Samantha", "Jeffrey"]
namen.sort
{% endhighlight %}

## Array#reverse

Du kannst Arrays umdrehen:

{% highlight ruby %}
namen
# => ["Melissa", "Daniel", "Samantha", "Jeffrey"]
namen.reverse
{% endhighlight %}

## Array#length

Du kannst die Länge eines Arrays herausfinden:

{% highlight ruby %}
namen.length
{% endhighlight %}

# Iteratoren

Nun zu einem sehr coolen Merkmal von Ruby: **Iteratoren**

Ein *Iterator* ist eine spezielle Art von Methode.
Es ist eine Methode, die dich auf Einträge zugreifen lässt, eins nach dem anderen.

Iteratoren versucht man sich am besten anhand von Beispielen klarzumachen.

Im folgenden benutzen wir **Array#each**:

{% highlight ruby %}
friends = ["Jim", "Jeff", "Tim", "Rob"]
friends.each do |friend|
  puts "Ich habe einen Freund, der " + friend + " heißt."
end
{% endhighlight %}

Man kann mit der **Integer#times** Methode über ganze Zahlen von **0** bis **n-1** iterieren:

{% highlight ruby %}
4.times do |zahl|
  puts zahl
end
{% endhighlight %}

Es scheint merkwürdig zu sein, dass mit 0 angefangen wird zu zählen, aber das stimmt mit dem Verhalten bei den Arrays überein, bei denen auch der Index mit 0 beginnt.

Deswegen könnte man die Ausgabe der Freunde auch folgendermaßen umschreiben:

{% highlight ruby %}
4.times do |index|
  puts "Ich habe einen Freund, der " + friends[index] + " heißt."
end
{% endhighlight %}

## Übung

Gegeben sei das folgende Array:

{% highlight ruby %}
names = [ "daniel", "eduardo", "alejandro", "enrique" ]
{% endhighlight %}

Benutz die Methode **String#capitalize**, um die Namen groß zu schreiben.

# Hashes

Die nächste Klasse, auf die wir einen Blick werfen, ist **Hash**.

Hashes sind eine Verallgemeinerung von Arrays.
Statt nur ganze Zahlen als Indizes zuzulassen, wie z.B. bei `array[3]`, erlauben Hashes irgendein Objekt als *index* zu benutzen.
Somit kannst du `hash["name"]` schreiben.

Wir wollen nun einige Informationen über einen Freund speichern.
Wir könnten hierfür ein Array benutzen:

{% highlight ruby %}
friend = [ "Herbert", "Maier", "Auf Maien 69",
  "Neunkirchen", "Saarland"
]
{% endhighlight %}

Das würde gehen, aber wir müssten uns merken, dass z.B. `freund[0]` der *Vorname* ist, `freund[1]` der *Nachname*, usw..
Es könnte noch komplizierter kommen.

Das ist genau das Problem, wo ein Hash weiterhelfen kann.
So definiert man ein Hash:

{% highlight ruby %}
friend = {
  "vorname"    => "Herbert",
  "nachname"   => "Maier",
  "adresse"    => "Auf Maien 69",
  "stadt"      => "Neunkirchen",
  "bundesland" => "Saarland"
}
{% endhighlight %}

Genauso wie bei Arrays können Sie ein neues Feld wie folgt hinzufügen:


{% highlight ruby %}
friend["land"] = "Deutschland"
{% endhighlight %}

## Schlüssel und Werte

Da Hases keine numerischen Indizes benutzen, benutzen wir das Wort *Schlüssel* (**key**) stattdessen.
Das Objekt, auf das der Schlüssel zeigt, wird *Wert* (**value**) genannt.

Im obigen Beispiel sind demnach *vorname*, *nachname* und *stadt* Schlüssel.
Ihre entsprechenden Werte sind *Herbert*, *Maier* und *Neunkirchen*.

## Über Hashes iterieren

Hashes haben auch Iteratoren.

Hashes haben die Methode **Hash#each**, ähnlich zu **Array#each**.
Diese Methode liefert jedoch den Schlüssel als auch den Wert.

{% highlight ruby %}
friends.each do |key, value|
  puts key + " => " + value
end
{% endhighlight %}

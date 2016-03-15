---
layout: default
title: Einführung
permalink: game-of-dice
---

# Würfelspiel

Wir bauen nun ein Würfelspiel mit Ruby.

Würfelspiele bauen auf zufälligen Zahlen auf.
Zufälle Zahlen können wir mit der Methode `rand` erzeugen:

{% highlight ruby %}
rand
{% endhighlight %}

Eine ganze Zahl können wir erzeugen, in dem wir das Maximum angeben:

{% highlight ruby %}
rand(6)
{% endhighlight %}

Wenn wir nun probeweise 10 Zufallszahlen daraus in `irb` erzeugen, können wir sehen,
dass es eine `0`, aber nie das Maximum von `6` vorkommt:

{% highlight ruby %}
10.times do puts rand(6) end
{% endhighlight %}

Um also einen Würfel zu simulieren, müssen wir noch 1 addieren:

{% highlight ruby %}
10.times do puts rand(6) + 1 end
{% endhighlight %}

Diese herangehensweise ist nicht sehr gut zu lesen, von daher versucht man
immer komplexe Umstände, oder auch die technische Implementierung zu verstecken,
sodass man nicht sieht wie etwas funktioniert - das ist oft auch nicht notwendig -
sondern man will es einfach nur nutzen. Wir können also folgende Dinge abändern:

{% highlight ruby %}
def wuerfle
  rand(6) + 1
end
{% endhighlight %}

Jetzt haben wir das Würfeln verpackt und können anstelle von rand(6) + 1 wuerfle
aufrufen:

{% highlight ruby %}
10.times do puts wuerfle end
{% endhighlight %}

und noch etwas leserlicher

{% highlight ruby %}
10.times do
  puts wuerfle
end
{% endhighlight %}


# Einfaches Würfelspiel

Zwei Personen A und B spielen wer die höchste Zahl würfelt

{% highlight ruby %}
def spiel_einfach
  wurf_a = wuerfle
  wurf_b = wuerfle

  if wurf_a > wurf_b
    puts "A gewinnt mit #{wurf_a} gegen #{wurf_b}"
  elsif wurf_b > wurf_a
    puts "B gewinnt mit #{wurf_b} gegen #{wurf_a}"
  else
    puts "Beide haben #{wurf_a} gewürfelt, kein Gewinner!"
  end
end

10.times do 
  spiel_einfach
end
{% endhighlight %}


# Würfelregeln von Siedler von Catan

Summe der Augenzahlen von 2 Würfel und bei 7 wird der Räuber/Pirat bewegt

{% highlight ruby %}
def spiel_siedler
  erster_wuerfel = wuerfle
  zweiter_wuerfel = wuerfle
  gesamt = erster_wuerfel + zweiter_wuerfel

  if gesamt == 7
    puts "Oh nein, eine 7! Der Räuber/Pirat wird bewegt"
  else
    puts "Würzelaugen #{gesamt}"
  end
end

10.times do
  spiel_siedler
end
{% endhighlight %}

# Würfelhistogramm erstellen

Wir wollen wissen, wie oft eine Zahl bereits gezogen wurde.

Hierfür können wir einen Hash verwenden:

{% highlight ruby %}
h = {'1'=>0,'2'=>0,'3'=>0,'4'=>0,'5'=>0,'6'=>0}
{% endhighlight %}

Alternativ auch dynamisch:

{% highlight ruby %}
h = {}
(1..6).each do |i|
  h[i] = 0
end 
{% endhighlight %}

Jetzt schauen wir mal nach 16 Würfen, wie das Histogramm aussieht:

{% highlight ruby %}
16.times do
  h[ wuerfle ] += 1
end

h
{% endhighlight %}

Wenn wir jetzt Neben einem 6-seitigen Würfel auch andere Würfeltypen
wie z.B. W12, W20, W100 benötigen, können wir natürlich diese auch
erstellen:

{% highlight ruby %}
def wuerfle_w12
  rand(12) + 1
end

def wuerfle_w20
  rand(20) + 1
end

def wuerfle_w100
  rand(100) + 1
end
{% endhighlight %}

Das ist natürlich sehr aufwändig und man sollte dies immer vereinfachen,
wir erstellen nun eine parametrierte Funktion:

{% highlight ruby %}
def wuerfle(seiten)
  rand(seiten) + 1
end
{% endhighlight %}

Für das Histogramm müssten wir nun auch einige Änderungen machen und so
langsan wird das wirklich sehr viel. 
Wir müssen uns neue Variablennamen aussuchen und könnten durcheinander kommen.

Schauen wir uns also an, welche Schritte wir als nächstes unternehmen müssen
um die jetzige Komplexität zu verstecken.

{% highlight ruby %}
class Wuerfel
  attr_reader :seiten, :histogramm

  def initialize(seiten)
    @seiten = seiten

    @histogramm = {}
    (1..@seiten).each do |s|
      @histogramm[s] = 0
    end
  end

  def wuerfeln
    wurf = rand(@seiten) + 1
    @histogramm[wurf] += 1
    return wurf
  end
end
{% endhighlight %}

Wenn wir jetzt unseren alten W6 wieder wollen, können wir diesen
so definieren und die bisherigen Ergebnisse in viel weniger 
Zeilen Code beschreiben.

Im Hintergrund passiert die gesamte Magie

{% highlight ruby %}
w6 = Wuerfel.new(6)
10.times do 
  w6.wuerfeln
end

puts w6.histogramm
{% endhighlight %}

Weitere Würfel wie w10, w100 können analog erstellt werden.

{% highlight ruby %}
w10 = Wuerfel.new(10)
32.times do 
  w10.wuerfeln
end

puts w10.histogramm
{% endhighlight %}



Erarbeiten wir nun noch eine schöne, grafische Repräsentation des
Histogramms. Hierfür erweitern wir die Klasse wie folgt.

{% highlight ruby %}
class WuerfelVerbessert < Wuerfel
  attr_reader :gesamtwuerfe

  def initialize(seiten)
    super(seiten)
    @gesamtwuerfe = 0
  end

  def wuerfeln
    @gesamtwuerfe += 1
    super
  end

  def histogramm_anzeigen()
    puts "Würfelhistogramm für Würfel mit Seitenanzahl #{@seiten}"
    puts ""
    @histogramm.each do |s,w|
      puts s.to_s.rjust(3," ") + " : " +  "-" * w
    end
    puts ""
    puts "Insgesamt #{gesamtwuerfe} Würfe"
  end
end

w6 = WuerfelVerbessert.new(6)
32.times do 
  w6.wuerfeln
end

w6.histogramm_anzeigen

w20 = WuerfelVerbessert.new(20)
32.times do 
  w20.wuerfeln
end

w20.histogramm_anzeigen
{% endhighlight %}


Wenn wir jetzt ein etwas komplexeres Würfelspiel verwirklichen wollen, so
können wir dies sehr einfach mit der Klasse Würfel erledigen, die die
Komplexität vor uns versteckt.

{% highlight ruby %}
class EinWurfKniffel
  attr_reader :wuerfel

  def initialize
    @wuerfel = []
    5.times do
      @wuerfel << Wuerfel.new(6)
    end
  end
  
  def wuerfeln
    @wuerfel.map do |w|
      w.wuerfeln
    end
  end
end

kniffel = EinWurfKniffel.new
puts kniffel.wuerfeln
{% endhighlight %}

Die Interpretation des Wurfes kann sich jeder selbst überlegen.

---
title: Arbeiten mit LINQ
description: In diesem Tutorial erfahren Sie, wie Sie Sequenzen mit LINQ generieren, Methoden zur Verwendung in LINQ-Abfragen schreiben und zwischen strikter Auswertung (Eager Evaluation) und verzögerter Auswertung (Lazy Evaluation) unterscheiden.
ms.date: 03/28/2017
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: e5f9baab13cddfb9e294de1e1a6ce967ccbe0813
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="working-with-linq"></a>Arbeiten mit LINQ

## <a name="introduction"></a>Einführung

In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen. Es werden die folgenden Themen abgedeckt:

*   Generieren von Sequenzen mit LINQ
*   Schreiben von Methoden, die sich problemlos in LINQ-Abfragen verwenden lassen
*   Unterscheiden zwischen strenger und verzögerter Auswertung

Sie lernen diese Techniken durch Erstellen einer Anwendung, die eine der grundlegenden Fertigkeiten jedes Zauberkünstlers demonstriert: den [Faro-Shuffle](https://en.wikipedia.org/wiki/Faro_shuffle). Ein Faro-Shuffle ist eine Kartenmischtechnik, bei der zwei Kartenpäckchen exakt so ineinander gefächert werden, dass auf eine Karte des einen Stapels stets eine Karte des anderen Stapels folgt.

Zauberer verwenden diese Technik, weil sie damit nach jedem Mischen genau wissen, welche Karte sich wo befindet, und die Reihenfolge ein sich wiederholendes Muster ist. 

Im vorliegenden Artikel dient die Technik dazu, das Manipulieren von Datensequenzen mit einem anschaulichen Beispiel zu zeigen. Die von Ihnen erstellte Anwendung stellt einen Kartenstapel zusammen und führt dann eine Sequenz aus Mischvorgängen aus, wobei die Sequenz jedes Mal ausgegeben wird. Sie werden auch die aktualisierte mit der ursprünglichen Reihenfolge vergleichen.

Dieses Tutorial besteht aus vielen Schritten. Sie können die Anwendung nach jedem Schritt ausführen und sich den Fortschritt ansehen. Sie können sich auch das [abgeschlossene Beispiel](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in unserem Repository „dotnet/samples“ auf GitHub ansehen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Erforderliche Komponenten

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten. Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core). Sie können diese Anwendung unter Windows, Ubuntu Linux, OS X oder in einem Docker-Container ausführen. Sie müssen Ihren bevorzugten Code-Editor installieren. In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor. Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.

## <a name="create-the-application"></a>Erstellen der Anwendung

Im ersten Schritt wird eine neue Anwendung erstellt. Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung. Legen Sie das Verzeichnis als aktuelles Verzeichnis fest. Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein. Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.

Wenn Sie C# noch nie verwendet haben, erläutert [dieses Tutorial](console-teleprompter.md) die Struktur eines C#-Programms. Sie können dieses Tutorial lesen und dann zu diesem Artikel zurückkehren, um mehr über LINQ zu erfahren. 

## <a name="creating-the-data-set"></a>Erstellen des Datasets

Beginnen wir damit, einen Kartenstapel zu erstellen. Zu diesem Zweck erstellen Sie eine LINQ-Abfrage mit zwei Quellen (eine für die vier Farben, eine für die dreizehn Werte). Diese Quellen werden Sie zu einem aus 52 Karten bestehenden Kartenstapel kombinieren. Ein `Console.WriteLine`-Auszug innerhalb einer `foreach`-Schleife zeigt die Karten an.

Hier ist die Abfrage:

```csharp
var startingDeck = from s in Suits()
                   from r in Ranks()
                   select new { Suit = s, Rank = r };

foreach (var c in startingDeck)
{
    Console.WriteLine(c);
}
```

Die verschiedenen `from`-Klauseln erzeugen `SelectMany`, wodurch aus der Kombination jedes Elements in der ersten Sequenz mit jedem Element in der zweiten Sequenz eine einzige Sequenz erstellt wird. Für unsere Zwecke ist die Reihenfolge wichtig. Das erste Element in der ersten Quellsequenz (Farben) wird mit jedem Element in der zweiten Sequenz (Werte) kombiniert. Dadurch werden alle dreizehn Karten der ersten Farbe erzeugt. Dieser Vorgang wird mit jedem Element in der ersten Sequenz (Farben) wiederholt. Das Ergebnis ist ein Kartenstapel, der erst nach Farben und innerhalb der Farben nach Werten sortiert ist.

Als Nächstes müssen Sie die Methoden „Suits()“ und „Ranks()“ erstellen. Wir beginnen mit einem einfachen Satz von *Iteratormethoden*, die die Sequenz als Enumeration von Zeichenfolgen generieren:

```csharp
static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

Diese Methoden nutzen beide die `yield return`-Syntax, um während der Ausführung eine Sequenz zu erzeugen. Der Compiler erstellt ein Objekt, das `IEnumerable<T>`implementiert und die Sequenz aus Zeichenfolgen erst dann generiert, wenn diese angefordert werden.

Führen Sie jetzt das erstellte Beispiel aus. Es werden alle 52 Karten des Kartenstapels angezeigt. Es kann sehr hilfreich sein, dieses Beispiel mit einem Debugger auszuführen, um zu beobachten, wie die Methoden `Suits()` und `Values()` ausgeführt werden. Sie können deutlich erkennen, dass jede Zeichenfolge in jeder Sequenz erst dann erstellt wird, wenn sie benötigt wird.

![Konsolenfenster, das die App zeigt, die 52 Karten schreibt](./media/working-with-linq/console.png)

## <a name="manipulating-the-order"></a>Ändern der Reihenfolge

Als Nächstes erstellen wir eine Hilfsprogrammmethode, die das Mischen ausführen kann. Der erste Schritt besteht darin, den Kartenstapel in zwei Hälften zu teilen. Die zu den LINQ-APIs gehörenden Methoden `Take()` und `Skip()` stellen uns diese Funktion bereit:

```csharp
var top = startingDeck.Take(26);
var bottom = startingDeck.Skip(26);
```

Die Mischmethode ist in der Standardbibliothek nicht vorhanden, Sie müssen sie also selbst schreiben. Diese neue Methode veranschaulicht verschiedene Techniken, die Sie mit LINQ-basierten Programmen verwenden werden. Daher erläutern wir jeden Teil der Methode in den Schritten.

Die Signatur für die Methode erstellt eine *Erweiterungsmethode*:

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T>
    (this IEnumerable<T> first, IEnumerable<T> second)
```

Bei einer Erweiterungsmethode handelt es sich um eine *statische Methode*, die einem bestimmten Zweck dient. Sie sehen, dass dem ersten Argument der Methode der `this`-Modifizierer hinzugefügt wurde. Dies bedeutet, dass Sie die Methode so aufrufen können, als wäre sie eine Membermethode vom Typ des ersten Arguments.

Erweiterungsmethoden können nur innerhalb von `static`-Klassen deklariert werden. Also erstellen wir hierfür eine neue statische Klasse namens `extensions`. Im weiteren Verlauf dieses Tutorials werden Sie weitere Erweiterungsmethoden hinzufügen. Diese werden in der gleichen Klasse platziert.

Diese Methodendeklaration folgt auch einem Standardidiom, bei dem die Eingabe- und Ausgabetypen `IEnumerable<T>` sind. Auf diese Weise können LINQ-Methoden miteinander verkettet werden, um komplexere Abfragen auszuführen.

```csharp
using System.Collections.Generic;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>
            (this IEnumerable<T> first, IEnumerable<T> second)
        {
            // implementation coming.
        }
    }
}
```

Sie zählen beide Sequenzen gleichzeitig auf, fächern die Elemente ineinander und erstellen ein einziges Objekt.  Um eine LINQ-Methode schreiben zu können, die mit Sequenzen arbeitet, müssen Sie verstehen, wie `IEnumerable` funktioniert.

Die `IEnumerable`-Schnittstelle weist eine einzige Methode auf: `GetEnumerator()`. Das von `GetEnumerator()` zurückgegebene Objekt verfügt über eine Methode, um zum nächsten Element zu wechseln, und eine Eigenschaft, die das aktuelle Element in der Sequenz abruft. Sie verwenden diese beiden Member, um die Auflistung aufzuzählen und die Elemente zurückzugeben. Diese Interleavemethode ist eine Iteratormethode, daher verwenden Sie die oben gezeigte `yield return`-Syntax, anstatt eine Auflistung zu erstellen und die Auflistung zurückzugeben. 

Hier sehen Sie die Implementierung dieser Methode:

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

Nachdem Sie diese Methode geschrieben haben, kehren Sie jetzt zur `Main`-Methode zurück und mischen den Kartenstapel ein Mal:

```csharp
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }
        
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a>Vergleiche

Sehen wir uns an, wie viele Mischvorgänge benötigt werden, damit der Kartenstapel wieder in seiner ursprünglichen Reihenfolge vorliegt. Sie müssen eine Methode schreiben, die ermittelt, ob zwei Sequenzen gleich sind. Nachdem Sie diese Methode erstellt haben, müssen Sie den Code, der den Stapel mischt, in eine Schleife platzieren und dann prüfen, wann der Stapel wieder die ursprüngliche Reihenfolge aufweist.

Das Schreiben einer Methode, mit der ermittelt wird, ob die beiden Sequenzen gleich sind, sollte kein Problem sein. Die Methode hat die gleiche Struktur wie die Methode, die Sie zum Mischen des Kartenstapels geschrieben haben. Der Unterschied ist, dass dieses Mal nicht jedes Element zurückgegeben werden soll, sondern dass Sie die übereinstimmenden Elemente jeder Sequenz vergleichen. Wenn die gesamte Sequenz aufgezählt wurde und alle Elemente übereinstimmen, sind die Sequenzen gleich:

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

Dies zeigt ein zweites LINQ-Idiom: Terminalmethoden. Diese Methoden akzeptieren eine Sequenz als Eingabe (bzw. in diesem Fall zwei Sequenzen) und geben einen einzelnen Skalarwert zurück. Wenn diese Methoden verwendet werden, sind sie immer die letzten Methoden einer Abfrage. (Sie beenden – englisch: to terminate – die Abfrage, daher der Name.) 

Sie können diese Methode in Aktion sehen, wenn Sie sie verwenden, um zu ermitteln, wann der Kartenstapel wieder die ursprüngliche Reihenfolge aufweist. Platzieren Sie den Code zum Mischen in einer Schleife, und halten Sie diese an, wenn die Sequenz wieder die ursprüngliche Reihenfolge aufweist. Wenden Sie hierzu die `SequenceEquals()`-Methode an. Hier sehen Sie, warum diese Methode immer die letzte in einer Abfrage sein muss: sie gibt anstelle einer Sequenz einen einzelnen Wert zurück:

```csharp
var times = 0;
var shuffle = startingDeck;

do
{
    shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    times++;
} while (!startingDeck.SequenceEquals(shuffle));

Console.WriteLine(times);
```

Führen Sie das Beispiel aus, und sehen Sie sich an, wie der Kartenstapel nach jedem Mischvorgang neu sortiert wird und nach 8 Durchgängen wieder seine ursprüngliche Konfiguration aufweist.

## <a name="optimizations"></a>Optimierungen

Das Beispiel, das Sie bisher erstellt haben, führt einen *Mischvorgang nach außen* aus, bei dem die oberste und unterste Karte bei jedem Durchgang gleich bleiben. Als Nächstes führen wir einen *Mischvorgang nach innen* aus, bei dem alle 52 Karten ihre Position ändern. Hierbei werden die Hälften so ineinander gefächert, dass die erste Karte der unteren Hälfte zur ersten Karte des Kartenstapels wird. Das bedeutet, dass die unterste Karte der oberen Hälfte zur untersten Karte des Stapels wird. Dazu muss nur eine Zeile geändert werden. Aktualisieren Sie den Aufruf zum Mischen so, dass die Reihenfolge der oberen und unteren Hälften des Kartenstapels getauscht wird:

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

Führen Sie das Programm erneut aus, Sie werden feststellen, dass 52 Iterationen nötig sind, um den Kartenstapel wieder in die ursprüngliche Reihenfolge zu bringen. Sie werden auch einige erhebliche Leistungsabfälle beim Ausführen des Programms bemerken.

Dafür gibt es eine Anzahl von Gründen. Befassen wir uns mit einem der wichtigsten Gründe: der ineffizienten Nutzung der *verzögerten Auswertung*.

LINQ-Abfragen werden verzögert ausgewertet. Die Sequenzen werden erst generiert, wenn die Elemente angefordert werden. Dies ist üblicherweise ein großer Vorteil von LINQ. In Programmen wie diesem verursacht diese Art der Auswertung jedoch ein exponentielles Wachstum der Ausführungszeit.

Der ursprüngliche Kartenstapel wurde mithilfe einer LINQ-Abfrage generiert. Jede Mischung wird durch Ausführung dreier LINQ-Abfragen im vorherigen Kartenstapel generiert. All diese werden verzögert ausgeführt. Das bedeutet auch, dass sie bei jeder Anforderung der Sequenz erneut ausgeführt werden. Zum Zeitpunkt der 52. Iteration haben Sie den ursprünglichen Stapel also sehr häufig neu generiert. Nun schreiben wir ein Protokoll, das dieses Verhalten veranschaulicht. Danach werden wir das Problem beheben.

Im Folgenden finden Sie eine Protokollmethode, die an jede Abfrage angefügt werden kann, um diese Abfrage als „ausgeführt“ zu kennzeichnen.

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

Als Nächstes instrumentieren Sie die Definition jeder Abfrage mit einer Protokollmeldung:

```csharp
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }
        
    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        shuffle = shuffle.Skip(26)
            .LogQuery("Bottom Half")
            .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
            .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

Beachten Sie, dass beim Zugreifen auf eine Abfrage kein Protokolleintrag erstellt wird. Ein Protokolleintrag wird nur erstellt, wenn Sie die ursprüngliche Abfrage erstellen. Die Ausführung des Programms dauert immer noch lang, aber nun sehen Sie den Grund dafür. Wenn Sie nicht warten möchten, bis das Mischen nach innen mit aktivierter Protokollierung ausgeführt wurde, wechseln Sie zurück zum Mischen nach außen. Sie sehen immer noch die Auswirkungen der verzögerten Auswertung. In einer Ausführung werden 2592 Abfragen ausgeführt, einschließlich der Generierung aller Werte und Farben.

Es gibt eine einfache Möglichkeit, dieses Programm so zu ändern, dass all diese Ausführungen vermieden werden. Die LINQ-Methoden `ToArray()` und `ToList()` sorgen dafür, dass die Abfrage ausgeführt wird, und speichern die Ergebnisse in einem Array bzw. einer Liste. Sie verwenden diese Methoden dazu, die Datenergebnisse einer Abfrage zwischenzuspeichern, anstatt die Quellabfrage erneut auszuführen.  Fügen Sie die Abfragen, die die Kartenstapel generieren, an einen Aufruf von `ToArray()` an, und führen Sie die Abfrage erneut aus:

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

Führen Sie das Programm erneut aus – das Mischen nach außen wurde auf 30 Abfragen reduziert. Auch beim Mischen nach innen werden Sie ähnliche Verbesserungen feststellen. (Dabei werden jetzt 162 Abfragen ausgeführt.)

Sie dürfen dieses Beispiel aber nicht so interpretieren, dass alle Abfragen mit strikter Auswertung ausgeführt werden sollten. Dieses Beispiel sollte nur Anwendungsfälle veranschaulichen, bei denen eine verzögerte Auswertung zu Leistungsproblemen führen kann. Die Ursache des Problems ist, dass jede neue Anordnung des Kartenstapels aus der vorherigen Anordnung erstellt wird. Bei der verzögerten Auswertung bedeutet dies, dass jede neue Kartenstapelkonfiguration aus dem ursprünglichen Kartenstapel erzeugt wird. Dabei wird sogar der Code ausgeführt, der den `startingDeck`-Stapel erstellt hat. Das verursacht eine Menge zusätzlichen Aufwands. 

In der Praxis werden manche Algorithmen besser mit der strikten Auswertung ausgeführt, für andere eignet sich die verzögerte Auswertung besser. (Im Allgemeinen eignet sich die verzögerte Auswertung wesentlich besser, wenn es sich bei der Datenquelle um einen separaten Prozess handelt, beispielsweise um eine Datenbank-Engine. In diesen Fällen ermöglicht die verzögerte Auswertung komplexere Abfragen, um nur einen Roundtrip an den Datenbankprozess auszuführen.) LINQ ermöglicht sowohl eine verzögerte als auch eine strikte Auswertung. Wählen Sie die für Ihr jeweiliges Programm am besten geeignete Variante aus.

## <a name="preparing-for-new-features"></a>Vorbereiten auf neue Funktionen

Der Code, den Sie für diesen Artikel geschrieben haben, ist ein Beispiel für die Erstellung eines einfachen Prototyps, der das gewünschte Ergebnis erzielt. Er eignet sich hervorragend, um einen Problembereich zu untersuchen, und ist für viele Funktionen möglicherweise die beste dauerhafte Lösung. Sie haben *anonyme Typen* für die Karten verwendet, und jede Karte wird durch Zeichenfolgen dargestellt.

*Anonyme Typen* bieten viele Produktivitätsvorteile. Sie müssen nicht selbst eine Klasse definieren, um den Speicher darzustellen. Der Compiler generiert den Typ für Sie. Der vom Compiler generierte Typ nutzt viele der bewährten Methoden für einfache Datenobjekte. Er ist *unveränderlich*, d.h., nach dem Erstellen kann keine seiner Eigenschaften geändert werden. Anonyme Typen sind für eine Assembly intern, gehören also nicht zur öffentlichen API für diese Assembly. Anonyme Typen enthalten auch eine Überschreibung der `ToString()`-Methode, die eine formatierte Zeichenfolge mit den jeweiligen Werten zurückgibt.

Anonyme Typen haben jedoch auch Nachteile. Sie verfügen nicht über aufrufbare Namen, können also nicht als Rückgabewerte oder Argumente verwendet werden. Sie werden feststellen, dass alle oben genannten Methoden, die diese anonymen Typen verwenden, generische Methoden sind. Die Überschreibung von `ToString()` ist möglicherweise nicht wünschenswert, wenn der Anwendung weitere Funktionen hinzugefügt werden. 

Das Beispiel verwendet auch Zeichenfolgen für die Farbe und den Rang jeder Karte. Es ist fast beliebig erweiterbar. Mit dem Typsystem von C# lässt sich ein besserer Code erstellen, indem `enum`-Typen für diese Werte verwendet werden.

Beginnen Sie mit den Farben. Jetzt ist der perfekte Zeitpunkt, einen `enum`-Typ zu verwenden:

[!CODE-csharp[Suit enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet2)]

Die `Suits()`-Methode ändert auch den Typ und Implementierung:

[!CODE-csharp[Suit IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet4)]

Als Nächstes nehmen Sie die gleiche Änderung am Rang der Karten vor:

[!CODE-csharp[Rank enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet3)]

Ändern Sie auch die Methode, die den Rang generiert:

[!CODE-csharp[Rank IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet5)]

Und um das Ganze abzuschließen, erstellen wir einen Typ zur Darstellung der Karte, statt einen anonymen Typ zu verwenden. Anonyme Typen eignen sich hervorragend für einfache lokale Typen, aber im vorliegenden Beispiel ist die Spielkarte eines der wichtigsten Konzepte. Daher sollte sie einen konkreten Typ aufweisen.

[!CODE-csharp[PlayingCard](../../../samples/csharp/getting-started/console-linq/playingcard.cs?name=snippet1)]

Dieser Typ verwendet *automatisch implementierte, schreibgeschützte Eigenschaften*, die im Konstruktor festgelegt werden und danach nicht mehr geändert werden können. Er verwendet auch das Feature [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md), mit dem sich die Zeichenfolgenausgabe einfacher formatieren lässt.

Aktualisieren Sie die Abfrage zum Generieren des anfänglichen Kartenstapels so, dass der neue Typ verwendet wird:

```csharp
var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                    from r in Ranks().LogQuery("Value Generation")
                    select new PlayingCard(s, r))
                    .LogQuery("Starting Deck")
                    .ToArray();
```

Kompilieren Sie den Code, und führen Sie ihn erneut aus. Die Ausgabe ist etwas sauberer, und der Code ist klarer und kann einfacher erweitert werden.

## <a name="conclusion"></a>Schlussbemerkung

In diesem Beispiel wurden einige der in LINQ verwendeten Methoden veranschaulicht sowie das Erstellen von eigenen Methoden, die einfach mit für LINQ aktiviertem Code verwendet werden können. Das Beispiel hat auch die Unterschiede zwischen verzögerter und strikter Auswertung aufgezeigt und erläutert, wie sich die Entscheidung für die eine oder andere Variante auf die Leistung auswirken kann.

Sie haben etwas über die Techniken von Zauberkünstlern erfahren. Zauberer verwenden den Faro-Shuffle, weil sie damit genau steuern können, wann sich welche Karte wo im Stapel befindet. Bei manchen Tricks bittet der Zauberer einen Zuschauer, eine Karte ganz nach oben auf den Stapel zu legen. Dann mischt der Zauberer die Karten einige Male und weiß genau, wo die Karte ist. Für andere Tricks muss der Kartenstapel auf eine ganz bestimmte Art sortiert sein. Der Zauberer bereitet den Stapel vor dem Trick vor. Dann mischt er den Stapel fünfmal nach außen. Auf der Bühne zeigt er den Zuschauern dann einen Kartenstapel, der zufällig gemischt aussieht, mischt ihn noch 3-mal und erzielt so genau die gewünschte Kartenreihenfolge.

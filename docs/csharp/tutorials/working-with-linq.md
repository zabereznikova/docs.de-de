---
title: Arbeiten mit LINQ
description: In diesem Tutorial erfahren Sie, wie Sie Sequenzen mit LINQ generieren, Methoden zur Verwendung in LINQ-Abfragen schreiben und zwischen strikter Auswertung (Eager Evaluation) und verzögerter Auswertung (Lazy Evaluation) unterscheiden.
ms.date: 10/29/2018
ms.technology: csharp-linq
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: b25cd1763511f460537bccaf6011a3d23390ea72
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039169"
---
# <a name="working-with-linq"></a>Arbeiten mit LINQ

## <a name="introduction"></a>Einführung

In diesem Tutorial lernen Sie Features in .NET Core und der Sprache C# kennen. Es werden die folgenden Themen abgedeckt:

- Generieren von Sequenzen mit LINQ
- Schreiben von Methoden, die sich problemlos in LINQ-Abfragen verwenden lassen
- Unterscheiden zwischen strenger und verzögerter Auswertung

Sie lernen diese Techniken durch Erstellen einer Anwendung, die eine der grundlegenden Fertigkeiten jedes Zauberkünstlers demonstriert: den [Faro-Shuffle](https://en.wikipedia.org/wiki/Faro_shuffle). Ein Faro-Shuffle ist eine Kartenmischtechnik, bei der zwei Kartenpäckchen exakt so ineinander gefächert werden, dass auf eine Karte des einen Stapels stets eine Karte des anderen Stapels folgt.

Zauberer verwenden diese Technik, weil sie damit nach jedem Mischen genau wissen, welche Karte sich wo befindet, und die Reihenfolge ein sich wiederholendes Muster ist.

Im vorliegenden Artikel dient die Technik dazu, das Manipulieren von Datensequenzen mit einem anschaulichen Beispiel zu zeigen. Die von Ihnen erstellte Anwendung stellt einen Kartenstapel zusammen und führt dann eine Sequenz aus Mischvorgängen aus, wobei die Sequenz jedes Mal ausgegeben wird. Sie werden auch die aktualisierte mit der ursprünglichen Reihenfolge vergleichen.

Dieses Tutorial besteht aus vielen Schritten. Sie können die Anwendung nach jedem Schritt ausführen und sich den Fortschritt ansehen. Sie können sich auch das [abgeschlossene Beispiel](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in unserem Repository „dotnet/samples“ auf GitHub ansehen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="prerequisites"></a>Erforderliche Komponenten

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten. Die Installationsanweisungen finden Sie auf der Downloadseite für [.NET Core](https://dotnet.microsoft.com/download). Sie können diese Anwendung unter Windows, Ubuntu Linux, OS X oder in einem Docker-Container ausführen. Sie müssen Ihren bevorzugten Code-Editor installieren. In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor. Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.

## <a name="create-the-application"></a>Erstellen der Anwendung

Im ersten Schritt wird eine neue Anwendung erstellt. Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung. Legen Sie das Verzeichnis als aktuelles Verzeichnis fest. Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein. Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.

Wenn Sie C# noch nie verwendet haben, erläutert [dieses Tutorial](console-teleprompter.md) die Struktur eines C#-Programms. Sie können dieses Tutorial lesen und dann zu diesem Artikel zurückkehren, um mehr über LINQ zu erfahren.

## <a name="creating-the-data-set"></a>Erstellen des Datasets

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Zeilen am Anfang der Datei `Program.cs` stehen, die von `dotnet new console` generiert wurde:

```csharp
// Program.cs
using System;
using System.Collections.Generic;
using System.Linq;
```

Wenn diese drei Zeilen (`using`-Anweisungen) nicht am Anfang der Datei stehen, wird unser Programm nicht kompiliert.

Jetzt haben Sie alle nötigen Referenzen und können die Struktur eines Spielkartenstapels berücksichtigen. In der Regel besteht ein Spielkartenstapel aus vier Farben, und jede hat dreizehn Werte. In der Regel würden Sie wohl direkt eine `Card`-Klasse erstellen und eine Sammlung von `Card`-Objekten manuell füllen. Mit LINQ können Sie einen Spielkartenstapel präziser als üblich erstellen. Statt eine `Card`-Klasse zu erstellen, können Sie zwei Sequenzen zur Darstellung von Farben und Rängen erstellen. Sie erstellen ein einfaches Paar von [*Iteratormethoden*](../iterators.md#enumeration-sources-with-iterator-methods), das die Ränge und Farben als <xref:System.Collections.Generic.IEnumerable%601>s von Zeichenfolgen generiert:

```csharp
// Program.cs
// The Main() method

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

Platzieren Sie diese unterhalb der `Main`-Methode in Ihrer `Program.cs`-Datei. Diese Methoden nutzen beide die `yield return`-Syntax, um während der Ausführung eine Sequenz zu erzeugen. Der Compiler erstellt ein Objekt, das <xref:System.Collections.Generic.IEnumerable%601>implementiert und die Sequenz aus Zeichenfolgen erst dann generiert, wenn diese angefordert werden.

Verwenden Sie nun diese Iteratormethoden, um den Spielkartenstapel zu erstellen. Sie platzieren die LINQ-Abfrage in unserer `Main`-Methode. Sie sieht wie folgt aus:

```csharp
// Program.cs
static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    // Display each card that we've generated and placed in startingDeck in the console
    foreach (var card in startingDeck)
    {
        Console.WriteLine(card);
    }
}
```

Die verschiedenen `from`-Klauseln erzeugen <xref:System.Linq.Enumerable.SelectMany%2A>, wodurch aus der Kombination jedes Elements in der ersten Sequenz mit jedem Element in der zweiten Sequenz eine einzige Sequenz erstellt wird. Für unsere Zwecke ist die Reihenfolge wichtig. Das erste Element in der ersten Quellsequenz (Farben) wird mit jedem Element in der zweiten Sequenz (Ränge) kombiniert. Dadurch werden alle dreizehn Karten der ersten Farbe erzeugt. Dieser Vorgang wird mit jedem Element in der ersten Sequenz (Farben) wiederholt. Das Ergebnis ist ein Kartenstapel, der erst nach Farben und innerhalb der Farben nach Werten sortiert ist.

Beachten Sie unbedingt Folgendes: Ob Sie LINQ-Anweisungen in der oben verwendeten Abfragesyntax schreiben oder stattdessen die Methodensyntax verwenden, Sie können immer von einer Form der Syntax zur anderen wechseln. Die obige, in der Abfragesyntax geschriebene Abfrage kann in der Methodensyntax geschrieben werden als:

```csharp
var startingDeck = Suits().SelectMany(suit => Ranks().Select(rank => new { Suit = suit, Rank = rank }));
```

Der Compiler übersetzt mit der Abfragesyntax geschriebene LINQ-Anweisungen in die entsprechende Methodenaufrufsyntax. Aus diesem Grund erzielen unabhängig von Ihrer Syntaxwahl die beiden Versionen der Abfrage das gleiche Ergebnis. Wählen Sie die beste Syntax für Ihre Situation aus: Wenn Sie z.B. in einem Team arbeiten, in dem einige Mitglieder mit der Methodensyntax Schwierigkeiten haben, versuchen Sie, die Abfragesyntax zu bevorzugen.

Führen Sie jetzt das erstellte Beispiel aus. Es werden alle 52 Karten des Kartenstapels angezeigt. Es kann sehr hilfreich sein, dieses Beispiel mit einem Debugger auszuführen, um zu beobachten, wie die Methoden `Suits()` und `Ranks()` ausgeführt werden. Sie können deutlich erkennen, dass jede Zeichenfolge in jeder Sequenz erst dann erstellt wird, wenn sie benötigt wird.

![Ein Konsolenfenster, das die App zeigt, die 52 Karten schreibt.](./media/working-with-linq/console-52-card-application.png)

## <a name="manipulating-the-order"></a>Ändern der Reihenfolge

Konzentrieren Sie sich nun darauf, wie die Karten im Kartenstapel gemischt werden sollen. Der erste Schritt bei jedem guten Mischen ist das Aufteilen des Kartenstapels in zwei Hälften. Die zu den LINQ-APIs gehörenden Methoden <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> stellen Ihnen diese Funktion bereit. Platzieren Sie sie unterhalb der `foreach`-Schleife:

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    // 52 cards in a deck, so 52 / 2 = 26
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
}
```

In der Standardbibliothek ist jedoch keine Mischmethode vorhanden, Sie müssen sie also selbst schreiben. Die Mischmethode, die Sie erstellen, veranschaulicht verschiedene Techniken, die Sie mit LINQ-basierten Programmen verwenden, sodass jeder Teil dieses Prozesses in Schritten erläutert wird.

Um Funktionalität für Ihre Interaktion mit den <xref:System.Collections.Generic.IEnumerable%601>-Formen, die Sie von einigen LINQ-Abfragen erhalten, hinzuzufügen, müssen Sie einige besondere Arten von Methoden schreiben, die als [Erweiterungsmethoden](../programming-guide/classes-and-structs/extension-methods.md) bezeichnet werden. Eine Erweiterungsmethode ist im Wesentlichen eine *statische Methode* für einen speziellen Zweck, die einem bereits vorhandenen Typ Funktionalität hinzufügt, ohne diesen ursprünglichen Typ ändern zu müssen.

Fügen Sie für Ihre Erweiterungsmethoden eine neue *statische* Klassendatei namens `Extensions.cs` Ihrem Programm hinzu, und beginnen Sie dann, die erste Erweiterungsmethode zu erstellen:

```csharp
// Extensions.cs
using System;
using System.Collections.Generic;
using System.Linq;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>(this IEnumerable<T> first, IEnumerable<T> second)
        {
            // Your implementation will go here soon enough
        }
    }
}
```

Beachten Sie für einen Moment die Signatur der Methode, insbesondere die Parameter:

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T> (this IEnumerable<T> first, IEnumerable<T> second)
```

Sie sehen, dass dem ersten Argument der Methode der `this`-Modifizierer hinzugefügt wurde. Dies bedeutet, dass Sie die Methode so aufrufen können, als wäre sie eine Membermethode vom Typ des ersten Arguments. Diese Methodendeklaration folgt auch einem Standardidiom, bei dem die Eingabe- und Ausgabetypen `IEnumerable<T>` sind. Auf diese Weise können LINQ-Methoden miteinander verkettet werden, um komplexere Abfragen auszuführen.

Wenn Sie den Kartenstapel in zwei Hälften geteilt haben, müssen Sie diese Hälften natürlich auch wieder zusammenführen. Im Code zählen Sie beide Sequenzen, die Sie durch <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> erhalten haben, gleichzeitig auf, führen ein *`interleaving`* der Elemente durch und erstellen eine einzige Sequenz: Ihr jetzt gemischter Kartenstapel. Um eine LINQ-Methode schreiben zu können, die mit Sequenzen arbeitet, müssen Sie verstehen, wie <xref:System.Collections.Generic.IEnumerable%601> funktioniert.

Die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle weist eine einzige Methode auf: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>. Das von <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> zurückgegebene Objekt verfügt über eine Methode, um zum nächsten Element zu wechseln, und eine Eigenschaft, die das aktuelle Element in der Sequenz abruft. Sie verwenden diese beiden Member, um die Auflistung aufzuzählen und die Elemente zurückzugeben. Diese Interleavemethode ist eine Iteratormethode, daher verwenden Sie die oben gezeigte `yield return`-Syntax, anstatt eine Auflistung zu erstellen und die Auflistung zurückzugeben.

Hier sehen Sie die Implementierung dieser Methode:

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

Nachdem Sie diese Methode geschrieben haben, kehren Sie jetzt zur `Main`-Methode zurück und mischen den Kartenstapel ein Mal:

```csharp
// Program.cs
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

Wie viele Mischvorgänge sind nötig, damit der Kartenstapel wieder in seiner ursprünglichen Reihenfolge vorliegt? Um dies herauszufinden, müssen Sie eine Methode schreiben, die ermittelt, ob zwei Sequenzen gleich sind. Nachdem Sie diese Methode erstellt haben, müssen Sie den Code, der den Stapel mischt, in eine Schleife platzieren und dann prüfen, wann der Stapel wieder die ursprüngliche Reihenfolge aufweist.

Das Schreiben einer Methode, mit der ermittelt wird, ob die beiden Sequenzen gleich sind, sollte kein Problem sein. Die Methode hat die gleiche Struktur wie die Methode, die Sie zum Mischen des Kartenstapels geschrieben haben. Der Unterschied ist, dass dieses Mal nicht für jedes Element ein `yield return` ausgeführt wird, sondern dass Sie die übereinstimmenden Elemente jeder Sequenz vergleichen. Wenn die gesamte Sequenz aufgezählt wurde und alle Elemente übereinstimmen, sind die Sequenzen gleich:

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

Dies zeigt ein zweites LINQ-Idiom: Terminalmethoden. Diese Methoden akzeptieren eine Sequenz als Eingabe (bzw. in diesem Fall zwei Sequenzen) und geben einen einzelnen Skalarwert zurück. Terminalmethoden sind immer die endgültige Methode in einer Kette von Methoden für eine LINQ-Abfrage, daher der Namen „Terminalmethode“.

Sie können diese Methode in Aktion sehen, wenn Sie sie verwenden, um zu ermitteln, wann der Kartenstapel wieder die ursprüngliche Reihenfolge aufweist. Platzieren Sie den Code zum Mischen in einer Schleife, und halten Sie diese an, wenn die Sequenz wieder die ursprüngliche Reihenfolge aufweist. Wenden Sie hierzu die `SequenceEquals()`-Methode an. Hier sehen Sie, warum diese Methode immer die letzte in einer Abfrage sein muss: sie gibt anstelle einer Sequenz einen einzelnen Wert zurück:

```csharp
// Program.cs
static void Main(string[] args)
{
    // Query for building the deck

    // Shuffling using InterleaveSequenceWith<T>();

    var times = 0;
    // We can re-use the shuffle variable from earlier, or you can make a new one
    shuffle = startingDeck;
    do
    {
        shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

        foreach (var card in shuffle)
        {
            Console.WriteLine(card);
        }
        Console.WriteLine();
        times++;

    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

Führen Sie den bisher erstellten Code aus, und notieren Sie sich, wie der Kartenstapel bei jedem Mischvorgang neu angeordnet wird. Nach 8 Mischvorgängen (Iterationen der Do-while-Schleife) kehrt der Stapel zur ursprünglichen Konfiguration zurück, die er hatte, als Sie ihn zum ersten Mal durch Starten der LINQ-Abfrage erstellt haben.

## <a name="optimizations"></a>Optimierungen

Das Beispiel, das Sie bisher erstellt haben, führt einen *Mischvorgang nach außen* aus, bei dem die oberste und unterste Karte bei jedem Durchgang gleich bleiben. Als Nächstes führen wir stattdessen einen *Mischvorgang nach innen* aus, bei dem alle 52 Karten ihre Position ändern. Hierbei werden die Hälften so ineinander gefächert, dass die erste Karte der unteren Hälfte zur ersten Karte des Kartenstapels wird. Das bedeutet, dass die unterste Karte der oberen Hälfte zur untersten Karte des Stapels wird. Dies ist eine einfache Änderung einer einzelnen Codezeile. Aktualisieren Sie den derzeitigen Mischvorgang durch Wechseln der Positionen von <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A>. Dies ändert die Reihenfolge der oberen und unteren Hälfte des Kartenstapels:

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

Führen Sie das Programm erneut aus, Sie werden feststellen, dass 52 Iterationen nötig sind, um den Kartenstapel wieder in die ursprüngliche Reihenfolge zu bringen. Sie werden auch einige erhebliche Leistungsabfälle beim Ausführen des Programms bemerken.

Dafür gibt es eine Anzahl von Gründen. Sie können eine der wichtigsten Ursachen dieses Leistungsabfalls bekämpfen: die ineffiziente Nutzung der [*verzögerten Auswertung*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

Der wesentliche Aspekt der verzögerten Auswertung ist, dass eine Anweisung erst dann ausgewertet wird, wenn der Wert benötigt wird. LINQ-Abfragen sind verzögert ausgewertete Anweisungen. Die Sequenzen werden erst generiert, wenn die Elemente angefordert werden. Dies ist üblicherweise ein großer Vorteil von LINQ. In Programmen wie diesem verursacht diese Art der Auswertung jedoch ein exponentielles Wachstum der Ausführungszeit.

Denken Sie daran, dass wir den ursprünglichen Stapel mithilfe einer LINQ-Abfrage generiert haben. Jede Mischung wird durch Ausführung dreier LINQ-Abfragen im vorherigen Kartenstapel generiert. All diese werden verzögert ausgeführt. Das bedeutet auch, dass sie bei jeder Anforderung der Sequenz erneut ausgeführt werden. Zum Zeitpunkt der 52. Iteration haben Sie den ursprünglichen Stapel also sehr häufig neu generiert. Nun schreiben wir ein Protokoll, das dieses Verhalten veranschaulicht. Danach werden wir das Problem beheben.

Geben Sie die folgende Methode in Ihre `Extensions.cs`-Datei ein, bzw. kopieren Sie sie hinein. Diese Erweiterungsmethode erstellt eine neue Datei namens `debug.log` in Ihrem Projektverzeichnis, und zeichnet in der Protokolldatei auf, welche Abfrage derzeit ausgeführt wird. Diese Erweiterungsmethode kann jeder Abfrage angefügt werden, um diese Abfrage als „ausgeführt“ zu kennzeichnen.

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

Dann werden unter `File` rote Wellenlinien angezeigt. Das bedeutet, dass dieses Element nicht vorhanden ist. Es erfolgt keine Kompilierung, da der Compiler nicht weiß, worum es sich bei `File` handelt. Sie können dieses Problem lösen, indem Sie die folgende Codezeile unter die erste Zeile der Datei `Extensions.cs` einfügen:

```csharp
using System.IO;
```

Dadurch sollten das Problem behoben und die roten Wellenlinien entfernt werden.

Als Nächstes instrumentieren Sie die Definition jeder Abfrage mit einer Protokollmeldung:

```csharp
// Program.cs
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
        // Out shuffle
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        // In shuffle
        shuffle = shuffle.Skip(26).LogQuery("Bottom Half")
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

Sie können hier die Leistung des Codes verbessern, um die Anzahl der Ausführungen zu reduzieren, die Sie vornehmen. Eine einfache Lösung ist das *Zwischenspeichern* der Ergebnisse der ursprünglichen LINQ-Abfrage, die den Kartenstapel erstellt. Derzeit führen Sie die Abfragen jedes Mal erneut aus, wenn die Do-while-Schleife eine Iteration durchläuft, wobei Sie jedes Mal den Kartenstapel neu erstellen und mischen. Zum Zwischenspeichern des Kartenstapels können Sie die LINQ-Methoden <xref:System.Linq.Enumerable.ToArray%2A> und <xref:System.Linq.Enumerable.ToList%2A> nutzen; wenn Sie sie an die Abfragen anfügen, führen sie die gleichen Aktionen aus, für die Sie sie programmiert haben, aber jetzt speichern sie die Ergebnisse in einem Array oder einer Liste, je nachdem, welche Methode Sie auswählen. Fügen Sie die LINQ-Methode <xref:System.Linq.Enumerable.ToArray%2A> an beide Abfragen an, und führen Sie das Programm erneut aus:

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

Jetzt ist der Mischvorgang nach außen auf 30 Abfragen reduziert. Auch beim Mischen nach innen werden Sie ähnliche Verbesserungen feststellen: Jetzt werden 162 Abfragen ausgeführt.

Bitte beachten Sie: Dieses Beispiel sollte **nur** Anwendungsfälle veranschaulichen, bei denen eine verzögerte Auswertung zu Leistungsproblemen führen kann. Es ist wichtig, festzustellen, wo die verzögerte Auswertung die Codeleistung beeinträchtigen kann, aber es ist gleichermaßen wichtig, zu verstehen, dass nicht alle Abfragen strikt ausgeführt werden sollten. Ursache der Leistungseinbußen, die auftreten, wenn Sie <xref:System.Linq.Enumerable.ToArray%2A> nicht verwenden, ist, dass jede neue Anordnung des Kartenstapels aus der vorherigen Anordnung erstellt wird. Bei der verzögerten Auswertung bedeutet dies, dass jede neue Kartenstapelkonfiguration aus dem ursprünglichen Kartenstapel erzeugt wird. Dabei wird sogar der Code ausgeführt, der den `startingDeck`-Stapel erstellt hat. Das verursacht eine Menge zusätzlichen Aufwands.

In der Praxis werden manche Algorithmen gut mit der strikten Auswertung ausgeführt, für andere eignet sich die verzögerte Auswertung besser. Für die routinemäßige Nutzung eignet sich die verzögerte Auswertung in der Regel besser, wenn es sich bei der Datenquelle um einen separaten Prozess handelt, beispielsweise um eine Datenbank-Engine. Bei Datenbanken ermöglicht die verzögerte Auswertung komplexere Abfragen, um nur einen Roundtrip zum Datenbankprozess und zurück zu Ihrem übrigen Code auszuführen. LINQ ist flexibel, unabhängig davon, ob Sie die verzögerte oder strikte Auswertung verwenden, also wägen Sie Ihre Prozesse ab, und wählen Sie die Art der Auswertung aus, die Ihnen die beste Leistung bietet.

## <a name="conclusion"></a>Schlussbemerkung

In diesem Projekt wurde Folgendes behandelt:

- Verwendung von LINQ-Abfragen zum Aggregieren von Daten in einer sinnvollen Abfolge
- Schreiben von Erweiterungsmethoden zum Hinzufügen eigener benutzerdefinierter Funktionalität zu LINQ-Abfragen
- Lokalisieren von Bereichen in unserem Code, in denen LINQ-Abfragen zu Leistungsproblemen wie Geschwindigkeitseinbußen führen können
- verzögerte und strikte Auswertung im Hinblick auf die LINQ-Abfragen und die möglichen Auswirkungen auf die Abfrageleistung

Abgesehen von LINQ haben Sie ein wenig über die Verfahren gelernt, die Zauberer für Kartentricks anwenden. Zauberer verwenden den Faro-Shuffle, weil sie damit genau steuern können, wann sich welche Karte wo im Stapel befindet. Verderben Sie mit Ihrem Wissen jetzt aber nicht anderen den Spaß!

Weitere Informationen zu LINQ finden Sie unter:

- [Language-Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md)
  - [Einführung in LINQ](../programming-guide/concepts/linq/index.md)
  - [Grundlegende LINQ-Abfragevorgänge (C#)](../programming-guide/concepts/linq/basic-linq-query-operations.md)
  - [Datentransformationen mit LINQ (C#)](../programming-guide/concepts/linq/data-transformations-with-linq.md)
  - [Abfragesyntax und Methodensyntax in LINQ (C#)](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)
  - [C#-Funktionen mit LINQ-Unterstützung](../programming-guide/concepts/linq/features-that-support-linq.md)

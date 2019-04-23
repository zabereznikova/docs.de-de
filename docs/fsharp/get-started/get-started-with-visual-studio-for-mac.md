---
title: Erste Schritte mit F# in Visual Studio für Mac
description: Erfahren Sie, wie F# in Visual Studio für Mac verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: a6997f139d7e6c5fdf77878442db0b0b75b3d727
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331863"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Erste Schritte mit F# in Visual Studio für Mac

F#und das visuelle F# Tools in Visual Studio für Mac-IDE unterstützt werden. Stellen Sie sicher, dass man [Visual Studio für Mac installiert](install-fsharp.md#install-f-with-visual-studio-for-mac).

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eine der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Sobald Visual Studio für Mac geöffnet ist:

1. Auf der **Datei** Startmenü **neue Projektmappe**.

2. Klicken Sie im Dialogfeld "Neues Projekt" gibt es unterschiedliche 2-Vorlagen für die Konsolenanwendung.  Es gibt einen anderen -> .NET und .NET Framework ausgerichtet ist.  Die andere Vorlage befindet sich unter .NET Core >, das auf .NET Core-App.  Entweder Vorlage sollte im Rahmen dieses Artikels funktionieren.

3. Unter Konsolen-app C#, F# bei Bedarf ändern.  Wählen Sie die **Weiter** Schaltfläche, um den Vorgang fortzusetzen.  

4. Geben Sie Ihrem Projekt einen Namen ein, und wählen Sie die Optionen, die Sie für die app verwenden möchten.  Beachten Sie, dass im Vorschaufenster auf der Seite des Bildschirms, der die Verzeichnisstruktur angezeigt wird, die erstellt werden, basierend auf den ausgewählten Optionen.  

5. Klicken Sie auf **Erstellen**.  Eine F#-Projekt im Projektmappen-Explorer sollte nun angezeigt werden.

## <a name="writing-your-code"></a>Das Schreiben von code

Erste Schritte zunächst, Code zu schreiben.  Stellen Sie sicher, dass die `Program.fs` Datei geöffnet ist, und Ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Beispiel, eine Funktion `square` wurde der Eingabe mit dem Namen akzeptiert definiert `x` und von sich selbst multipliziert.  Da F# verwendet [Typrückschluss](../language-reference/type-inference.md), den Typ des `x` muss nicht angegeben werden.  Die F# Compiler versteht die Typen, in denen Multiplikation gültig ist, und weist einen Typ `x` basieren, wie `square` aufgerufen wird.  Wenn Sie darauf zeigen `square`, sollte Folgendes angezeigt:

```
val square: x:int -> int
```

Dies ist als die Signatur der Funktion Typ bezeichnet wird.  Sie können wie folgt gelesen werden: "Quadrat ist eine Funktion, die nimmt eine ganze Zahl, die mit dem Namen X und erzeugt eine ganze Zahl".  Beachten Sie, die der Compiler hat `square` der `int` Typ vorerst - Dies liegt daran Multiplikation nicht für generische *alle* Typen, aber stattdessen über einen vollständigen Satz von Typen ist generisch.  Die F# Compiler ausgewählt `int` an diesem Punkt, aber es passt die Datentyp-Signatur Aufrufen `square` mit einem anderen Eingabetyp, z. B. eine `float`.

Eine andere Funktion, `main`, definiert ist, wird die ergänzt, mit der `EntryPoint` Attribut Teilen der F# Compiler, mit dem Programm Ausführung sollte es starten.  Dabei wird die gleiche Konvention wie andere [Programmiersprachen C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in dem Befehlszeilenargumente an diese Funktion übergeben werden können und ein ganzzahligen Code wird zurückgegeben (in der Regel `0`).

Es ist in dieser Funktion, die wir Aufrufen der `square` Funktion mit dem Argument `12`.  Die F# Compiler weist dann den Typ des `square` sein `int -> int` (, also eine Funktion, die nimmt eine `int` und erzeugt eine `int`).  Der Aufruf von `printfn` ist eine formatierte drucken Funktion, die eine Formatzeichenfolge, die Programmiersprachen C-Stil, Parameter ähnelt, verwendet die in der Formatzeichenfolge angegeben entsprechen, und gibt dann das Ergebnis und eine neue Zeile.

## <a name="running-your-code"></a>Ausführen des Codes

Sie können den Code auszuführen und Ergebnisse anzeigen, indem Sie auf **ausführen** Menü der obersten Ebene und dann **Starten ohne Debugging**.  Dies führt die Anwendung ohne Debuggen und ermöglicht es Ihnen, um die Ergebnisse anzuzeigen.

Sie sollten jetzt sehen, dass die folgenden im Konsolenfenster anzuzeigen, die Visual Studio für Mac eingeblendet wird, wird ausgegeben:

```
12 squared is 144!
```

Herzlichen Glückwunsch!  Sie haben Ihre erste erstellt F# Projekt in Visual Studio für Mac, geschrieben ein F# Funktion ausgegeben, die Ergebnisse des Aufrufs, die Funktion, und führen Sie das Projekt aus, um einige Ergebnisse anzuzeigen.

## <a name="using-f-interactive"></a>Verwenden von F# Interactive

Eine der besten Features von der Visual F#-Tools in Visual Studio für Mac ist die F# Interactive-Fenster.  Sie können Code über an einen Prozess zu senden, können Sie rufen diesen Code und zeigen Sie das Ergebnis interaktiv.

Um mit der Nutzung beginnen, markieren Sie die `square` Funktion, die in Ihrem Code definiert.  Klicken Sie anschließend auf **bearbeiten** Menü der obersten Ebene.  Wählen Sie als Nächstes **Auswahl an F# Interactive senden**.  Dadurch wird den Code in die F# Interactive-Fenster ausgeführt.  Alternativ können Sie klicken Sie mit der rechten Maustaste auf die Auswahl und wählen Sie **Auswahl an F# Interactive senden**.  Daraufhin sollte die F# Interactive-Fenster mit den folgenden darin angezeigt:

```
>

val square : x:int -> int

>
```

Dies zeigt die gleiche Funktionssignatur für die `square` -Funktion, die Sie zuvor gesehen haben, wenn Sie über die Funktion gezeigt.  Da `square` ist nun im F# Interactive-Prozess definiert wird, können Sie ihn mit anderen Werten aufrufen:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Dies führt die Funktion, bindet das Ergebnis an einen neuen Namen `it`, und zeigt den Typ und Wert des `it`.  Beachten Sie, dass Sie jede Zeile mit dem Beenden müssen `;;`.  Dies ist wie F# Interactive weiß, wenn der Funktionsaufruf abgeschlossen ist.  Sie können auch neue Funktionen in F# Interactive definieren:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Die oben genannten definiert eine neue Funktion, `isOdd`, nimmt ein `int` und prüft, ob es ungerade ist!  Sie können Aufrufen dieser Funktion können Sie sehen, was es mit unterschiedlichen Eingaben zurückgibt.  Sie können Funktionen innerhalb von Funktionsaufrufen aufrufen:

```
> isOdd (square 15);;
val it : bool = true
```

Sie können auch die [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) auf den Wert an die beiden Funktionen zu übergeben:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

Der Pipe-Forward-Operator und vieles mehr, werden in späteren Tutorials behandelt.

Dies ist nur ein kurzer Einblick in die Verwendungsmöglichkeiten mit F# Interactive.  Weitere Informationen finden Sie [Interaktive Programmierung mit F#](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md), die behandelt einige der wichtigsten Funktionen der Sprache F#.  Es wird bieten Ihnen einen Überblick über einige der Funktionen von F# und bieten reichlich Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.  Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können, im gerätekatalog dargestellt die [Leitfaden für F#](../index.md).

## <a name="see-also"></a>Siehe auch

- [Visual F#](../index.md)
- [Einführung in F#](../tour.md)
- [F#Referenz zur Abfragesprache](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol und dem Operator-Referenz](../language-reference/symbol-and-operator-reference/index.md)

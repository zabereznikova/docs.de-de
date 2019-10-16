---
title: Erste Schritte mit F# in Visual Studio für Mac
description: Erfahren Sie, wie F# in Visual Studio für Mac verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: d3604178f93cf17d21f25b09084be7e7977378b5
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082974"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Erste Schritte mit F# in Visual Studio für Mac

F# und die visuellen F#-Tools werden in der IDE für Visual Studio für Mac unterstützt. Um zu beginnen, stellen Sie sicher, dass [Visual Studio für Mac installiert](install-fsharp.md#install-f-with-visual-studio-for-mac) ist.

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Nachdem Visual Studio für Mac geöffnet ist:

1. Zeigen Sie im Menü Datei auf **neue**Projekt **Mappe** .

2. Im Dialogfeld Neues Projekt gibt es zwei verschiedene Vorlagen für die Konsolenanwendung.  Es gibt einen unter anderen-> .net, der die .NET Framework als Ziel hat.  Die andere Vorlage befindet sich unter .net core->-app, die auf .net Core abzielt.  Beide Vorlagen sollten für den Zweck dieses Artikels funktionieren.

3. Bei der Konsolen-App ändern Sie bei Bedarf C# zu F#.  Wählen Sie die Schaltfläche **Weiter** aus, um fortzufahren.  

4. Benennen Sie Ihr Projekt, und wählen Sie die gewünschten Optionen für die App aus.  Beachten Sie, dass ein Vorschaufenster auf der Seite des Fensters angezeigt wird, auf der die Verzeichnisstruktur dargestellt wird, die basierend auf den ausgewählten Optionen erstellt wird.  

5. Klicken Sie auf **Erstellen**.  Ein F#-Projekt sollte nun im Projektmappen-Explorer angezeigt werden.

## <a name="writing-your-code"></a>Schreiben von Code

Beginnen wir, indem wir zuerst Code schreiben.  Stellen Sie sicher, dass die Datei `Program.fs` geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel wurde eine Funktion `square` definiert, die eine Eingabe mit dem Namen `x` annimmt und diese mit sich selbst multipliziert.  Da F# [Typrückschluss](../language-reference/type-inference.md) verwendet, muss der Typ von `x` nicht angegeben werden.  Der F#-Compiler versteht die Typen, bei denen eine Multiplikation gültig ist, und weist `x` basierend auf dem `square`-Aufruf einen Typen zu.  Wenn Sie mit den Mauszeiger auf `square` zeigen, sollte Folgendes angezeigt werden:

```console
val square: x:int -> int
```

Dies wird als Typsignatur der Funktion bezeichnet.  Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen" x "annimmt und eine ganze Zahl erstellt.  Beachten Sie, dass der `square` Compiler `int` den Typ für den Moment erteilt hat. Dies liegt daran, dass die Multiplikation nicht für *alle* Typen generisch ist, sondern für einen geschlossenen Satz von Typen generisch ist.  Der F# Compiler hat `int` an dieser Stelle gewählt, aber er passt die Typsignatur an, wenn `square` Sie mit einem `float`anderen Eingabetyp, z. b., aufruft.

Eine weitere Funktion `main` ist definiert und wurde mit dem `EntryPoint`-Attribut versehen, um dem F#-Compiler mitzuteilen, dass die Programmausführung hier gestartet werden soll.  Der Ausdruck folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code (in der Regel `0`) zurück gegeben wird.

In dieser Funktion wird die `square` Funktion mit einem Argument von `12`aufgerufen.  Der F# Compiler weist dann den Typ von `square` zu `int -> int` , d. h. eine Funktion, die einen `int` annimmt und einen `int`erzeugt.  Der-Befehl ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt. `printfn`

## <a name="running-your-code"></a>Ausführen des Codes

Sie können den Code ausführen und sich die Ergebnisse anzeigen lassen, indem Sie im Menü der obersten Ebene auf **Ausführen** klicken und dann **Ohne Debugging starten**.  Dadurch wird das Programm ohne Debuggen ausgeführt, und die Ergebnisse können angezeigt werden.

Nun sollte Folgendes im Konsolenfenster dargestellt werden, das im Visual Studio für Mac-Popup angezeigt wird:

```console
12 squared is 144!
```

Herzlichen Glückwunsch!  Sie haben Ihr erstes F#-Projekt in Visual Studio erstellt, eine F#-Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion ausgegeben hat, und das Projekt ausgeführt, um einige Ergebnisse anzuzeigen.

## <a name="using-f-interactive"></a>Verwenden von F# Interactive

Eines der besten Features von Visual F#-Tools in Visual Studio für Mac ist das F# Interactive-Fenster.  Es ermöglicht Ihnen das Senden von Code an einen Prozess, der diesen Code ausführt, sodass Sie das Ergebnis interaktiv sehen können.

Um mit der Verwendung zu beginnen, markieren Sie die im Code definierte Funktion `square`.  Klicken Sie anschließend im Menü der obersten Ebene auf **Bearbeiten**.  Wählen Sie als Nächstes **Auswahl an F# Interactive senden**.  Dadurch wird der Code im F# Interactive-Fenster ausgeführt.  Alternativ können Sie mit der rechten Maustaste auf die Auswahl klicken und **Auswahl an F# Interactive senden** wählen.  Es sollte das interaktive Fenster mit folgendem F#-Code angezeigt werden:

```console
>

val square : x:int -> int

>
```

Dies zeigt die gleiche Funktionssignatur für die `square`-Funktion, die Sie zuvor gesehen haben, als Sie mit dem Mauszeiger auf die Funktion gezeigt haben.  Da `square` nun im F# Interactive-Prozess definiert wird, können Sie sie mit anderen Werten aufrufen:

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Dadurch wird die Funktion ausgeführt, das Ergebnis an einen neuen Namen `it`gebunden und der Typ und der Wert von `it`angezeigt.  Beachten Sie, dass Sie jede Zeile mit `;;`beenden müssen.  Dies ist wie F# Interactive weiß, wenn der Funktionsaufruf abgeschlossen ist.  Sie können auch neue Funktionen in F# Interactive definieren:

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Im obigen Beispiel wird eine neue Funktion `isOdd` definiert, die eine `int`-Funktion annimmt und überprüft, ob diese ungerade ist.  Diese Funktion kann mit unterschiedlichen Eingaben aufgerufen werden, um zu sehen, was sie zurückgibt.  Sie können Funktionen innerhalb von Funktionsaufrufen aufrufen:

```console
> isOdd (square 15);;
val it : bool = true
```

Sie können auch den [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) verwenden, um den Wert in die beiden Funktionen zu überführen:

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

Der Pipe-Forward-Operator und mehr werden in späteren Tutorials behandelt.

Dies ist nur ein kurzer Einblick in die Verwendungsmöglichkeiten von F# Interactive.  Weitere Informationen finden Sie unter [Interaktive Programmierung mit F#](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md), die behandelt einige der wichtigsten Funktionen der Sprache F#.  Es wird bieten Ihnen einen Überblick über einige der Funktionen von F# und bieten reichlich Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.  Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können, im gerätekatalog dargestellt die [Leitfaden für F#](../index.md).

## <a name="see-also"></a>Siehe auch

- [Visual F#](../index.md)
- [Einführung in F#](../tour.md)
- [F#-Sprachreferenz](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol-und Operator Verweis](../language-reference/symbol-and-operator-reference/index.md)

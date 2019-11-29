---
title: Beginnen Sie mit F# in Visual Studio für Mac
description: Erfahren Sie, wie F# Sie mit Visual Studio für Mac verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: cd45ab9c59cef76e4bf85a93f39d8e2ee063d200
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552371"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Beginnen Sie mit F# in Visual Studio für Mac

F#und die visuellen F# Tools werden in der Visual Studio für Mac IDE unterstützt. Stellen Sie sicher, dass [Visual Studio für Mac installiert](install-fsharp.md#install-f-with-visual-studio-for-mac)ist.

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Nachdem Visual Studio für Mac geöffnet ist:

1. Zeigen Sie im Menü Datei auf **neue**Projekt **Mappe** .

2. Im Dialogfeld Neues Projekt gibt es zwei verschiedene Vorlagen für die Konsolenanwendung.  Es gibt einen unter anderen-> .net, der die .NET Framework als Ziel hat.  Die andere Vorlage befindet sich unter .net core->-app, die auf .net Core abzielt.  Beide Vorlagen sollten für den Zweck dieses Artikels funktionieren.

3. Ändern C# Sie unter Konsolen-APP F# bei Bedarf in.  Wählen Sie die Schaltfläche **weiter** aus, um fortzufahren.  

4. Benennen Sie Ihr Projekt, und wählen Sie die gewünschten Optionen für die APP aus.  Beachten Sie, dass der Vorschaufenster auf der Seite des Bildschirms angezeigt wird, auf der die Verzeichnisstruktur angezeigt wird, die basierend auf den ausgewählten Optionen erstellt wird.  

5. Klicken Sie auf **Erstellen**.  Nun sollte ein F# -Projekt in der Projektmappen-Explorer angezeigt werden.

## <a name="writing-your-code"></a>Schreiben von Code

Beginnen wir, indem wir zuerst Code schreiben.  Stellen Sie sicher, dass die Datei `Program.fs` geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel wurde eine Funktions `square` definiert, die eine Eingabe mit dem Namen `x` annimmt und Sie selbst multipliziert.  Da F# den [Typrückschluss](../language-reference/type-inference.md)verwendet, muss der Typ der `x` nicht angegeben werden.  Der F# Compiler versteht die Typen, bei denen die Multiplikation gültig ist, und weist `x` basierend auf der Aufruf `square` einen Typ zu.  Wenn Sie auf `square`zeigen, sollte Folgendes angezeigt werden:

```console
val square: x:int -> int
```

Dies wird als Typsignatur der Funktion bezeichnet.  Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen x annimmt und eine ganze Zahl erzeugt."  Beachten Sie, dass der Compiler den `int`-Typ vorerst `square` hat. Dies liegt daran, dass die Multiplikation nicht in *allen* Typen generisch ist, sondern eher für einen geschlossenen Satz von Typen.  Der F# Compiler hat an dieser Stelle `int` ausgewählt, aber die Typsignatur wird angepasst, wenn Sie `square` mit einem anderen Eingabetyp (z. b. einem `float`) aufzurufen.

Eine weitere Funktion, `main`, ist definiert und wird mit dem `EntryPoint`-Attribut versehen, um F# dem Compiler mitzuteilen, dass die Programmausführung gestartet werden soll.  Es folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code zurückgegeben wird (in der Regel `0`).

In dieser Funktion wird die `square`-Funktion mit einem Argument `12`aufgerufen.  Der F# Compiler weist dann den Typ des `square` zu, der `int -> int` werden soll (d. h. eine Funktion, die eine `int` annimmt und eine `int`erzeugt).  Der-`printfn` ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt.

## <a name="running-your-code"></a>Ausführen des Codes

Sie können den Code ausführen und Ergebnisse anzeigen, indem Sie im Menü der obersten Ebene auf **Ausführen** klicken und dann **ohne Debugging starten**.  Dadurch wird das Programm ohne Debuggen ausgeführt, und die Ergebnisse können angezeigt werden.

Nun sollte Folgendes im Konsolenfenster gedruckt angezeigt werden, das Visual Studio für Mac Popup angezeigt wird:

```console
12 squared is 144!
```

Herzlichen Glückwunsch!  Sie haben ihr erstes F# Projekt in Visual Studio für Mac erstellt, eine F# Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion gedruckt hat, und das Projekt ausführen, um einige Ergebnisse anzuzeigen.

## <a name="using-f-interactive"></a>Interaktiv F# verwenden

Eine der besten Features der visuellen F# Werkzeuge in Visual Studio für Mac ist das F# interaktive Fenster.  Es ermöglicht Ihnen das Senden von Code an einen Prozess, in dem Sie diesen Code aufzurufen und das Ergebnis interaktiv sehen können.

Um mit der Verwendung zu beginnen, markieren Sie die `square` Funktion, die in Ihrem Code definiert ist.  Klicken Sie anschließend im Menü der obersten Ebene auf **Bearbeiten** .  Wählen Sie dann **Auswahl an F# interaktiv senden**aus.  Dadurch wird der Code im F# interaktiven Fenster ausgeführt.  Alternativ können Sie mit der rechten Maustaste auf die Auswahl klicken und **Auswahl an F# Interactive senden**wählen.  Es sollte angezeigt werden F# , dass das interaktive Fenster mit folgendem Code angezeigt wird:

```console
>

val square : x:int -> int

>
```

Dies zeigt die gleiche Funktions Signatur für die `square`-Funktion, die Sie zuvor gesehen haben, als Sie mit dem Mauszeiger auf die Funktion gezeigt haben.  Da `square` jetzt im F# interaktiven Prozess definiert ist, können Sie ihn mit unterschiedlichen Werten aufzurufen:

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Dadurch wird die Funktion ausgeführt, das Ergebnis an einen neuen Namen `it`gebunden, und der Typ und der Wert `it`werden angezeigt.  Beachten Sie, dass Sie jede Zeile mit `;;`beenden müssen.  So weiß F# interaktiv, wann der Funktions Aufrufvorgang abgeschlossen ist.  Sie können neue Funktionen auch F# interaktiv definieren:

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Der obige Abschnitt definiert eine neue Funktion, `isOdd`, die eine `int` annimmt und überprüft, ob Sie ungerade ist!  Diese Funktion kann aufgerufen werden, um zu sehen, was Sie mit unterschiedlichen Eingaben zurückgibt.  Sie können Funktionen innerhalb von Funktionsaufrufen aufrufen:

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

Dies ist nur ein Überblick darüber, was mit F# Interactive möglich ist.  Weitere Informationen finden Sie unter [interaktive Programmierung mit F# ](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie dies noch nicht getan haben, sehen Sie [sich den F#Überblick über die wichtigsten ](../tour.md)Features der F# Sprache an.  Sie erhalten einen Überblick über einige der Funktionen von F#und bieten zahlreiche Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.  Es gibt auch einige hervorragend externe Ressourcen, die Sie verwenden können, [ F# ](../index.yml)die im Handbuch vorgestellt werden.

## <a name="see-also"></a>Siehe auch

- [F#lenken](../index.yml)
- [Einführung in F#](../tour.md)
- [F#Sprachreferenz](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol-und Operator Verweis](../language-reference/symbol-and-operator-reference/index.md)

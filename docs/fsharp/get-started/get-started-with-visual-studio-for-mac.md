---
title: Erste Schritte mit F# in Visual Studio für Mac
description: Erfahren Sie, wie F# in Visual Studio für Mac verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: 679ed1ea28f5d0e0d910dbd407b38d1d2f0314f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629752"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Erste Schritte mit F# in Visual Studio für Mac

F#und die visuellen F# Tools werden in der Visual Studio für Mac IDE unterstützt. Stellen Sie sicher, dass [Visual Studio für Mac installiert](install-fsharp.md#install-f-with-visual-studio-for-mac)ist.

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Nachdem Visual Studio für Mac geöffnet ist:

1. Zeigen Sie im Menü Datei auf **neue**Projekt **Mappe** .

2. Im Dialogfeld Neues Projekt gibt es zwei verschiedene Vorlagen für die Konsolenanwendung.  Es gibt einen unter anderen-> .net, der die .NET Framework als Ziel hat.  Die andere Vorlage befindet sich unter .net core->-app, die auf .net Core abzielt.  Beide Vorlagen sollten für den Zweck dieses Artikels funktionieren.

3. Unter Konsolen-app C#, F# bei Bedarf ändern.  Wählen Sie die Schaltfläche **weiter** aus, um fortzufahren.  

4. Benennen Sie Ihr Projekt, und wählen Sie die gewünschten Optionen für die APP aus.  Beachten Sie, dass der Vorschaufenster auf der Seite des Bildschirms angezeigt wird, auf der die Verzeichnisstruktur angezeigt wird, die basierend auf den ausgewählten Optionen erstellt wird.  

5. Klicken Sie auf **Erstellen**.  Eine F#-Projekt im Projektmappen-Explorer sollte nun angezeigt werden.

## <a name="writing-your-code"></a>Schreiben von Code

Beginnen wir, indem wir zuerst Code schreiben.  Stellen Sie sicher, `Program.fs` dass die Datei geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel wurde eine Funktion `square` definiert, die eine Eingabe mit dem Namen `x` annimmt und Sie selbst multipliziert.  Da F# verwendet [Typrückschluss](../language-reference/type-inference.md), den Typ des `x` muss nicht angegeben werden.  Der F# Compiler versteht die Typen, bei denen die Multiplikation gültig ist, und weist `x` basierend auf der `square` Aufruf von einen Typ zu.  Wenn Sie den Maus `square`Zeiger darüber bewegen, sollte Folgendes angezeigt werden:

```
val square: x:int -> int
```

Dies wird als Typsignatur der Funktion bezeichnet.  Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen" x "annimmt und eine ganze Zahl erstellt.  Beachten Sie, dass der `square` Compiler `int` den Typ für den Moment erteilt hat. Dies liegt daran, dass die Multiplikation nicht für *alle* Typen generisch ist, sondern für einen geschlossenen Satz von Typen generisch ist.  Der F# Compiler hat `int` an dieser Stelle gewählt, aber er passt die Typsignatur an, wenn `square` Sie mit einem `float`anderen Eingabetyp, z. b., aufruft.

Eine weitere Funktion `main`,, ist definiert und wird mit dem `EntryPoint` -Attribut versehen, um F# dem Compiler mitzuteilen, dass die Programmausführung gestartet werden soll.  Es folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code zurück `0`gegeben wird (in der Regel).

In dieser Funktion wird die `square` Funktion mit einem Argument von `12`aufgerufen.  Der F# Compiler weist dann den Typ von `square` zu `int -> int` , d. h. eine Funktion, die einen `int` annimmt und einen `int`erzeugt.  Der-Befehl ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt. `printfn`

## <a name="running-your-code"></a>Ausführen des Codes

Sie können den Code ausführen und Ergebnisse anzeigen, indem Sie im Menü der obersten Ebene auf **Ausführen** klicken und dann **ohne Debugging starten**.  Dadurch wird das Programm ohne Debuggen ausgeführt, und die Ergebnisse können angezeigt werden.

Nun sollte Folgendes im Konsolenfenster gedruckt angezeigt werden, das Visual Studio für Mac Popup angezeigt wird:

```
12 squared is 144!
```

Herzlichen Glückwunsch!  Sie haben ihr erstes F# Projekt in Visual Studio für Mac erstellt, eine F# Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion gedruckt hat, und das Projekt ausführen, um einige Ergebnisse anzuzeigen.

## <a name="using-f-interactive"></a>Verwenden von F# Interactive

Eine der besten Features von der Visual F#-Tools in Visual Studio für Mac ist die F# Interactive-Fenster.  Es ermöglicht Ihnen das Senden von Code an einen Prozess, in dem Sie diesen Code aufzurufen und das Ergebnis interaktiv sehen können.

Um mit der Verwendung zu beginnen, `square` markieren Sie die im Code definierte Funktion.  Klicken Sie anschließend im Menü der obersten Ebene auf **Bearbeiten** .  Wählen Sie als Nächstes **Auswahl an F# Interactive senden**.  Dadurch wird den Code in die F# Interactive-Fenster ausgeführt.  Alternativ können Sie klicken Sie mit der rechten Maustaste auf die Auswahl und wählen Sie **Auswahl an F# Interactive senden**.  Es sollte angezeigt werden F# , dass das interaktive Fenster mit folgendem Code angezeigt wird:

```
>

val square : x:int -> int

>
```

Dies zeigt die gleiche Funktions Signatur für die `square` Funktion, die Sie zuvor gesehen haben, als Sie mit dem Mauszeiger auf die Funktion gezeigt haben.  Da `square` ist nun im F# Interactive-Prozess definiert wird, können Sie ihn mit anderen Werten aufrufen:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Dadurch wird die Funktion ausgeführt, das Ergebnis an einen neuen Namen `it`gebunden und der Typ und der Wert von `it`angezeigt.  Beachten Sie, dass Sie jede Zeile mit `;;`beenden müssen.  Dies ist wie F# Interactive weiß, wenn der Funktionsaufruf abgeschlossen ist.  Sie können auch neue Funktionen in F# Interactive definieren:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Im obigen Beispiel wird eine neue Funktion `isOdd`definiert, die eine `int` annimmt und überprüft, ob Sie ungerade ist.  Diese Funktion kann aufgerufen werden, um zu sehen, was Sie mit unterschiedlichen Eingaben zurückgibt.  Sie können Funktionen innerhalb von Funktionsaufrufen aufrufen:

```
> isOdd (square 15);;
val it : bool = true
```

Sie können auch den [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) verwenden, um den Wert in die beiden Funktionen zu überführen:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

Der Pipe-Forward-Operator und mehr werden in späteren Tutorials behandelt.

Dies ist nur ein kurzer Einblick in die Verwendungsmöglichkeiten mit F# Interactive.  Weitere Informationen finden Sie [Interaktive Programmierung mit F#](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md), die behandelt einige der wichtigsten Funktionen der Sprache F#.  Es wird bieten Ihnen einen Überblick über einige der Funktionen von F# und bieten reichlich Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.  Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können, im gerätekatalog dargestellt die [Leitfaden für F#](../index.md).

## <a name="see-also"></a>Siehe auch

- [Visual F#](../index.md)
- [Einführung in F#](../tour.md)
- [F#Sprachreferenz](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol-und Operator Verweis](../language-reference/symbol-and-operator-reference/index.md)

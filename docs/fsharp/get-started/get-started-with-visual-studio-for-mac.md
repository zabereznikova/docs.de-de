---
title: 'Beginnen Sie mit F # in Visual Studio für Mac'
description: 'Erfahren Sie, wie Sie F # mit Visual Studio für Mac verwenden.'
ms.date: 07/03/2018
ms.openlocfilehash: d2ad24ad18bb31419b39508f2cf555c82fbe2e0b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437991"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Beginnen Sie mit F # in Visual Studio für Mac

F # und die Visual F# Tools werden in der Visual Studio für Mac IDE unterstützt. Stellen Sie sicher, dass [Visual Studio für Mac installiert](install-fsharp.md#install-f-with-visual-studio-for-mac)ist.

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.  Dazu gehen Sie wie folgt vor.  Nachdem Visual Studio für Mac geöffnet ist:

1. Zeigen Sie im Menü Datei auf **neue** Projekt **Mappe** .

2. Im Dialogfeld Neues Projekt gibt es zwei verschiedene Vorlagen für die Konsolenanwendung.  Es gibt einen unter anderen-> .net, der die .NET Framework als Ziel hat.  Die andere Vorlage befindet sich unter .net Core->-APP, die auf .net Core abzielt.  Beide Vorlagen sollten für den Zweck dieses Artikels funktionieren.

3. Ändern Sie bei Bedarf unter Konsolen-app c# in F #.  Wählen Sie die Schaltfläche **weiter** aus, um fortzufahren.  

4. Benennen Sie Ihr Projekt, und wählen Sie die gewünschten Optionen für die APP aus.  Beachten Sie, dass der Vorschaufenster auf der Seite des Bildschirms angezeigt wird, auf der die Verzeichnisstruktur angezeigt wird, die basierend auf den ausgewählten Optionen erstellt wird.  

5. Klicken Sie auf **Erstellen**.  Ein F #-Projekt sollte nun in der Projektmappen-Explorer angezeigt werden.

## <a name="writing-your-code"></a>Schreiben von Code

Beginnen wir, indem wir zuerst Code schreiben.  Stellen Sie sicher, dass die `Program.fs` Datei geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel wurde eine Funktion `square` definiert, die eine Eingabe mit dem Namen annimmt `x` und Sie selbst multipliziert.  Da F # den [Typrückschluss](../language-reference/type-inference.md)verwendet, muss der Typ von `x` nicht angegeben werden.  Der F #-Compiler kennt die Typen, bei denen die Multiplikation gültig ist, und weist basierend auf der Aufruf von einen Typ zu `x` `square` .  Wenn Sie den Mauszeiger darüber bewegen `square` , sollte Folgendes angezeigt werden:

```console
val square: x:int -> int
```

Dies wird als Typsignatur der Funktion bezeichnet.  Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen x annimmt und eine ganze Zahl erzeugt."  Beachten Sie, dass der Compiler `square` den `int` Typ für den Moment erteilt hat. Dies liegt daran, dass die Multiplikation nicht für *alle* Typen generisch ist, sondern für einen geschlossenen Satz von Typen generisch ist.  Der F #-Compiler `int` hat zu diesem Zeitpunkt gewählt, aber er passt die Typsignatur an, wenn Sie `square` mit einem anderen Eingabetyp, z. b. einer, aufzurufen `float` .

Eine weitere Funktion, `main` , ist definiert und wird mit dem- `EntryPoint` Attribut versehen, um dem F #-Compiler mitzuteilen, dass die Programmausführung gestartet werden soll.  Es folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code zurückgegeben wird (in der Regel `0` ).

In dieser Funktion wird die `square` Funktion mit einem Argument von aufgerufen `12` .  Der F #-Compiler weist dann den Typ von zu (d. h. `square` `int -> int` eine Funktion, die einen annimmt `int` und einen erzeugt `int` ).  Der-Befehl `printfn` ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt.

## <a name="running-your-code"></a>Ausführen Ihres Codes

Sie können den Code ausführen und Ergebnisse anzeigen, indem Sie im Menü der obersten Ebene auf **Ausführen** klicken und dann **ohne Debugging starten**.  Dadurch wird das Programm ohne Debuggen ausgeführt, und die Ergebnisse können angezeigt werden.

Nun sollte Folgendes im Konsolenfenster gedruckt angezeigt werden, das Visual Studio für Mac Popup angezeigt wird:

```console
12 squared is 144!
```

Glückwunsch!  Sie haben ihr erstes f #-Projekt in Visual Studio für Mac erstellt, eine f #-Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion gedruckt hat, und das Projekt ausführen, um einige Ergebnisse anzuzeigen.

## <a name="using-f-interactive"></a>Verwenden von F# Interactive

Eine der besten Funktionen der Visual F# Tools in Visual Studio für Mac ist das F# Interactive Fenster.  Es ermöglicht Ihnen das Senden von Code an einen Prozess, in dem Sie diesen Code aufzurufen und das Ergebnis interaktiv sehen können.

Um mit der Verwendung zu beginnen, markieren Sie die `square` im Code definierte Funktion.  Klicken Sie anschließend im Menü der obersten Ebene auf **Bearbeiten** .  Wählen Sie dann **Auswahl an F# Interactive senden** aus.  Dadurch wird der Code im Fenster F# Interactive ausgeführt.  Alternativ dazu können Sie auch mit der rechten Maustaste auf die Auswahl klicken und **Auswahl senden an F# Interactive** auswählen.  Es sollte angezeigt werden, dass das Fenster F# Interactive mit folgendem Code angezeigt wird:

```console
>

val square : x:int -> int

>
```

Dies zeigt die gleiche Funktions Signatur für die `square` Funktion, die Sie zuvor gesehen haben, als Sie mit dem Mauszeiger auf die Funktion gezeigt haben.  Da `square` jetzt im F# Interactive Prozess definiert ist, können Sie ihn mit unterschiedlichen Werten aufzurufen:

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Dadurch wird die Funktion ausgeführt, das Ergebnis an einen neuen Namen gebunden `it` und der Typ und der Wert von angezeigt `it` .  Beachten Sie, dass Sie jede Zeile mit beenden müssen `;;` .  Auf diese Weise F# Interactive weiß, wann der Funktions Aufrufvorgang abgeschlossen ist.  Sie können auch neue Funktionen in F# Interactive definieren:

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Im obigen Beispiel wird eine neue Funktion definiert, `isOdd` die eine annimmt `int` und überprüft, ob Sie ungerade ist.  Diese Funktion kann aufgerufen werden, um zu sehen, was Sie mit unterschiedlichen Eingaben zurückgibt.  Sie können Funktionen innerhalb von Funktionsaufrufen aufrufen:

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

Dies ist nur ein Überblick darüber, was Sie mit F# Interactive tun können.  Weitere Informationen finden Sie unter [interaktive Programmierung mit F #](../tools/fsharp-interactive/index.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie dies noch nicht getan haben, sehen Sie sich die Einführung [von f # an](../tour.md), in der einige der wichtigsten Features der Programmiersprache f # behandelt werden.  Sie erhalten einen Überblick über einige der Funktionen von F # und bieten zahlreiche Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.  Es gibt auch einige hervorragend externe Ressourcen, die Sie verwenden können, die im [Leitfaden zu F #](../index.yml)vorgestellt werden.

## <a name="see-also"></a>Weitere Informationen

- [Leitfaden für F#](../index.yml)
- [Einführung in F#](../tour.md)
- [F#-Programmiersprachenreferenz](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol- und Operatorenreferenz](../language-reference/symbol-and-operator-reference/index.md)

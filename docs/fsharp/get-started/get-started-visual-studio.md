---
title: Einstieg F# in Visual Studio
description: Erfahren Sie, wie F# Sie mit Visual Studio verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: 80b4fc5b7631eace719832fe32003cad578ead27
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552821"
---
# <a name="get-started-with-f-in-visual-studio"></a>Einstieg F# in Visual Studio

F#und die visuellen F# Tools werden in der Visual Studio-IDE unterstützt.

Vergewissern Sie sich zunächst, dass [Visual Studio mit F#installiert ](install-fsharp.md#install-f-with-visual-studio)ist.

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Nachdem Visual Studio geöffnet wurde:

1. Zeigen Sie im Menü **Datei** auf **neu**, und wählen Sie dann **Projekt**aus.

2. Im Dialogfeld Neues Projekt unter **Vorlagen**sollte **Visualisierung F#** angezeigt werden.  Wählen Sie diese Option aus F# , um die Vorlagen anzuzeigen.

3. Wählen Sie entweder **.net Core-Konsolen-App** oder Konsolen- **App**aus.

4. Wählen Sie **die Schaltfläche** OK aus F# , um das Projekt zu erstellen.  Nun sollte ein F# -Projekt in der Projektmappen-Explorer angezeigt werden.

## <a name="writing-your-code"></a>Schreiben von Code

Beginnen wir, indem wir zuerst Code schreiben.  Stellen Sie sicher, dass die Datei `Program.fs` geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel wurde eine Funktions `square` definiert, die eine Eingabe mit dem Namen `x` annimmt und Sie selbst multipliziert.  Da F# den [Typrückschluss](../language-reference/type-inference.md)verwendet, muss der Typ der `x` nicht angegeben werden.  Der F# Compiler versteht die Typen, bei denen die Multiplikation gültig ist, und weist `x` basierend auf der Aufruf `square` einen Typ zu.  Wenn Sie auf `square`zeigen, sollte Folgendes angezeigt werden:

```fsharp
val square: x:int -> int
```

Dies wird als Typsignatur der Funktion bezeichnet.  Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen x annimmt und eine ganze Zahl erzeugt."  Beachten Sie, dass der Compiler den `int`-Typ vorerst `square` hat. Dies liegt daran, dass die Multiplikation nicht in *allen* Typen generisch ist, sondern eher für einen geschlossenen Satz von Typen.  Der F# Compiler hat an dieser Stelle `int` ausgewählt, aber die Typsignatur wird angepasst, wenn Sie `square` mit einem anderen Eingabetyp (z. b. einem `float`) aufzurufen.

Eine weitere Funktion, `main`, ist definiert und wird mit dem `EntryPoint`-Attribut versehen, um F# dem Compiler mitzuteilen, dass die Programmausführung gestartet werden soll.  Es folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code zurückgegeben wird (in der Regel `0`).

In dieser Funktion wird die `square`-Funktion mit einem Argument `12`aufgerufen.  Der F# Compiler weist dann den Typ des `square` zu, der `int -> int` werden soll (d. h. eine Funktion, die eine `int` annimmt und eine `int`erzeugt).  Der-`printfn` ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt.

## <a name="running-your-code"></a>Ausführen des Codes

Sie können den Code ausführen und Ergebnisse anzeigen, indem Sie **STRG**+**F5**drücken.  Dadurch wird das Programm ohne Debuggen ausgeführt, und Sie können die Ergebnisse anzeigen.  Alternativ können Sie in Visual Studio das Menü Element der obersten Ebene **Debuggen** auswählen und dann **Starten ohne Debugging**auswählen.

Im Konsolenfenster, in dem Visual Studio angezeigt wird, sollte nun Folgendes angezeigt werden:

```console
12 squared is 144!
```

Herzlichen Glückwunsch!  Sie haben ihr erstes F# Projekt in Visual Studio erstellt, eine F# Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion gedruckt hat, und das Projekt ausführen, um einige Ergebnisse anzuzeigen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie dies noch nicht getan haben, sehen Sie [sich den F#Überblick über die wichtigsten ](../tour.md)Features der F# Sprache an.  Sie erhalten einen Überblick über einige der Funktionen von F#und bieten zahlreiche Codebeispiele, die Sie in Visual Studio kopieren und ausführen können.  Weitere Informationen zur F# Dokumentation finden Sie auf der [ F# Dokumentations Homepage](../index.yml).

## <a name="see-also"></a>Siehe auch

- [Einführung in F#](../tour.md)
- [F#Sprachreferenz](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol-und Operator Verweis](../language-reference/symbol-and-operator-reference/index.md)

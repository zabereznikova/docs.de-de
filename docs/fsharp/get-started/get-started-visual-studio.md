---
title: Erste Schritte mit F# in Visual Studio
description: Erfahren Sie, wie Sie F# in Visual Studio verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: 24c9a81cfa61dc904db9b2213224677696d7eb9b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629770"
---
# <a name="get-started-with-f-in-visual-studio"></a>Erste Schritte mit F# in Visual Studio

F#und die visuellen F# Tools werden in der Visual Studio-IDE unterstützt.

Um zu beginnen, stellen Sie sicher, dass man [Visual Studio installiert, die mit F#](install-fsharp.md#install-f-with-visual-studio).

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Nachdem Visual Studio geöffnet wurde:

1. Zeigen Sie im Menü **Datei** auf **neu**, und wählen Sie dann **Projekt**aus.

2. Im Dialogfeld Neues Projekt unter **Vorlagen**sollte **Visualisierung F#** angezeigt werden.  Wählen Sie diese Option aus F# , um die Vorlagen anzuzeigen.

3. Wählen Sie entweder **.net Core-Konsolen-App** oder Konsolen- **App**aus.

4. Wählen Sie die **OK** klicken, um den F#-Projekt zu erstellen!  Eine F#-Projekt im Projektmappen-Explorer sollte nun angezeigt werden.

## <a name="writing-your-code"></a>Schreiben von Code

Beginnen wir, indem wir zuerst Code schreiben.  Stellen Sie sicher, `Program.fs` dass die Datei geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel wurde eine Funktion `square` definiert, die eine Eingabe mit dem Namen `x` annimmt und Sie selbst multipliziert.  Da F# verwendet [Typrückschluss](../language-reference/type-inference.md), den Typ des `x` muss nicht angegeben werden.  Der F# Compiler versteht die Typen, bei denen die Multiplikation gültig ist, und weist `x` basierend auf der `square` Aufruf von einen Typ zu.  Wenn Sie den Maus `square`Zeiger darüber bewegen, sollte Folgendes angezeigt werden:

```fsharp
val square: x:int -> int
```

Dies wird als Typsignatur der Funktion bezeichnet.  Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen" x "annimmt und eine ganze Zahl erstellt.  Beachten Sie, dass der `square` Compiler `int` den Typ für den Moment erteilt hat. Dies liegt daran, dass die Multiplikation nicht für *alle* Typen generisch ist, sondern für einen geschlossenen Satz von Typen generisch ist.  Der F# Compiler hat `int` an dieser Stelle gewählt, aber er passt die Typsignatur an, wenn `square` Sie mit einem `float`anderen Eingabetyp, z. b., aufruft.

Eine weitere Funktion `main`,, ist definiert und wird mit dem `EntryPoint` -Attribut versehen, um F# dem Compiler mitzuteilen, dass die Programmausführung gestartet werden soll.  Es folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code zurück `0`gegeben wird (in der Regel).

In dieser Funktion wird die `square` Funktion mit einem Argument von `12`aufgerufen.  Der F# Compiler weist dann den Typ von `square` zu `int -> int` , d. h. eine Funktion, die einen `int` annimmt und einen `int`erzeugt.  Der-Befehl ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet, ähnlich wie Programmiersprachen im C-Stil, Parameter, die den in der Format Zeichenfolge angegebenen entsprechen, und dann das Ergebnis und eine neue Zeile ausgibt. `printfn`

## <a name="running-your-code"></a>Ausführen des Codes

Sie können den Code ausführen und die Ergebnisse anzeigen, indem Sie **STRG**+**F5**drücken.  Dadurch wird das Programm ohne Debuggen ausgeführt, und Sie können die Ergebnisse anzeigen.  Alternativ können Sie in Visual Studio das Menü Element der obersten Ebene **Debuggen** auswählen und dann **Starten ohne Debugging**auswählen.

Im Konsolenfenster, in dem Visual Studio angezeigt wird, sollte nun Folgendes angezeigt werden:

```
12 squared is 144!
```

Herzlichen Glückwunsch!  Sie haben ihr erstes F# Projekt in Visual Studio erstellt, eine F# Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion gedruckt hat, und das Projekt ausführen, um einige Ergebnisse anzuzeigen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md), die behandelt einige der wichtigsten Funktionen der Sprache F#.  Es wird bieten Ihnen einen Überblick über einige der Funktionen von F# und bieten reichlich Codebeispiele, die Sie in Visual Studio kopieren und ausführen können.  Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können, im gerätekatalog dargestellt die [Leitfaden für F#](../index.md).

## <a name="see-also"></a>Siehe auch

- [Einführung in F#](../tour.md)
- [F#Sprachreferenz](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol-und Operator Verweis](../language-reference/symbol-and-operator-reference/index.md)

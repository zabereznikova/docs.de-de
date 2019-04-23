---
title: Erste Schritte mit F# in Visual Studio
description: Erfahren Sie, wie Sie F# in Visual Studio verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: 020e5d32b3aa5d5a2195c19d70d8fe684fbd56ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331909"
---
# <a name="get-started-with-f-in-visual-studio"></a>Erste Schritte mit F# in Visual Studio

F#und das visuelle F# Tools in Visual Studio-IDE unterstützt werden.

Um zu beginnen, stellen Sie sicher, dass man [Visual Studio installiert, die mit F#](install-fsharp.md#install-f-with-visual-studio).

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eine der grundlegendsten Projekte in Visual Studio ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Sobald Visual Studio geöffnet ist:

1. Auf der **Datei** Startmenü **neu**, und wählen Sie dann **Projekt**.

2. In das neue Projekt im Dialogfeld unter **Vorlagen**, sollte **Visual F#** .  Wählen Sie diese Option, um das Anzeigen der F# Vorlagen.

3. Wählen Sie entweder **.NET Core-Konsolen-app** oder **Konsolen-app**.

3. Wählen Sie die **OK** klicken, um den F#-Projekt zu erstellen!  Eine F#-Projekt im Projektmappen-Explorer sollte nun angezeigt werden.

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

Sie können den Code auszuführen und Ergebnisse angezeigt, durch Drücken von **STRG**+**F5**.  Dies führt das Programm ohne Debuggen und ermöglicht Ihnen, um die Ergebnisse anzuzeigen.  Alternativ können Sie auch die **Debuggen** Menü der obersten Ebene in Visual Studio, und wählen Sie **Starten ohne Debugging**.

Sie sollten jetzt sehen, dass die folgenden im Konsolenfenster anzuzeigen, die Visual Studio eingeblendet wird, wird ausgegeben:

```
12 squared is 144!
```

Herzlichen Glückwunsch!  Sie haben Ihre erste erstellt F# Projekt in Visual Studio geschrieben ein F# Funktion ausgegeben, die Ergebnisse des Aufrufs, die Funktion, und führen Sie das Projekt aus, um einige Ergebnisse anzuzeigen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md), die behandelt einige der wichtigsten Funktionen der Sprache F#.  Es wird bieten Ihnen einen Überblick über einige der Funktionen von F# und bieten reichlich Codebeispiele, die Sie in Visual Studio kopieren und ausführen können.  Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können, im gerätekatalog dargestellt die [Leitfaden für F#](../index.md).

## <a name="see-also"></a>Siehe auch

- [Einführung in F#](../tour.md)
- [F#Referenz zur Abfragesprache](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol und dem Operator-Referenz](../language-reference/symbol-and-operator-reference/index.md)

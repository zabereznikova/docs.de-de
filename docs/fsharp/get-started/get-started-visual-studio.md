---
title: Erste Schritte mit F# in Visual Studio
description: Erfahren Sie, wie Sie F# in Visual Studio verwenden.
ms.date: 07/03/2018
ms.openlocfilehash: e573af67a1fc00b0a340f8c73ab1ee0ed2b97810
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082695"
---
# <a name="get-started-with-f-in-visual-studio"></a>Erste Schritte mit F# in Visual Studio

F# und die visuellen F#-Tools werden in der Visual Studio-IDE unterstützt.

Um zu beginnen, stellen Sie sicher, dass [Visual Studio zusammen mit F# installiert ist](install-fsharp.md#install-f-with-visual-studio).

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Nachdem Visual Studio geöffnet wurde:

1. Zeigen Sie im Menü **Datei** auf **neu**, und wählen Sie dann **Projekt** aus.

2. Im Dialogfeld "Neues Projekt" unter **Vorlagen** sollte **Visualisierung F#** angezeigt werden.  Wählen Sie diese Option aus, um die F#-Vorlagen anzuzeigen.

3. Wählen Sie entweder **Konsolen-App (.NET Core)** oder **Konsolen-App (.NET Framework)** aus.

4. Wählen Sie **OK**, um das F#-Projekt zu erstellen!  Ein F#-Projekt im Projektmappen-Explorer sollte nun angezeigt werden.

## <a name="writing-your-code"></a>Schreiben von Code

Beginnen wir, indem wir zuerst Code schreiben.  Stellen Sie sicher, dass die Datei `Program.fs` geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel wurde eine Funktion `square` definiert, die eine Eingabe mit dem Namen `x` annimmt und diese mit sich selbst multipliziert.  Da F# [Typrückschluss](../language-reference/type-inference.md) verwendet, muss der Typ von `x` nicht angegeben werden.  Der F#-Compiler versteht die Typen, bei denen eine Multiplikation gültig ist, und weist `x` basierend auf dem `square` Aufruf einen Typen zu.  Wenn Sie mit den Cursor auf `square` zeigen, sollte Folgendes angezeigt werden:

```fsharp
val square: x:int -> int
```

Dies wird als Typsignatur der Funktion bezeichnet.  Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen "x" annimmt und eine ganze Zahl zurückgibt."  Beachten Sie, dass für diesen Moment der Compiler `square` den Typ `int` zugewiesen hat. Dies liegt daran, dass die Multiplikation nicht für *alle* Typen generisch ist, aber für eine geschlossene Gruppe von Typen.  Der F#-Compiler hat `int` an dieser Stelle ausgewählt. Er passt die Typsignatur aber an, wenn Sie `square` mit einem anderen Eingabetyp, z. B. `float`, aufrufen.

Eine weitere Funktion `main` ist definiert und wurde mit dem `EntryPoint`-Attribut versehen, um dem F#-Compiler mitzuteilen, dass die Programmausführung hier gestartet werden soll.  Der Ausdruck folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code (in der Regel `0`) zurück gegeben wird.

In dieser Funktion wird die `square`-Funktion mit dem Argument `12` aufgerufen.  Der F#-Compiler weist dann `square` den Typ `int -> int` zu, d. h. eine Funktion, die einen `int` annimmt und einen `int` zurückgibt.  Der `printfn`-Befehl ist eine formatierte Druckfunktion, die eine formatierte Zeichenfolge verwendet, ähnlich wie andere Programmiersprachen im C-Stil. Übergebene Parameter werden der formatierten Zeichenfolge entsprechen formatiert, dann werden das Ergebnis und eine neue Zeile ausgegeben.

## <a name="running-your-code"></a>Ausführen des Codes

Sie können den Code ausführen und die Ergebnisse anzeigen, indem Sie **STRG**+**F5** drücken.  Dadurch wird das Programm ohne Debuggen ausgeführt, und Sie können die Ergebnisse anzeigen.  Alternativ können Sie in Visual Studio in der obersten Ebene das Menü-Element  **Debuggen** auswählen und dann **Starten ohne Debugging** auswählen.

Im Konsolenfenster, das durch Visual Studio anzeigt wird, sollte nun Folgendes angezeigt werden:

```console
12 squared is 144!
```

Herzlichen Glückwunsch!  Sie haben Ihr erstes F#-Projekt in Visual Studio erstellt, eine F#-Funktion geschrieben, die die Ergebnisse des Aufrufs dieser Funktion ausgegeben hat, und das Projekt ausgeführt, um einige Ergebnisse anzuzeigen.

## <a name="next-steps"></a>Nächste Schritte

Falls Sie es nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md)an. Diese behandelt einige der wichtigsten Funktionen der Sprache F#.  Es werden Ihnen einen Überblick über einige der Funktionen von F# mit reichlich Codebeispiele geboten, die Sie in Visual Studio kopieren und ausführen können.  Es gibt auch einige hervorragenden externe Ressourcen, die Sie verwenden können und die in der Übersicht [Leitfaden für F#](../index.md) dargestellt sind.

## <a name="see-also"></a>Siehe auch

- [Einführung in F#](../tour.md)
- [F#-Sprachreferenz](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol-und Operator Verweis](../language-reference/symbol-and-operator-reference/index.md)

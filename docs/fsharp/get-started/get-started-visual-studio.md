---
title: Erste Schritte mit F# in Visual Studio
description: Erfahren Sie, wie Sie F# in Visual Studio verwenden.
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337349"
---
# <a name="get-started-with-f-in-visual-studio"></a>Erste Schritte mit F# in Visual Studio

F#und die visuellen F# Tools werden in der integrierten Entwicklungsumgebung (IDE) von Visual Studio unterstützt.

Vergewissern Sie sich zunächst, dass [Visual Studio mit F# Unterstützung installiert](install-fsharp.md#install-f-with-visual-studio)ist.

## <a name="create-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio ist die Konsolen-app. Gehen Sie zum Erstellen wie folgt vor:

1. Öffnen Sie Visual Studio 2019.

2. Wählen Sie im Startfenster **Neues Projekt erstellen** aus.

3. Wählen Sie **F#** auf der Seite **Neues Projekt erstellen** aus der Liste Sprache aus.

4. Wählen Sie die Vorlage **Konsolen-app (.net Core)** aus, und klicken Sie dann auf **weiter**.

5. Geben Sie auf der Seite **Neues Projekt konfigurieren** einen Namen in das Feld **Projektname** ein. Wählen Sie anschließend **Erstellen**.

   Visual Studio erstellt das neue F# Projekt. Sie können Sie im Projektmappen-Explorer Fenster sehen.

## <a name="write-the-code"></a>Den Code schreiben

Wir beginnen mit dem Schreiben von Code. Stellen Sie sicher, dass die Datei `Program.fs` geöffnet ist, und ersetzen Sie deren Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel wird eine Funktion mit dem Namen "`square`" definiert, die eine Eingabe mit dem Namen "`x`" annimmt und Sie selbst multipliziert. Da F# den [Typrückschluss](../language-reference/type-inference.md)verwendet, muss der Typ der `x` nicht angegeben werden. Der F# Compiler versteht die Typen, bei denen Multiplikation gültig ist, und weist `x` basierend auf der Aufruf `square` einen Typ zu. Wenn Sie mit den Cursor auf `square` zeigen, sollte Folgendes angezeigt werden:

```fsharp
val square: x:int -> int
```

Dies wird als Typsignatur der Funktion bezeichnet. Sie kann wie folgt gelesen werden: "Square ist eine Funktion, die eine ganze Zahl mit dem Namen x annimmt und eine ganze Zahl erzeugt." Der Compiler hat dem `int`-Typ jetzt `square`. Dies liegt daran, dass die Multiplikation nicht in *allen* Typen generisch ist, sondern eher ein geschlossener Satz von Typen. Der F# Compiler passt die Typsignatur an, wenn Sie `square` mit einem anderen Eingabetyp (z. b. einer `float`) aufzurufen.

Eine weitere Funktion, `main`, ist definiert und wird mit dem `EntryPoint`-Attribut ergänzt. Dieses Attribut weist den F# Compiler an, dass die Programmausführung gestartet werden soll. Der Ausdruck folgt derselben Konvention wie andere [Programmiersprachen im C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), bei denen Befehlszeilenargumente an diese Funktion übermittelt werden können, und ein ganzzahliger Code (in der Regel `0`) zurück gegeben wird.

Sie befindet sich in der Einstiegspunkt Funktion `main`, dass Sie die `square`-Funktion mit einem Argument von `12`aufzurufen. Der F# Compiler weist dann den Typ des `square` zu, der `int -> int` werden soll (d. h. eine Funktion, die eine `int` annimmt und eine `int`erzeugt). Der `printfn`-Aufrufe ist eine formatierte Druckfunktion, die eine Format Zeichenfolge verwendet und das Ergebnis (und eine neue Zeile) ausgibt. Die Format Zeichenfolge, ähnlich wie Programmiersprachen im C-Stil, verfügt über Parameter (`%d`), die den an Sie über gebenden Argumenten entsprechen, in diesem Fall `12` und `(square 12)`.

## <a name="run-the-code"></a>Ausführen des Codes

Sie können den Code ausführen und die Ergebnisse anzeigen, indem Sie **STRG**+**F5**drücken. Alternativ können Sie das **Debuggen** > **Starten ohne Debuggen** in der Menüleiste der obersten Ebene auswählen. Dadurch wird das Programm ohne Debuggen ausgeführt.

Die folgende Ausgabe wird im Konsolenfenster ausgegeben, das von Visual Studio geöffnet wurde:

```console
12 squared is: 144!
```

Herzlichen Glückwunsch! Sie haben ihr erstes F# Projekt in Visual Studio erstellt, eine F# Funktion geschrieben, die einen Wert berechnet und druckt, und das Projekt ausführen, um die Ergebnisse anzuzeigen.

## <a name="next-steps"></a>Nächste Schritte

Falls Sie es nicht bereits getan haben, sehen Sie sich die [Einführung in F#](../tour.md)an. Diese behandelt einige der wichtigsten Funktionen der Sprache F#. Es bietet eine Übersicht über einige der Funktionen von F# und zahlreiche Codebeispiele, die Sie in Visual Studio kopieren und ausführen können.

> [!div class="nextstepaction"]
> [Einführung in F#](../tour.md)

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](../language-reference/index.md)
- [Typrückschluss](../language-reference/type-inference.md)
- [Symbol-und Operator Verweis](../language-reference/symbol-and-operator-reference/index.md)

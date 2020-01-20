---
title: Untersuchen von Code mit der Roslyn-Syntaxschnellansicht in Visual Studio Code
description: Die Syntaxschnellansicht bietet ein visuelles Tool, um die Modelle zu untersuchen, die das .NET Compiler Platform SDK für Code generiert.
ms.date: 03/07/2018
ms.custom: mvc, vs-dotnet
ms.openlocfilehash: c4b4414dabcb6c9749a23d726e4a69334376d988
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346963"
---
# <a name="explore-code-with-the-roslyn-syntax-visualizer-in-visual-studio"></a>Untersuchen von Code mit der Roslyn-Syntaxschnellansicht in Visual Studio Code

Dieser Artikel enthält eine Übersicht über das Syntaxschnellansichtstool, das als Teil des .NET Compiler Platform („Roslyn“) SDK geliefert wird. Die Syntaxschnellansicht ist ein Toolfenster, das Ihnen beim Prüfen und Untersuchen von Syntaxstrukturen hilft. Es ist ein grundlegendes Tool, um die Modelle für den Code zu verstehen, die Sie analysieren möchten. Es ist auch eine Hilfe beim Debuggen, wenn Sie Ihre eigenen Anwendungen unter Verwendung des .NET Compiler Platform („Roslyn“) SDK entwickeln. Öffnen Sie dieses Tool, wenn Sie Ihre ersten Analysetools erstellen. Die Schnellansicht hilft Ihnen, die von den APIs verwendeten Modelle zu verstehen. Sie können auch Tools wie [SharpLab](https://sharplab.io) oder [LINQPad](https://www.linqpad.net/) verwenden, um Code zu untersuchen und Syntaxstrukturen zu verstehen.

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

Lesen Sie den Artikel zur [Übersicht](compiler-api-model.md), und machen Sie sich mit den Konzepten vertraut, die im .NET Compiler Platform SDK verwendet werden. Er gibt eine Übersicht über Syntaxstrukturen, Knoten, Tokens und Trivia.

## <a name="syntax-visualizer"></a>Syntaxschnellansicht

Die **Syntaxschnellansicht** ermöglicht die Untersuchung der Syntaxstruktur für die C#- oder Visual Basic-Codedatei im aktuellen aktiven Editor-Fenster in der integrierten Entwicklungsumgebung (IDE) von Visual Studio. Die Schnellansicht kann gestartet werden, indem Sie auf **Ansicht** > **Andere Fenster** > **Syntaxschnellansicht** klicken.  Sie können auch die **Schnellstart**-Symbolleiste in der oberen rechten Ecke verwenden. Geben Sie „syntax“ ein, und der Befehl zum Öffnen der **Syntaxschnellansicht** sollte erscheinen.

Dieser Befehl öffnet die Syntaxschnellansicht als unverankertes Toolfenster. Wenn Sie kein Code-Editor-Fenster geöffnet haben, ist die Anzeige leer, wie in der folgenden Abbildung dargestellt. 

![Das Toolfenster der Syntaxschnellansicht](media/syntax-visualizer/syntax-visualizer.png)

Docken Sie dieses Toolfenster an einem geeigneten Ort innerhalb von Visual Studio an, z.B. an die linke Seite. Die Schnellansicht zeigt Informationen über die aktuelle Codedatei.

Erstellen Sie ein neues Projekt mit dem Befehl **Datei** > **Neues Projekt**. Sie können ein Visual Basic- oder ein C#-Projekt erstellen. Wenn Visual Studio die Haupt-Codedatei für dieses Projekt öffnet, zeigt die Schnellansicht die entsprechende Syntaxstruktur an. Sie können eine beliebige C#-/Visual Basic-Datei in dieser Instanz von Visual Studio öffnen, und die Schnellansicht zeigt die Syntaxstruktur dieser Datei an. Wenn Sie mehrere Codedateien in Visual Studio geöffnet haben, zeigt die Schnellansicht die Syntaxstruktur für die derzeit aktive Codedatei (die Codedatei, die über den Tastaturfokus verfügt) an.

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Visualisieren einer C#-Syntaxstruktur](media/syntax-visualizer/visualize-csharp.png)

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)
![Visualisieren einer Visual Basic-Syntaxstruktur](media/syntax-visualizer/visualize-visual-basic.png)

---

Wie in den vorherigen Abbildungen dargestellt wird, zeigt das Schnellansichts-Toolfenster die Syntaxstruktur oben und ein Eigenschaftenraster unten an. Das Eigenschaftenraster zeigt die Eigenschaften des Elements an, das derzeit in der Struktur ausgewählt ist, einschließlich .NET-*Typ* und *Art* (SyntaxKind) des Elements.

Syntaxstrukturen umfassen drei Typen von Elementen: *Knoten*, *Token*, und *Trivia*. Sie können mehr über diese Typen im Artikel zum [Arbeiten mit Syntax](work-with-syntax.md) erfahren. Elemente der einzelnen Typen werden mit einer bestimmten Farbe dargestellt. Klicken Sie für einen Überblick über die verwendeten Farben auf die Schaltfläche „Legende“.

Jedes Element in der Struktur zeigt außerdem seinen eigenen **Bereich** an. Der **Bereich** umfasst die Indizes (Start- und Endposition) des Knotens in der Textdatei.  Im vorherigen C#-Beispiel hat das ausgewählte Token „UsingKeyword [0..5)“ einen **Bereich**, der fünf Zeichen breit ist, [0..5). Die Notation „[..)“ bedeutet, dass der Startindex Teil des Bereichs ist, der Endindex allerdings nicht.

Es gibt zwei Möglichkeiten, in der Struktur zu navigieren:

* Erweitern oder klicken Sie auf Elemente in der Struktur. Die Schnellansicht wählt automatisch den entsprechenden Text aus, der zum Bereich des Elements im Code-Editor gehört.
* Klicken Sie auf oder wählen Sie Text im Code-Editor. Wenn Sie im vorangegangenen Visual Basic-Beispiel die Zeile mit „Module Module1“ im Code-Editor auswählen, navigiert die Schnellansicht automatisch zum entsprechenden ModuleStatement-Knoten in der Struktur. 

Die Schnellansicht markiert das Element in der Struktur, dessen Bereich am besten zum Bereich des im Editor ausgewählten Texts passt.

Die Schnellansicht aktualisiert die Struktur, um Änderungen in der aktiven Codedatei abzubilden. Fügen Sie einen Aufruf von `Console.WriteLine()` innerhalb von `Main()` hinzu. Während der Eingabe aktualisiert die Schnellansicht die Struktur.

Unterbrechen Sie die Eingabe, nachdem Sie `Console.` eingegeben haben. Die Struktur besitzt einige rosa gefärbte Elemente. Zu diesem Zeitpunkt bestehen Fehler (auch als „Diagnose“ bezeichnet) in dem eingegebenen Code. Diese Fehler hängen mit Knoten, Tokens und Trivia in der Syntaxstruktur zusammen. Die Schnellansicht zeigt Ihnen, welche Elemente fehlerbehaftet sind, indem sie den Hintergrund rosa markiert. Sie können die Fehler an jedem rosa gefärbten Element überprüfen, indem Sie mit dem Mauszeiger auf das Element zeigen. Die Schnellansicht zeigt nur syntaktische Fehler an (das sind Fehler im Zusammenhang mit der Syntax des eingegebenen Codes); sie zeigt keine semantischen Fehler an.
 
## <a name="syntax-graphs"></a>Syntaxdiagramme

Klicken Sie mit der rechten Maustaste auf ein beliebiges Element in der Struktur, und klicken Sie auf **Gerichtetes Syntax-Diagramm anzeigen**. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

Die Schnellansicht zeigt eine grafische Darstellung des Teilbaums, der von dem ausgewählten Element abstammt. Versuchen Sie diese Schritte für den **MethodDeclaration**-Knoten, der der `Main()`-Methode im C#-Beispiel entspricht. Die Schnellansicht zeigt ein Syntaxdiagramm an, das wie folgt aussieht:

![C#-Syntaxdiagramm](media/syntax-visualizer/csharp-syntax-graph.png)

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

Versuchen Sie das Gleiche für den **SubBlock**-Knoten, der der `Main()`-Methode im vorangehenden Visual Basic-Beispiel entspricht. Die Schnellansicht zeigt ein Syntaxdiagramm an, das wie folgt aussieht:

![Anzeigen eines Visual Basic-Syntaxgraphen](media/syntax-visualizer/visual-basic-syntax-graph.png)

---

Der Syntaxdiagramm-Viewer verfügt über eine Option zum Anzeigen seines Farbschemas. Sie können auch mit dem Mauszeiger auf einzelne Elemente im Syntaxdiagramm zeigen, um die Eigenschaften des jeweiligen Elements anzuzeigen.

Sie können Syntaxdiagramme für verschiedene Elemente in der Struktur wiederholt anzeigen lassen. Die Diagramme werden immer im gleichen Fenster innerhalb von Visual Studio angezeigt. Sie können dieses Fenster an einem geeigneten Ort innerhalb von Visual Studio andocken, damit Sie zum Anzeigen eines neuen Syntaxdiagramms nicht zwischen Registerkarten hin- und herwechseln müssen. Der untere Bereich, unter dem Fenster des Code-Editors, bietet sich oft an.

So sieht das Docking-Layout für die Verwendung mit dem Schnellansichts-Toolfenster und dem Syntaxdiagramm aus:

![Ein Docking-Layout für Schnellansichts- und Syntaxdiagrammfenster](media/syntax-visualizer/docking-layout.png)

Bei einem Setup mit zwei Monitoren kann das Syntaxdiagramm auch auf einen zweiten Monitor gelegt werden.

## <a name="inspecting-semantics"></a>Überprüfen der Semantik

Die Syntaxschnellansicht ermöglicht die rudimentäre Überprüfung von Symbolen und semantischen Informationen. Geben Sie `double x = 1 + 1;` innerhalb von Main() im C#-Beispiel ein. Wählen Sie dann den Ausdruck `1 + 1` im Code-Editor-Fenster. Die Schnellansicht hebt den **AddExpression**-Knoten in der Schnellansicht hervor. Klicken Sie mit der rechten Maustaste auf **AddExpression**, und klicken Sie dann auf **View Symbol (if any)** (Symbol anzeigen (sofern vorhanden)). Beachten Sie, dass die meisten Menüelemente über den Qualifizierer „if any“ (sofern vorhanden) verfügen. Die Syntaxschnellansicht untersucht Eigenschaften eines Knotens, einschließlich Eigenschaften, die möglicherweise nicht bei allen Knoten vorhanden sind. 

Das Eigenschaftenraster in der Schnellansicht wird wie in der folgenden Abbildung gezeigt aktualisiert: Das Symbol für den Ausdruck ist ein **SynthesizedIntrinsicOperatorSymbol** mit **Kind = Method**.

![Symboleigenschaften](media/syntax-visualizer/symbol-properties.png)

Versuchen Sie **View TypeSymbol (if any)** (TypeSymbol anzeigen (sofern vorhanden)) für den gleichen **AddExpression**-Knoten. Das Eigenschaftenraster in der Schnellansicht wird wie in der folgenden Abbildung aktualisiert und zeigt an, dass der Typ des gewählten Ausdrucks `Int32` ist.

![Eigenschaften von TypeSymbol](media/syntax-visualizer/type-symbol-properties.png)

Versuchen Sie **View Converted TypeSymbol (if any)** (Konvertiertes TypeSymbol anzeigen (sofern vorhanden)) für den gleichen **AddExpression**-Knoten. Das aktualisierte Eigenschaftenraster zeigt an, dass zwar der Typ des Ausdrucks `Int32` ist, der konvertierte Typ des Ausdrucks aber `Double` ist, wie in der folgenden Abbildung gezeigt. Dieser Knoten beinhaltet konvertierte TypeSymbol-Eigenschaften, da der `Int32`-Ausdruck in einem Kontext erscheint, in dem er zu `Double` konvertiert werden muss. Diese Konvertierung erfüllt den `Double`-Typ für die Variable `x` auf der linken Seite des Zuweisungsoperators.

![Eigenschaften von TypeSymbol (konvertiert)](media/syntax-visualizer/converted-type-symbol-properties.png)

Versuchen Sie als Letztes **View Constant Value (if any)** (Konstanten Wert anzeigen (sofern vorhanden)) für den gleichen **AddExpression**-Knoten. Das Eigenschaftenraster zeigt an, dass der Wert des Ausdrucks eine kompilierte Zeitkonstante mit dem Wert `2` ist.

![Ein konstanter Wert](media/syntax-visualizer/constant-value.png)

Das vorherige Beispiel kann auch in Visual Basic repliziert werden. Geben Sie `Dim x As Double = 1 + 1` in einer Visual Basic-Datei ein. Wählen Sie den Ausdruck `1 + 1` im Code-Editor-Fenster. Die Schnellansicht hebt den entsprechenden **AddExpression**-Knoten in der Schnellansicht hervor. Wiederholen Sie die vorherigen Schritte für **AddExpression**, und Sie sollten identische Ergebnisse erhalten.

Untersuchen Sie weiteren Code in Visual Basic. Aktualisieren Sie Ihre Visual Basic-Hauptdatei mit dem folgenden Code:

```vb
Imports C = System.Console

Module Program
    Sub Main(args As String())
        C.WriteLine()
    End Sub
End Module
```

Dieser Code führt einen Alias mit dem Namen `C` ein, der dem Typ `System.Console` am Anfang der Datei zugeordnet ist und verwendet diesen Alias in `Main()`. Wählen Sie die Verwendung dieses Alias aus, der `C` in `C.WriteLine()`, innerhalb der `Main()`-Methode. Die Schnellansicht wählt den entsprechenden **IdentifierName**-Knoten in der Schnellansicht aus. Klicken Sie mit der rechten Maustaste auf diesen Knoten, und klicken Sie auf **Symbol anzeigen (sofern vorhanden)** . Das Eigenschaftenraster zeigt an, dass dieser Bezeichner an den Typ `System.Console` gebunden ist, wie in der nachfolgenden Abbildung gezeigt:

![Symboleigenschaften](media/syntax-visualizer/symbol-visual-basic.png)

Versuchen Sie **View AliasSymbol (if any)** (AliasSymbol anzeigen (sofern vorhanden)) für den gleichen **IdentifierName**-Knoten. Das Eigenschaftenraster zeigt an, dass der Bezeichner ein Alias mit dem Namen `C` ist, der an das Ziel `System.Console` gebunden ist. Mit anderen Worten: Das Eigenschaftenraster liefert Informationen in Bezug auf das **AliasSymbol**, das zum Bezeichner `C` gehört.

![AliasSymbol-Eigenschaften](media/syntax-visualizer/alias-symbol.png)

Untersuchen Sie das Symbol auf deklarierten Typ, Methode, Eigenschaft. Wählen Sie den entsprechenden Knoten in der Schnellansicht aus, und klicken Sie auf **Symbol anzeigen (sofern vorhanden)** . Wählen Sie die Methode `Sub Main()`, einschließlich des Textkörpers der Methode. Klicken Sie auf **Symbol anzeigen (sofern vorhanden)** für den entsprechenden **SubBlock**-Knoten in der Schnellansicht. Das Eigenschaftenraster zeigt, dass das **MethodSymbol** für diesen **SubBlock** den Namen `Main` mit Rückgabetyp `Void` hat.

![Symbol für eine Methodendeklaration anzeigen](media/syntax-visualizer/method-symbol.png)

Die oben genannten Visual Basic-Beispiele können problemlos in C# reproduziert werden. Geben Sie `using C = System.Console;` anstelle von `Imports C = System.Console` für den Alias ein. Die vorhergehenden Schritte in C# ergeben identische Ergebnisse im Schnellansichtsfenster.

Semantische Überprüfungsvorgänge sind nur an Knoten verfügbar. Sie sind nicht an Tokens oder Trivia verfügbar. Nicht alle Knoten haben relevante semantische Informationen, die überprüft werden können. Wenn ein Knoten keine relevanten semantischen Informationen hat, wird beim Klicken auf **Symbol \* anzeigen (sofern vorhanden)** ein leeres Eigenschaftenraster angezeigt.

Sie können mehr über APIs für die semantische Analyse im Übersichtsdokument [Arbeiten mit der Semantik](work-with-semantics.md) erfahren.

## <a name="closing-the-syntax-visualizer"></a>Schließen der Syntaxschnellansicht

Sie können das Schnellansichtsfenster schließen, wenn Sie es nicht zum Untersuchen von Quellcode verwenden. Die Syntaxschnellansicht aktualisiert ihre Darstellung, während Sie durch Code navigieren und ihn bearbeiten oder verändern. Das kann störend sein, wenn die Schnellansicht nicht verwendet wird. 

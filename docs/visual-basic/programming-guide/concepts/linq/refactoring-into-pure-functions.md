---
title: Refactoring in reine Funktionen
ms.date: 07/20/2015
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
ms.openlocfilehash: 415b088661eca347330f4776901d68ee514d8dad
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413478"
---
# <a name="refactoring-into-pure-functions-visual-basic"></a>Refactoring in reine Funktionen (Visual Basic)

Ein wichtiger Aspekt bei dem Studium reiner funktionaler Transformationen besteht darin zu lernen, wie Code mit reinen Funktionen umgestaltet werden kann.

Wie bereits weiter oben erwähnt, besitzt eine reine Funktion zwei nützliche Eigenschaften:

- Sie hat keine Nebenwirkungen. Die Funktion ändert keine Variablen oder Daten irgendeines Typs außerhalb der Funktion.

- Sie ist konsistent. Bei identischen Eingabedaten gibt die Funktion immer denselben Ausgabewert zurück.

 Eine Möglichkeit des Umstiegs auf die funktionale Programmierung besteht darin, vorhandenen Code umzugestalten und so unnötige Nebenwirkungen und externe Abhängigkeiten abzuschaffen. Auf diese Weise können Sie Versionen von reinen Funktionen von vorhandenem Code erstellen.

In diesem Thema wird erläutert, was eine reine Funktion ist und was nicht. Im [Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) erfahren Sie, wie Sie ein WordprocessingML-Dokument bearbeiten können. Außerdem enthält es zwei Beispiele für das Umgestalten mithilfe einer reinen Funktion.

## <a name="eliminating-side-effects-and-external-dependencies"></a>Beseitigen von Nebenwirkungen und externen Abhängigkeiten

In den folgenden Beispielen werden zwei nicht reine Funktionen einer reinen Funktion gegenübergestellt.

### <a name="non-pure-function-that-changes-a-class-member"></a>Nicht reine Funktion, die einen Klassenmember ändert

Im folgenden Code ist die `HyphenatedConcat`-Funktion keine reine Funktion, da sie den `aMember`-Datenmember in der Klasse ändert:

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

Dieser Code erzeugt die folgende Ausgabe:

```console
StringOne-StringTwo
```

Beachten Sie, dass es unerheblich ist, ob die geänderten Daten über oder zugreifen oder ob es `public` `private` sich um einen `shared` Member oder einen Instanzmember handelt. Reine Funktionen führen zu keinerlei Änderungen an Daten außerhalb der Funktion.

### <a name="non-pure-function-that-changes-an-argument"></a>Nicht reine Funktion, die ein Argument ändert

Außerdem ist die folgende Version derselben Funktion keine reine Funktion, weil sie den Inhalt ihres Parameters, `sb`, ändert.

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

Diese Version des Programms produziert dieselbe Ausgabe wie die erste Version, weil die `HyphenatedConcat`-Funktion durch Aufrufen der <xref:System.Text.StringBuilder.Append%2A>-Memberfunktion den Wert (Status) ihres ersten Parameters geändert hat. Beachten Sie, dass diese Änderung trotz der Tatsache auftritt, dass `HyphenatedConcat` mit Wertparameterübergabe arbeitet.

> [!IMPORTANT]
> Wenn Sie bei Verweistypen einen Parameter nach Wert übergeben, führt dies zu einer Kopie des Verweises auf ein zu übergebendes Objekt. Diese Kopie ist weiterhin mit denselben Instanzdaten wie der ursprüngliche Verweis verknüpft (so lange, bis die Verweisvariable einem neuen Objekt zugewiesen wird). Für das Ändern eines Parameters durch einen Parameter ist die Referenzparameterübergabe nicht unbedingt erforderlich.

### <a name="pure-function"></a>Reine Funktion

Die nächste Version des Programms zeigt, wie die `HyphenatedConcat`-Funktion als reine Funktion implementiert werden kann.

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

Auch diese Version erzeugt dieselbe Zeile in der Ausgabe: `StringOne-StringTwo`. Um den verketteten Wert beizubehalten, wird er in der Zwischenvariable `s2` gespeichert.

Ein Ansatz, der sich als sehr hilfreich erweisen kann, besteht darin, Funktionen zu schreiben, die zwar lokal unrein (also lokale Variablen deklarieren und ändern), global aber rein sind. Solche Funktionen besitzen viele der wünschenswerten Zusammensetzbarkeitseigenschaften, vermeiden dabei aber einige der komplizierteren Idiome der funktionalen Programmierung, z. B. die Notwendigkeit der Verwendung der Rekursion, wenn eine einfache Schleife dasselbe Ziel erreichen würde.

## <a name="standard-query-operators"></a>Standardabfrageoperatoren

Ein wichtiges Merkmal der Standardabfrageoperatoren besteht darin, dass sie als reine Funktionen implementiert sind.

Weitere Informationen finden Sie unter [Übersicht über Standard Abfrage Operatoren (Visual Basic)](standard-query-operators-overview.md).

## <a name="see-also"></a>Weitere Informationen

- [Einführung in reine funktionale Transformationen (Visual Basic)](introduction-to-pure-functional-transformations.md)
- [Funktionale Programmierung im Vergleich zu imperativer Programmierung (Visual Basic)](functional-programming-vs-imperative-programming.md)

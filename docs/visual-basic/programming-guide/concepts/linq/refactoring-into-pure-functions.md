---
title: Umgestalten in reine Funktionen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e622436905893872521994f6dc1a5bc1c8b3d06a
ms.lasthandoff: 03/13/2017


---
# <a name="refactoring-into-pure-functions-visual-basic"></a>Umgestalten in reine Funktionen (Visual Basic)
Ein wichtiger Aspekt bei dem Studium reiner funktionaler Transformationen besteht darin zu lernen, wie Code mit reinen Funktionen umgestaltet werden kann.  
  
 Wie bereits weiter oben erwähnt, besitzt eine reine Funktion zwei nützliche Eigenschaften:  
  
-   Sie hat keine Nebenwirkungen. Die Funktion ändert keine Variablen oder Daten irgendeines Typs außerhalb der Funktion.  
  
-   Sie ist konsistent. Bei identischen Eingabedaten gibt die Funktion immer denselben Ausgabewert zurück.  
  
 Eine Möglichkeit des Umstiegs auf die funktionale Programmierung besteht darin, vorhandenen Code umzugestalten und so unnötige Nebenwirkungen und externe Abhängigkeiten abzuschaffen. Auf diese Weise können Sie Versionen von reinen Funktionen von vorhandenem Code erstellen.  
  
 In diesem Thema wird erläutert, was eine reine Funktion ist und was nicht. Die [Lernprogramm: Bearbeiten des Inhalts eines WordprocessingML-Dokuments (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) Lernprogramm zeigt, wie Sie ein WordprocessingML-Dokument bearbeiten können, und enthält zwei Beispiele für das Umgestalten mit einer reinen Funktion.  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a>Beseitigen von Nebenwirkungen und externen Abhängigkeiten  
 In den folgenden Beispielen werden zwei nicht reine Funktionen einer reinen Funktion gegenübergestellt.  
  
### <a name="non-pure-function-that-changes-a-class-member"></a>Nicht reine Funktion, die einen Klassenmember ändert  
 Im folgenden Code ist die `HypenatedConcat`-Funktion keine reine Funktion, da sie den `aMember`-Datenmember in der Klasse ändert:  
  
```vb  
Module Module1  
    Dim aMember As String = "StringOne"  
  
    Public Sub HypenatedConcat(ByVal appendStr As String)  
        aMember = aMember & "-" & appendStr  
    End Sub  
  
    Sub Main()  
        HypenatedConcat("StringTwo")  
        Console.WriteLine(aMember)  
    End Sub  
End Module  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
StringOne-StringTwo  
```  
  
 Beachten Sie, dass spielt, ob die zu ändernden Daten `public` oder `private` Zugriff, oder eine `shared` Member bzw. ein Instanzmember. Reine Funktionen führen zu keinerlei Änderungen an Daten außerhalb der Funktion.  
  
### <a name="non-pure-function-that-changes-an-argument"></a>Nicht reine Funktion, die ein Argument ändert  
 Außerdem ist die folgende Version derselben Funktion keine reine Funktion, weil sie den Inhalt ihres Parameters, `sb`, ändert.  
  
```vb  
Module Module1  
    Public Sub HypenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)  
        sb.Append("-" & appendStr)  
    End Sub  
  
    Sub Main()  
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")  
        HypenatedConcat(sb1, "StringTwo")  
        Console.WriteLine(sb1)  
    End Sub  
End Module  
```  
  
 Diese Version des Programms produziert dieselbe Ausgabe wie die erste Version, weil die `HypenatedConcat` Funktion den Wert (Status) ihres ersten Parameters geändert hat, durch den Aufruf der <xref:System.Text.StringBuilder.Append%2A>-Memberfunktion.</xref:System.Text.StringBuilder.Append%2A> Beachten Sie, dass diese Änderung trotz der Tatsache auftritt, dass `HypenatedConcat` mit Wertparameterübergabe arbeitet.  
  
> [!IMPORTANT]
>  Wenn Sie bei Verweistypen einen Parameter nach Wert übergeben, führt dies zu einer Kopie des Verweises auf ein zu übergebendes Objekt. Diese Kopie ist weiterhin mit denselben Instanzdaten wie der ursprüngliche Verweis verknüpft (so lange, bis die Verweisvariable einem neuen Objekt zugewiesen wird). Für das Ändern eines Parameters durch einen Parameter ist die Referenzparameterübergabe nicht unbedingt erforderlich.  
  
### <a name="pure-function"></a>Reine Funktion  
 Die nächste Version des Programms zeigt, wie die `HypenatedConcat`-Funktion als reine Funktion implementiert werden kann.  
  
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
  
 Weitere Informationen finden Sie unter [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in reine funktionale Transformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)   
 [Funktionale Programmierung und Imperative Programmierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)

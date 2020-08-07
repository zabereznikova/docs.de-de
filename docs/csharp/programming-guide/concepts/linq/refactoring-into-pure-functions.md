---
title: Refactoring in reine Funktionen (C#)
description: Erfahren Sie, wie Sie Code mithilfe von reinen Funktionen umgestalten. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: cc5dd26923e2edaed34c8f1b742b3dfa1e935e68
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300227"
---
# <a name="refactoring-into-pure-functions-c"></a>Refactoring in reine Funktionen (C#)

Ein wichtiger Aspekt bei dem Studium reiner funktionaler Transformationen besteht darin zu lernen, wie Code mit reinen Funktionen umgestaltet werden kann.  
  
> [!NOTE]
> Nach der allgemeinen Nomenklatur bei der funktionalen Programmierung werden Programme mit reinen Funktionen umgestaltet. In Visual Basic und C++ geht dies mit der Verwendung von Funktionen in den jeweiligen Sprachen einher. In C# werden Funktionen aber als Methoden bezeichnet. Im Rahmen dieser Erläuterung ist die reine Funktion als C#-Methode implementiert.  
  
 Wie bereits weiter oben erwähnt, besitzt eine reine Funktion zwei nützliche Eigenschaften:  
  
- Sie hat keine Nebenwirkungen. Die Funktion ändert keine Variablen oder Daten irgendeines Typs außerhalb der Funktion.  
  
- Sie ist konsistent. Bei identischen Eingabedaten gibt die Funktion immer denselben Ausgabewert zurück.  
  
 Eine Möglichkeit des Umstiegs auf die funktionale Programmierung besteht darin, vorhandenen Code umzugestalten und so unnötige Nebenwirkungen und externe Abhängigkeiten abzuschaffen. Auf diese Weise können Sie Versionen von reinen Funktionen von vorhandenem Code erstellen.  
  
 In diesem Thema wird erläutert, was eine reine Funktion ist und was nicht. Im [Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))](./shape-of-wordprocessingml-documents.md) wird gezeigt, wie Sie ein WordprocessingML-Dokument bearbeiten können. Außerdem enthält dieses Tutorial zwei Beispiele für das Umgestalten mithilfe einer reinen Funktion.  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a>Beseitigen von Nebenwirkungen und externen Abhängigkeiten  
 In den folgenden Beispielen werden zwei nicht reine Funktionen einer reinen Funktion gegenübergestellt.  
  
### <a name="non-pure-function-that-changes-a-class-member"></a>Nicht reine Funktion, die einen Klassenmember ändert  
 Im folgenden Code ist die `HyphenatedConcat`-Funktion keine reine Funktion, da sie den `aMember`-Datenmember in der Klasse ändert:  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HyphenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HyphenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```output  
StringOne-StringTwo  
```  
  
 Ob die zu ändernden Daten `public`-Zugriff oder `private`-Zugriff besitzen oder ein `static`-Member bzw. ein Instanzmember sind, spielt keine Rolle. Reine Funktionen führen zu keinerlei Änderungen an Daten außerhalb der Funktion.  
  
### <a name="non-pure-function-that-changes-an-argument"></a>Nicht reine Funktion, die ein Argument ändert  
 Außerdem ist die folgende Version derselben Funktion keine reine Funktion, weil sie den Inhalt ihres Parameters, `sb`, ändert.  
  
```csharp  
public class Program  
{  
    public static void HyphenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HyphenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 Diese Version des Programms produziert dieselbe Ausgabe wie die erste Version, weil die `HyphenatedConcat`-Funktion durch Aufrufen der <xref:System.Text.StringBuilder.Append%2A>-Memberfunktion den Wert (Status) ihres ersten Parameters geändert hat. Beachten Sie, dass diese Änderung trotz der Tatsache auftritt, dass `HyphenatedConcat` mit Wertparameterübergabe arbeitet.  
  
> [!IMPORTANT]
> Wenn Sie bei Verweistypen einen Parameter nach Wert übergeben, führt dies zu einer Kopie des Verweises auf ein zu übergebendes Objekt. Diese Kopie ist weiterhin mit denselben Instanzdaten wie der ursprüngliche Verweis verknüpft (so lange, bis die Verweisvariable einem neuen Objekt zugewiesen wird). Für das Ändern eines Parameters durch einen Parameter ist die Referenzparameterübergabe nicht unbedingt erforderlich.  
  
### <a name="pure-function"></a>Reine Funktion  
Die nächste Version des Programms zeigt, wie die `HyphenatedConcat`-Funktion als reine Funktion implementiert werden kann.  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 Auch diese Version erzeugt dieselbe Zeile in der Ausgabe: `StringOne-StringTwo`. Um den verketteten Wert beizubehalten, wird er in der Zwischenvariable `s2` gespeichert.  
  
 Ein Ansatz, der sich als sehr hilfreich erweisen kann, besteht darin, Funktionen zu schreiben, die zwar lokal unrein (also lokale Variablen deklarieren und ändern), global aber rein sind. Solche Funktionen besitzen viele der wünschenswerten Zusammensetzbarkeitseigenschaften, vermeiden dabei aber einige der komplizierteren Idiome der funktionalen Programmierung, z. B. die Notwendigkeit der Verwendung der Rekursion, wenn eine einfache Schleife dasselbe Ziel erreichen würde.  
  
## <a name="standard-query-operators"></a>Standardabfrageoperatoren  
 Ein wichtiges Merkmal der Standardabfrageoperatoren besteht darin, dass sie als reine Funktionen implementiert sind.  
  
 Weitere Informationen finden Sie unter [Übersicht über Standardabfrageoperatoren (C#)](./standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Introduction to Pure Functional Transformations (C#) (Einführung in reine funktionale Transformationen (c#))](./introduction-to-pure-functional-transformations.md)
- [Funktionale Programmierung und Imperative Programmierung (C#)](./functional-programming-vs-imperative-programming.md)

---
title: Framework-Typen, die Ausdrucksbaumstrukturen unterstützen
description: Erfahren Sie mehr zu Frameworktypen, die Ausdrucksbaumstrukturen unterstützen, wie Sie diese erstellen können und Methoden zum Arbeiten mit Ausdrucksbaumstruktur-APIs.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.openlocfilehash: 8483c46dde3ea97138e55ab84a5924a3d2578730
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146085"
---
# <a name="framework-types-supporting-expression-trees"></a>Framework-Typen, die Ausdrucksbaumstrukturen unterstützen

[Vorherige – Ausdrucksbaumstrukturen mit Erläuterung](expression-trees-explained.md)

Es gibt eine umfangreiche Liste von Klassen im .NET Core Framework, die mit Ausdrucksbaumstrukturen arbeiten.
Die vollständige Liste finden Sie unter <xref:System.Linq.Expressions>.
Anstatt die vollständige Liste zu durchlaufen, sehen wir uns an, wie die Framework-Klassen entwickelt wurden.

Im Sprachentwurf ist ein Ausdruck ein Teil eines Codes, der ausgewertet wird und einen Wert zurückgibt. Ausdrücke können sehr einfach sein: Der konstante Ausdruck `1` gibt den konstanten Wert 1 zurück. Sie sind möglicherweise komplizierter: Der Ausdruck `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` gibt ein Stammverzeichnis für eine quadratische Gleichung zurück (in dem Fall, in dem die Gleichung eine Lösung hat).  

## <a name="it-all-starts-with-systemlinqexpression"></a>Es beginnt alles mit System.Linq.Expression

Eine der Komplexitäten der Arbeit mit Ausdrucksbaumstrukturen ist, dass viele verschiedene Arten von Ausdrücken an vielen Stellen in Programmen gültig sind. Betrachten Sie einen Zuweisungsausdruck. Die rechte Seite einer Zuweisung kann ein konstanter Wert, eine Variable, ein Methodenaufrufausdruck oder anderes sein. Die Sprachflexibilität bedeutet, dass Sie viele unterschiedliche Ausdruckstypen an beliebigen Stellen in den Knoten einer Struktur erhalten können, wenn Sie eine Ausdrucksbaumstruktur durchlaufen. Wenn Sie mit dem Typ des Ausdrucks arbeiten können, ist dies daher der einfachste Weg zum Arbeiten. Allerdings müssen Sie manchmal mehr wissen.
Die Basisausdrucksklasse enthält eine `NodeType`-Eigenschaft für diesen Zweck.
Es gibt einen `ExpressionType` zurück, der eine Enumeration möglicher Ausdruckstypen ist.
Wenn Sie den Typ des Knotens kennen, können Sie es in diesen Typ umwandeln, und bestimmte Aktionen, die den Typ des Ausdrucksknotens kennen, durchführen. Sie können nach bestimmten Knoten suchen, und anschließend mit den bestimmten Eigenschaften dieser Art von Ausdruck arbeiten.

Dieser Code wird z.B. den Namen einer Variablen für einen Variablenzugriff des Ausdrucks ausgeben. Ich habe den Knotentyp überprüft, ihn anschließend in einen Variablenzugriff des Ausdrucks umgewandelt und die Eigenschaften des bestimmten Ausdruckstyps überprüft:

```csharp
Expression<Func<int, int>> addFive = (num) => num + 5;

if (addFive.NodeType == ExpressionType.Lambda)
{
    var lambdaExp = (LambdaExpression)addFive;

    var parameter = lambdaExp.Parameters.First();

    Console.WriteLine(parameter.Name);
    Console.WriteLine(parameter.Type);
}
```

## <a name="creating-expression-trees"></a>Erstellen von Ausdrucksbaumstrukturen

Die `System.Linq.Expression`-Klasse enthält außerdem viele statische Methoden zum Erstellen von Ausdrücken. Diese Methoden erstellen mithilfe der Argumente für seine untergeordneten Elemente einen Ausdrucksknoten. Auf diese Weise erstellen Sie einen Ausdruck über seine Endknoten. Dieser Code erstellt z.B. einen Add-Ausdruck:

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

Sie können in diesem einfachen Beispiel erkennen, dass viele Typen bei der Erstellung und beim Arbeiten mit Ausdrucksbaumstrukturen beteiligt sind. Diese Komplexität ist erforderlich, um die Funktionalität des rich-Vokabulars der C#-Sprache bereitzustellen.

## <a name="navigating-the-apis"></a>Navigieren in den APIs
Es gibt Ausdrucksknotentypen, die fast alle Elemente der Syntax der C#-Sprache zuordnen. Jeder Typ verfügt über spezielle Methoden für diese Art von Sprachelement. Es ist viel, was Sie sich gleichzeitig merken müssen. Anstatt sich alles zu merken, finden Sie hier die Techniken, die ich zum Arbeiten mit Ausdrucksbaumstrukturen verwende:

1. Betrachten Sie die Member des `ExpressionType`-enum, um mögliche Knoten zu bestimmen, die Sie untersuchen sollten. Dies ist wirklich hilfreich, wenn Sie eine Ausdrucksbaumstruktur durchlaufen und verstehen möchten.
2. Betrachten Sie die statischen Member der `Expression`-Klasse, um einen Ausdruck zu erstellen. Diese Methoden können jeden Ausdruckstyp aus einer Reihe von untergeordneten Knoten erstellen.
3. Sehen Sie sich die `ExpressionVisitor`-Klasse an, um eine geänderte Ausdrucksbaumstruktur zu erstellen.

Sie werden mehr finden, wenn Sie sich jeden dieser drei Bereiche ansehen. Unweigerlich, werden Sie feststellen, was Sie benötigen, wenn Sie mit einem dieser drei Schritte starten.

 [Weiter -- Ausführen von Ausdrucksbaumstrukturen](expression-trees-execution.md)

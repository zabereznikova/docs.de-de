---
title: Erstellen von Ausdrucksbaumstrukturen
description: Informationen zu den Verfahren zum Erstellen von Ausdrucksbaumstrukturen.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 542754a9-7f40-4293-b299-b9f80241902c
ms.openlocfilehash: 45628b00633c8d6ff51dbd5f5dbdda7ca25dd7c4
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037093"
---
# <a name="building-expression-trees"></a>Erstellen von Ausdrucksbaumstrukturen

[Vorheriges - Interpretieren von Ausdrücken](expression-trees-interpreting.md)

Alle Ausdrucksbaumstrukturen, die Sie bisher gesehen haben, wurden vom C#-Compiler erstellt. Sie müssen einfach einen Lambdaausdruck erstellen, der einer typisierten Variable als `Expression<Func<T>>` oder als einen ähnlichen Typ zugewiesen wurde. Das ist nicht die einzige Möglichkeit, eine Ausdrucksbaumstruktur zu erstellen. Für viele Szenarios stellen Sie möglicherweise fest, dass Sie einen Ausdruck im Arbeitsspeicher zur Laufzeit erstellen müssen. 

Das Erstellen von Ausdrucksbaumstrukturen ist kompliziert, da diese Ausdrucksbaumstrukturen unveränderlich sind. Unveränderlich bedeutet, dass Sie die Struktur von den Blättern bis zum Stamm erstellen müssen. Die APIs, die Sie zum Erstellen von Ausdrucksbaumstrukturen verwenden, spiegeln diese Tatsache wider: Die Methoden, die Sie verwenden, um einen Knoten zu erstellen, nehmen alle untergeordneten Elemente als Argumente. Betrachten wir einige Beispiele, die Ihnen die Techniken zeigen.

## <a name="creating-nodes"></a>Erstellen von Knoten

Beginnen wir erneut relativ einfach. Wir verwenden den Additionsausdruck, mit dem ich in diesen Abschnitten arbeiten werde:

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

Um diese Ausdrucksbaumstruktur zu erstellen, müssen Sie die Endknoten erstellen.
Die Endknoten sind Konstanten, damit Sie die `Expression.Constant`-Methode verwenden können, um die Knoten zu erstellen:

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
```

Als Nächstes erstellen Sie den Additionsausdruck:

```csharp
var addition = Expression.Add(one, two);
```

Sobald Sie den Additionsausdruck haben, können Sie den Lambdaausdruck erstellen:

```csharp
var lambda = Expression.Lambda(addition);
```

Dies ist ein sehr einfacher Lambdaausdruck, da er keine Argumente enthält.
In diesem Abschnitt erfahren Sie später, wie Sie Parametern Argumente zuordnen und kompliziertere Ausdrücke erstellen.

Für Ausdrücke, die so einfach wie dieser sind, können Sie alle Aufrufe in einer einzelnen Anweisung kombinieren:

```csharp
var lambda = Expression.Lambda(
    Expression.Add(
        Expression.Constant(1, typeof(int)),
        Expression.Constant(2, typeof(int))
    )
);
```

## <a name="building-a-tree"></a>Erstellen einer Struktur

Das sind die Grundlagen der Erstellung einer Ausdrucksbaumstruktur im Arbeitsspeicher. Komplexere Strukturen bedeuten im Allgemeinen mehr Knotentypen und weitere Knoten in der Struktur. Lassen Sie uns ein weiteres Beispiel ausführen, und zwei weitere Knotentypen, die Sie in der Regel beim Erstellen von Ausdrucksbaumstrukturen erstellen, anzeigen: Die Argumentknoten und Methodenaufrufknoten.

Wir erstellen eine Ausdrucksbaumstruktur, um diesen Ausdruck zu erstellen:

```csharp
Expression<Func<double, double, double>> distanceCalc =
    (x, y) => Math.Sqrt(x * x + y * y);
```
 
Sie beginnen mit dem Erstellen der Parameterausdrücke für `x` und `y`:

```csharp
var xParameter = Expression.Parameter(typeof(double), "x");
var yParameter = Expression.Parameter(typeof(double), "y");
```

Das Erstellen der Multiplikations- und Additionsausdrücke folgt dem Muster, das Sie bereits gesehen haben:

```csharp
var xSquared = Expression.Multiply(xParameter, xParameter);
var ySquared = Expression.Multiply(yParameter, yParameter);
var sum = Expression.Add(xSquared, ySquared);
```

Anschließend müssen Sie einen Ausdruck des Methodenaufrufs für den Aufruf von `Math.Sqrt` erstellen.

```csharp
var sqrtMethod = typeof(Math).GetMethod("Sqrt", new[] { typeof(double) });
var distance = Expression.Call(sqrtMethod, sum);
```

Und anschließend legen Sie den Methodenaufruf in einen Lambdaausdruck, und stellen sicher, dass Sie die Argumente für den Lambdaausdruck definieren:

```csharp
var distanceLambda = Expression.Lambda(
    distance,
    xParameter,
    yParameter);
```

In diesem komplizierteren Beispiel sehen Sie ein paar weitere Verfahren, die Sie häufig benötigen, um Ausdrucksbaumstrukturen zu erstellen.

Zunächst müssen Sie die Objekte erstellen, die Parameter oder lokale Variablen darstellen, bevor Sie sie verwenden. Wenn Sie diese Objekte erstellt haben, können Sie diese in Ihrer Ausdrucksbaumstruktur verwenden, wo immer Sie sie benötigen.

Zweitens müssen Sie einen Teil der Reflektions-APIs verwenden, um ein `MethodInfo`-Objekt zu erstellen, sodass Sie eine Ausdrucksbaumstruktur für den Zugriff auf diese Methode erstellen können. Sie müssen sich auf die Teilmenge der Reflektions-APIs begrenzen, die auf der .NET Core-Plattform verfügbar sind. In diesem Fall werden diese Techniken auf andere Ausdrucksbaumstrukturen erweitert.

## <a name="building-code-in-depth"></a>Erstellen von Code im Detail

Sie sind nicht darin beschränkt, was Sie mithilfe dieser APIs erstellen können. Je komplizierter jedoch die Ausdrucksbaumstruktur ist, die Sie erstellen möchten, desto schwieriger ist der Code zu verwalten und zu lesen. 

Wir erstellen eine Ausdrucksbaumstruktur, die diesem Code entspricht:

```csharp
Func<int, int> factorialFunc = (n) =>
{
    var res = 1;
    while (n > 1)
    {
        res = res * n;
        n--;
    }
    return res;
};
```

Beachten Sie oben, dass ich nicht die Ausdrucksbaumstruktur, aber einfach den Delegaten erstellt habe. Mithilfe der `Expression`-Klasse können Sie keine Anweisungslambdas erstellen. Hier ist der Code, der erforderlich ist, um die gleiche Funktionalität zu erstellen. Es ist etwas kompliziert, dass es keine API zum Erstellen einer `while`-Schleife gibt. Stattdessen müssen Sie eine Schleife, die einen bedingten Test enthält, und ein Bezeichnungsziel erstellen, um die Schleife zu unterbrechen. 

```csharp
var nArgument = Expression.Parameter(typeof(int), "n");
var result = Expression.Variable(typeof(int), "result");

// Creating a label that represents the return value
LabelTarget label = Expression.Label(typeof(int));

var initializeResult = Expression.Assign(result, Expression.Constant(1));

// This is the inner block that performs the multiplication,
// and decrements the value of 'n'
var block = Expression.Block(
    Expression.Assign(result,
        Expression.Multiply(result, nArgument)),
    Expression.PostDecrementAssign(nArgument)
);

// Creating a method body.
BlockExpression body = Expression.Block(
    new[] { result },
    initializeResult,
    Expression.Loop(
        Expression.IfThenElse(
            Expression.GreaterThan(nArgument, Expression.Constant(1)),
            block,
            Expression.Break(label, result)
        ),
        label
    )
);
```

Der Code zum Erstellen der Baumstruktur für die Fakultätsfunktion ist etwas länger, komplizierter, und er ist voll von Bezeichnungen und Break-Anweisungen und anderen Elemente, die wir in unseren täglichen Codieraufgaben vermeiden möchten. 

Für diesen Abschnitt habe ich auch den Besuchercode aktualisiert, um jeden Knoten in dieser Ausdrucksbaumstruktur zu finden, und Informationen zu den Knoten, die in diesem Beispiel erstellt wurden, zu schreiben. Sie können den Beispielcode vom Repository „dotnet/docs“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/csharp/expression-trees). Experimentieren Sie selbst, indem Sie die Beispiele erstellen und ausführen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="examining-the-apis"></a>Untersuchen der APIs

Die Ausdrucksbaumstruktur-APIs sind einige der Schwierigeren zum Navigieren in .NET Core, aber das ist in Ordnung. Ihr Zweck ist ein recht komplexes Unterfangen: Schreiben von Code, der Code zur Laufzeit generiert. Sie sind notwendigerweise kompliziert, um ein Gleichgewicht zwischen der Unterstützung aller verfügbaren Steuerungsstrukturen in der C#-Sprache bereitzustellen und um die Oberfläche der APIs so klein wie angemessenen zu halten. Diese Balance bedeutet, dass viele Steuerungsstrukturen nicht über die C#-Konstrukte dargestellt werden, jedoch über Konstrukte, die die zugrunde liegende Logik darstellen, die der Compiler von diesen Konstrukten mit höherer Ebene generiert. 

Außerdem sind zu diesem Zeitpunkt C#-Ausdrücke vorhanden, die nicht direkt mit `Expression`-Klassenmethoden erstellt werden können. Im Allgemeinen werden dies die neuesten Operatoren und Ausdrücke sein, die in C# 5 und C# 6 hinzugefügt werden. (Z.B. `async`-Ausdrücke können nicht erstellt werden, und der neue `?.`-Operator kann nicht direkt erstellt werden.)

[Weiter– Übersetzen von Ausdrücken](expression-trees-translating.md)

---
title: Übersetzen von Ausdrucksbaumstrukturen
description: Hier erfahren Sie, wie Sie auf jeden Knoten in einer Ausdrucksbaumstruktur zugreifen, während eine geänderte Kopie dieser Ausdrucksbaumstruktur erstellt wird.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.openlocfilehash: cb64e79d915a5c5567d5a3d25f1d747df9687c87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537462"
---
# <a name="translate-expression-trees"></a>Übersetzen von Ausdrucksbaumstrukturen

[Vorheriges – Erstellen von Ausdrücken](expression-trees-building.md)

In diesem letzten Abschnitt erfahren Sie, wie Sie auf jeden Knoten in einer Ausdrucksbaumstruktur zugreifen, während eine geänderte Kopie dieser Ausdrucksbaumstruktur erstellt wird. Dies sind die Techniken, die Sie in zwei wichtigen Szenarios verwenden werden. Die erste besteht darin, die Algorithmen zu verstehen, die durch eine Ausdrucksbaumstruktur ausgedrückt werden, sodass sie in eine andere Umgebung übersetzt werden können. Die zweite ist, wenn Sie den erstellten Algorithmus ändern möchten. Dies könnte zum Beispiel dazu dienen, Protokollierung hinzuzufügen oder Methodenaufrufe abzufangen und zu verfolgen.

## <a name="translating-is-visiting"></a>Übersetzen bedeutet Zugreifen

Der Code, den Sie erstellen, um eine Ausdrucksbaumstruktur zu übersetzen, ist eine Erweiterung von dem, was Sie bereits gesehen haben, um auf alle Knoten in einer Struktur zuzugreifen. Wenn Sie eine Ausdrucksbaumstruktur übersetzen, greifen Sie auf alle Knoten zu, und erstellen während des Zugriffs auf diese die neue Struktur. Die neue Struktur enthält Verweise auf den ursprünglichen Knoten oder neue Knoten, die Sie in der Struktur platziert haben.

Betrachten wir dies in Aktion durch Zugriff auf eine Ausdrucksbaumstruktur und Erstellen einer neuen Struktur mit einigen Knoten zum Ersetzen. Ersetzen wir in diesem Beispiel jede Konstante durch eine Konstante, die zehnmal so groß ist.
Ansonsten werden wir die Ausdrucksbaumstruktur intakt lassen. Anstatt den Wert der Konstante zu lesen und sie durch eine neue Konstante zu ersetzen, führen wir diese Ersetzung durch Ersetzen des konstanten Knotens durch einen neuen Knoten durch, der die Multiplikation ausführt.

Hier erstellen Sie, sobald Sie einen konstanten Knoten gefunden haben, einen neuen Multiplikationsknoten, dessen untergeordnete Elemente die ursprünglichen Konstanten sind, und die Konstante `10`:

```csharp
private static Expression ReplaceNodes(Expression original)
{
    if (original.NodeType == ExpressionType.Constant)
    {
        return Expression.Multiply(original, Expression.Constant(10));
    }
    else if (original.NodeType == ExpressionType.Add)
    {
        var binaryExpression = (BinaryExpression)original;
        return Expression.Add(
            ReplaceNodes(binaryExpression.Left),
            ReplaceNodes(binaryExpression.Right));
    }
    return original;
}
```

Durch Ersetzen des ursprünglichen Knotens durch den Ersatz wird eine neue Struktur gebildet, die unsere Änderungen enthält. Wir können dies durch Kompilieren und Ausführen der ersetzten Struktur überprüfen.

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
var sum = ReplaceNodes(addition);
var executableFunc = Expression.Lambda(sum);

var func = (Func<int>)executableFunc.Compile();
var answer = func();
Console.WriteLine(answer);
```

Das Erstellen einer neuen Struktur ist eine Kombination aus dem Zugriff auf die Knoten in der vorhandenen Struktur und dem Erstellen und Einfügen neuer Knoten in die Struktur.

Dieses Beispiel zeigt, wie wichtig es ist, dass Ausdrucksbaumstrukturen unveränderlich sind. Beachten Sie, dass die weiter oben erstellte neue Struktur eine Mischung aus neu erstellten Knoten und Knoten aus der vorhandenen Struktur enthält. Dies ist sicher, da die Knoten in der vorhandenen Struktur nicht geändert werden können. Dies kann zu beträchtlicher Effizienz beim Speicherplatz führen.
Die gleichen Knoten können in der gesamten Struktur oder in mehreren Ausdrucksbaumstrukturen verwendet werden. Da Knoten nicht geändert werden können, kann der gleiche Knoten wiederverwendet werden, wenn er benötigt wird.

## <a name="traversing-and-executing-an-addition"></a>Durchlaufen und Ausführen einer Addition

Lassen Sie uns dies überprüfen, indem Sie einen zweiten Besucher erstellen, der die Struktur der Additionsknoten durchläuft und das Ergebnis berechnet. Hierzu können Sie einige Änderungen an dem Besucher vornehmen, den Sie bisher gesehen haben. In dieser neuen Version wird der Besucher die partielle Summe des Additionsvorgangs bis zu diesem Punkt zurückgeben. Für einen konstanten Ausdruck ist dies einfach der Wert des konstanten Ausdrucks. Für einen Additionsausdruck ist das Ergebnis die Summe der linken und rechten Operanden, sobald diese Strukturen durchlaufen wurden.

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var three= Expression.Constant(3, typeof(int));
var four = Expression.Constant(4, typeof(int));
var addition = Expression.Add(one, two);
var add2 = Expression.Add(three, four);
var sum = Expression.Add(addition, add2);

// Declare the delegate, so we can call it
// from itself recursively:
Func<Expression, int> aggregate = null;
// Aggregate, return constants, or the sum of the left and right operand.
// Major simplification: Assume every binary expression is an addition.
aggregate = (exp) =>
    exp.NodeType == ExpressionType.Constant ?
    (int)((ConstantExpression)exp).Value :
    aggregate(((BinaryExpression)exp).Left) + aggregate(((BinaryExpression)exp).Right);

var theSum = aggregate(sum);
Console.WriteLine(theSum);
```

Es ist einiges an Code, aber die Konzepte sind sehr zugänglich.
Dieser Code besucht untergeordnete Elemente in einer ersten tiefgründigen Suche. Wenn er einen konstanten Knoten erkennt, gibt der Besucher den Wert der Konstanten zurück. Nachdem der Besucher auf beide untergeordnete Elemente zugegriffen hat, werden diese untergeordneten Elemente die Summe für die Unterstruktur berechnet haben. Der Additionsknoten kann jetzt seine Summe berechnen.
Sobald alle Knoten in der Ausdrucksbaumstruktur aufgerufen wurden, wird die Summe berechnet worden sein. Sie können die Ausführung verfolgen, indem Sie das Beispiel im Debugger ausführen und die Ausführung verfolgen.

Wir erleichtern die Verfolgung, wie die Knoten analysiert werden und wie die Summe berechnet wird, indem wir die Struktur durchlaufen. Hier ist eine aktualisierte Version der Aggregatmethode, die ziemlich viel Ablaufverfolgungsinformationen enthält:

```csharp
private static int Aggregate(Expression exp)
{
    if (exp.NodeType == ExpressionType.Constant)
    {
        var constantExp = (ConstantExpression)exp;
        Console.Error.WriteLine($"Found Constant: {constantExp.Value}");
        return (int)constantExp.Value;
    }
    else if (exp.NodeType == ExpressionType.Add)
    {
        var addExp = (BinaryExpression)exp;
        Console.Error.WriteLine("Found Addition Expression");
        Console.Error.WriteLine("Computing Left node");
        var leftOperand = Aggregate(addExp.Left);
        Console.Error.WriteLine($"Left is: {leftOperand}");
        Console.Error.WriteLine("Computing Right node");
        var rightOperand = Aggregate(addExp.Right);
        Console.Error.WriteLine($"Right is: {rightOperand}");
        var sum = leftOperand + rightOperand;
        Console.Error.WriteLine($"Computed sum: {sum}");
        return sum;
    }
    else throw new NotSupportedException("Haven't written this yet");
}
```

Es auf demselben Ausdruck auszuführen, ergibt die folgende Ausgabe:

```output
10
Found Addition Expression
Computing Left node
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Constant: 2
Right is: 2
Computed sum: 3
Left is: 3
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 10
10
```

Verfolgen Sie die Ausgabe und folgen Sie dem obigen Code. Sie sollten in der Lage sein zu ermitteln, wie der Code auf jeden Knoten zugreift und die Summe berechnet, während er die Struktur durchläuft und die Summe ermittelt.

Jetzt sehen wir uns eine andere Ausführung mit dem von `sum1` zur Verfügung gestellten Ausdruck an:

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

Hier ist die Ausgabe von der Untersuchung dieses Ausdrucks:

```output
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 2
Left is: 2
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 9
Right is: 9
Computed sum: 10
10
```

Während die endgültige Antwort identisch ist, ist das Durchlaufen der Struktur unterschiedlich. Die Knoten werden in einer anderen Reihenfolge zurückgelegt, da die Struktur mit verschiedenen Vorgängen zuerst erstellt wurde.

## <a name="learning-more"></a>Weitere Informationen

Dieses Beispiel zeigt eine kleine Teilmenge des Codes, den Sie erstellen möchten, um die durch eine Ausdrucksbaumstruktur dargestellten Algorithmen zu durchlaufen und zu interpretieren. Für eine vollständige Beschreibung aller notwendigen Arbeiten zur Erstellung einer allgemeinen Bibliothek, die Ausdrucksbaumstrukturen in eine andere Sprache übersetzt, lesen Sie [diese Serie](/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) von Matt Warren. Es wird bis ins Detail erklärt, wie jeder Code übersetzt wird, den Sie in einer Ausdrucksbaumstruktur finden könnten.

Ich hoffe, dass Sie jetzt die tatsächliche Leistungsfähigkeit von Ausdrucksbaumstrukturen gesehen haben.
Sie können einen Satz von Code untersuchen, alle Änderungen vornehmen, die Sie für diesen Code haben möchten, und die geänderte Version ausführen. Da die Ausdrucksbaumstrukturen unveränderlich sind, können Sie neue Strukturen mithilfe der Komponenten von vorhandenen Strukturen erstellen. Dies minimiert die Menge an erforderlichem Arbeitsspeicher, um geänderte Ausdrucksbaumstrukturen zu erstellen.

[Weiter – Schlussbemerkung](expression-trees-summary.md)

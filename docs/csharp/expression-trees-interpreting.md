---
title: Interpretieren von Ausdrücken
description: Weitere Informationen zum Schreiben von Code, um die Struktur einer Ausdrucksbaumstruktur zu untersuchen.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: 34434a633d866b82da3da713aaecc218c7d35124
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036896"
---
# <a name="interpreting-expressions"></a>Interpretieren von Ausdrücken

[Vorheriges – Ausführen von Ausdrücken](expression-trees-execution.md)

Lassen Sie uns nun Code schreiben, um die Struktur einer *Ausdrucksbaumstruktur* zu untersuchen. Jeder Knoten in einer Ausdrucksbaumstruktur ist ein Objekt einer Klasse, die von `Expression` abgeleitet ist.

Dieser Entwurf macht den Zugriff auf alle Knoten in einer Ausdrucksbaumstruktur zu einem relativ unkomplizierten rekursiven Vorgang. Die allgemeine Strategie besteht darin, im Stammknoten zu starten und zu bestimmen, welche Art von Knoten es ist.

Wenn der Knotentyp untergeordnete Elemente besitzt, greifen Sie rekursiv auf die untergeordneten Elemente zu. Wiederholen Sie den beim Stammknoten verwendeten Prozess bei jedem untergeordneten Knoten: Bestimmen Sie den Typ, und wenn er untergeordnete Elemente aufweist, greifen Sie auf jedes der untergeordneten Elemente zu.

## <a name="examining-an-expression-with-no-children"></a>Untersuchen eines Ausdrucks ohne untergeordnete Elemente
Beginnen wir damit, auf jeden Knoten in einer einfachen Ausdrucksbaumstruktur zuzugreifen.
Hier ist der Code, der einen konstanten Ausdruck erstellt und anschließend seine Eigenschaften überprüft:

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

Dadurch wird Folgendes zurückgegeben:

```output
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

Jetzt schreiben wir den Code, der diesen Ausdruck untersuchen und einige wichtige Eigenschaften darüber schreiben würde. Hier ist dieser Code:

## <a name="examining-a-simple-addition-expression"></a>Untersuchen eines einfachen Additionsausdrucks

Beginnen wir mit dem Hinzufügen-Beispiel aus der Einführung zu diesem Abschnitt.

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> Ich verwende kein `var`, um diese Ausdrucksbaumstruktur zu deklarieren, da es nicht möglich ist, weil die rechte Seite der Zuweisung implizit typisiert ist. Um dies besser zu verstehen, lesen Sie [hier](implicitly-typed-lambda-expressions.md).

Der Stammknoten ist ein `LambdaExpression`. Um interessanten Code auf der rechten Seite des `=>`-Operators zu erhalten, müssen Sie eines der untergeordneten Elemente des `LambdaExpression` finden. Wir werden dies mit allen Ausdrücken in diesem Abschnitt durchführen. Der übergeordnete Knoten hilft uns beim Finden des Rückgabetyps des `LambdaExpression`.

Wir müssen rekursiv auf eine Anzahl von Knoten zugreifen, um jeden Knoten in diesem Ausdruck zu untersuchen. Hier ist eine einfache erste Implementierung:

```csharp
Expression<Func<int, int, int>> addition = (a, b) => a + b;

Console.WriteLine($"This expression is a {addition.NodeType} expression type");
Console.WriteLine($"The name of the lambda is {((addition.Name == null) ? "<null>" : addition.Name)}");
Console.WriteLine($"The return type is {addition.ReturnType.ToString()}");
Console.WriteLine($"The expression has {addition.Parameters.Count} arguments. They are:");
foreach(var argumentExpression in addition.Parameters)
{
    Console.WriteLine($"\tParameter Type: {argumentExpression.Type.ToString()}, Name: {argumentExpression.Name}");
}

var additionBody = (BinaryExpression)addition.Body;
Console.WriteLine($"The body is a {additionBody.NodeType} expression");
Console.WriteLine($"The left side is a {additionBody.Left.NodeType} expression");
var left = (ParameterExpression)additionBody.Left;
Console.WriteLine($"\tParameter Type: {left.Type.ToString()}, Name: {left.Name}");
Console.WriteLine($"The right side is a {additionBody.Right.NodeType} expression");
var right= (ParameterExpression)additionBody.Right;
Console.WriteLine($"\tParameter Type: {right.Type.ToString()}, Name: {right.Name}");
```

Dieses Beispiel gibt die folgende Ausgabe zurück:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 arguments. They are:
        Parameter Type: System.Int32, Name: a
        Parameter Type: System.Int32, Name: b
The body is a/an Add expression
The left side is a Parameter expression
        Parameter Type: System.Int32, Name: a
The right side is a Parameter expression
        Parameter Type: System.Int32, Name: b
```

Sie werden viele Wiederholungen im obigen Codebeispiel sehen.
Lassen Sie uns dies bereinigen und einen Ausdrucksknoten für Besucher für eine allgemeinere Verwendung erstellen. Dafür müssen wir einen rekursiven Algorithmus schreiben. Jeder Knoten kann ein Typ sein, der möglicherweise untergeordnete Elemente aufweist.
Jeder Knoten mit untergeordneten Elementen erfordert es, dass Sie auf diese untergeordneten Elemente zugreifen und bestimmen, was dieser Knoten ist. Hier finden Sie die bereinigte Version, die Rekursion verwendet, um auf die Additionsvorgänge zuzugreifen:

```csharp
// Base Visitor class:
public abstract class Visitor
{
    private readonly Expression node;

    protected Visitor(Expression node)
    {
        this.node = node;
    }

    public abstract void Visit(string prefix);

    public ExpressionType NodeType => this.node.NodeType;
    public static Visitor CreateFromExpression(Expression node)
    {
        switch(node.NodeType)
        {
            case ExpressionType.Constant:
                return new ConstantVisitor((ConstantExpression)node);
            case ExpressionType.Lambda:
                return new LambdaVisitor((LambdaExpression)node);
            case ExpressionType.Parameter:
                return new ParameterVisitor((ParameterExpression)node);
            case ExpressionType.Add:
                return new BinaryVisitor((BinaryExpression)node);
            default:
                Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
                return default(Visitor);
        }
    }
}

// Lambda Visitor
public class LambdaVisitor : Visitor
{
    private readonly LambdaExpression node;
    public LambdaVisitor(LambdaExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression type");
        Console.WriteLine($"{prefix}The name of the lambda is {((node.Name == null) ? "<null>" : node.Name)}");
        Console.WriteLine($"{prefix}The return type is {node.ReturnType.ToString()}");
        Console.WriteLine($"{prefix}The expression has {node.Parameters.Count} argument(s). They are:");
        // Visit each parameter:
        foreach (var argumentExpression in node.Parameters)
        {
            var argumentVisitor = Visitor.CreateFromExpression(argumentExpression);
            argumentVisitor.Visit(prefix + "\t");
        }
        Console.WriteLine($"{prefix}The expression body is:");
        // Visit the body:
        var bodyVisitor = Visitor.CreateFromExpression(node.Body);
        bodyVisitor.Visit(prefix + "\t");
    }
}

// Binary Expression Visitor:
public class BinaryVisitor : Visitor
{
    private readonly BinaryExpression node;
    public BinaryVisitor(BinaryExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This binary expression is a {NodeType} expression");
        var left = Visitor.CreateFromExpression(node.Left);
        Console.WriteLine($"{prefix}The Left argument is:");
        left.Visit(prefix + "\t");
        var right = Visitor.CreateFromExpression(node.Right);
        Console.WriteLine($"{prefix}The Right argument is:");
        right.Visit(prefix + "\t");
    }
}

// Parameter visitor:
public class ParameterVisitor : Visitor
{
    private readonly ParameterExpression node;
    public ParameterVisitor(ParameterExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}Type: {node.Type.ToString()}, Name: {node.Name}, ByRef: {node.IsByRef}");
    }
}

// Constant visitor:
public class ConstantVisitor : Visitor
{
    private readonly ConstantExpression node;
    public ConstantVisitor(ConstantExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}The type of the constant value is {node.Type}");
        Console.WriteLine($"{prefix}The value of the constant value is {node.Value}");
    }
}
```

Dieser Algorithmus ist die Grundlage für einen Algorithmus, der jeden beliebigen `LambdaExpression` besuchen kann. Es gibt viele Löcher, da der Code, den ich erstellt habe, nur nach einem kleinen Teil der möglichen Sätze von Knoten in der Ausdrucksbaumstruktur sucht, die auftreten können. Allerdings können Sie dennoch etwas von dem lernen, was er produziert. (Der Standardfall in der `Visitor.CreateFromExpression`-Methode gibt eine Meldung an die Fehlerkonsole, wenn ein neuer Knotentyp gefunden wird. Auf diese Weise wissen Sie, dass Sie einen neuen Ausdruck hinzufügen können.)

Beim Ausführen dieser Besucher auf dem oben gezeigten Additionsausdruck erhalten Sie die folgende Ausgabe:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: b, ByRef: False
```

Nun, da Sie eine allgemeinere Besucherimplementierung erstellt haben, können Sie auf mehr verschiedene Ausdruckstypen zugreifen und diese verarbeiten.

## <a name="examining-an-addition-expression-with-many-levels"></a>Untersuchen eines Additionsausdrucks mit vielen Ebenen

Wir versuchen ein etwas komplizierteres Beispiel, aber trotzdem beschränken wir die Knotentypen auf Addition:

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

Bevor Sie dies auf dem Besucheralgorithmus ausführen, versuchen Sie eine Denkübung, um herauszufinden, was die Ausgabe sein könnte. Beachten Sie, dass der `+`-Operator ein *binärer Operator* ist: Er muss über zwei untergeordnete Elemente verfügen, die die linken und rechten Operanden darstellen. Es gibt mehrere Möglichkeiten, eine Struktur zu erstellen, die richtig sein könnte:

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

Sie sehen die Aufteilung in zwei mögliche Antworten, um die vielversprechendste zu markieren. Die erste stellt *rechtsassoziative* Ausdrücke dar. Die zweite stellt *linksassoziative* Ausdrücke dar.
Der Vorteil dieser beiden Formate ist, dass das Format auf jede beliebige Anzahl von Additionsausdrücken skaliert. 

Wenn Sie diesen Ausdruck über die Besucher ausführen, sehen Sie diese Ausgabe, die überprüft, ob der einfache Additionsausdruck *linksassoziativ* ist. 

Um dieses Beispiel auszuführen und die vollständige Ausdrucksbaumstruktur anzuzeigen, musste ich eine Änderung an der Quelle der Ausdrucksbaumstruktur vornehmen. Wenn die Ausdrucksbaumstruktur alle Konstanten enthält, enthält die resultierende Struktur einfach den konstanten Wert von `10`. Der Compiler führt alle Additionen aus und reduziert den Ausdruck auf seine einfachste Form. Das Hinzufügen einer Variablen im Ausdruck ist ausreichend, um die ursprüngliche Struktur anzuzeigen:

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

Erstellen Sie einen Besucher für diese Summe, und führen Sie den Besucher aus, für den Sie diese Ausgabe sehen:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This binary expression is a Add expression
                        The Left argument is:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                        The Right argument is:
                                This is an Parameter expression type
                                Type: System.Int32, Name: a, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
        The Right argument is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 4
```

Sie können auch eines der anderen Beispiele über den Besuchercode ausführen und sehen, welche Struktur es darstellt. Hier ist ein Beispiel für den oben stehenden `sum3`-Ausdruck (mit einem zusätzlichen Parameter, um zu verhindern, dass der Compiler die Konstante berechnet):

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

Dies ist die Ausgabe vom Besucher:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 1
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: b, ByRef: False
```

Beachten Sie, dass die Klammern nicht Teil der Ausgabe sind. Es sind keine Knoten in der Ausdrucksbaumstruktur vorhanden, die die Klammern im eingegebenen Ausdruck darstellen. Die Struktur der Ausdrucksbaumstruktur enthält alle Informationen, die erforderlich sind, um die Rangfolge zu kommunizieren.

## <a name="extending-from-this-sample"></a>Erweiterungen aus diesem Beispiel

Das Beispiel behandelt nur die elementarsten Ausdrucksbaumstrukturen. Der Code, den Sie in diesem Abschnitt gesehen haben, behandelt nur konstante ganze Zahlen und den binären `+`-Operator. Als letztes Beispiel aktualisieren wir den Besucher, um einen komplizierteren Ausdruck zu behandeln. Lassen Sie uns dafür sorgen, dass es hierfür funktioniert:

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ? 
    1 : 
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

Dieser Code stellt eine mögliche Implementierung für die mathematische *Fakultät*-Funktion dar. So wie ich diesen Code geschrieben habe, werden zwei Einschränkungen beim Erstellen von Ausdrucksbaumstrukturen durch die Zuweisung von Lambdaausdrücken an Ausdrücke hervorgehoben. Erstens sind Anweisungslambdas nicht zulässig. Das bedeutet, ich kann keine Schleifen, Blöcke, if/else-Anweisungen und anderen allgemeinen Steuerungsstrukturen in C# verwenden. Ich kann nur Ausdrücke verwenden. Zweitens kann ich nicht denselben Ausdruck rekursiv aufrufen.
Ich könnte dies, wenn er bereits ein Delegat wäre, aber ich kann ihn nicht in seiner Form der Ausdrucksbaumstruktur aufrufen. Im Abschnitt zu [building expression trees (Erstellen von Ausdrucksbaumstrukturen)](expression-trees-building.md) werden Sie Techniken erlernen, um diese Einschränkung zu umgehen.

In diesem Ausdruck können Knoten all dieser Typen auftreten:

1. Gleich (binärer Ausdruck)
2. Multiplizieren (binärer Ausdruck)
3. Bedingt (der ? : Ausdruck)
4. Ausdruck des Methodenaufrufs (Aufrufen von `Range()` und `Aggregate()`)

Eine Möglichkeit zum Ändern des Besucheralgorithmus besteht darin, ihn auszuführen, und den Knotentyp jedes Mal, wenn Sie Ihre `default`-Klausel erreichen, zu schreiben. Nach einigen Iterationen haben Sie alle möglichen Knoten gesehen. Dann haben Sie alles, was Sie benötigen. Das Ergebnis würde in etwa wie folgt aussehen:

```csharp
public static Visitor CreateFromExpression(Expression node)
{
    switch(node.NodeType)
    {
        case ExpressionType.Constant:
            return new ConstantVisitor((ConstantExpression)node);
        case ExpressionType.Lambda:
            return new LambdaVisitor((LambdaExpression)node);
        case ExpressionType.Parameter:
            return new ParameterVisitor((ParameterExpression)node);
        case ExpressionType.Add:
        case ExpressionType.Equal:
        case ExpressionType.Multiply:
            return new BinaryVisitor((BinaryExpression)node);
        case ExpressionType.Conditional:
            return new ConditionalVisitor((ConditionalExpression)node);
        case ExpressionType.Call:
            return new MethodCallVisitor((MethodCallExpression)node);
        default:
            Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
            return default(Visitor);
    }
}
```

ConditionalVisitor und MethodCallVisitor verarbeiten diese zwei Knoten:

```csharp
public class ConditionalVisitor : Visitor
{
    private readonly ConditionalExpression node;
    public ConditionalVisitor(ConditionalExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        var testVisitor = Visitor.CreateFromExpression(node.Test);
        Console.WriteLine($"{prefix}The Test for this expression is:");
        testVisitor.Visit(prefix + "\t");
        var trueVisitor = Visitor.CreateFromExpression(node.IfTrue);
        Console.WriteLine($"{prefix}The True clause for this expression is:");
        trueVisitor.Visit(prefix + "\t");
        var falseVisitor = Visitor.CreateFromExpression(node.IfFalse);
        Console.WriteLine($"{prefix}The False clause for this expression is:");
        falseVisitor.Visit(prefix + "\t");
    }
}

public class MethodCallVisitor : Visitor
{
    private readonly MethodCallExpression node;
    public MethodCallVisitor(MethodCallExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        if (node.Object == null)
            Console.WriteLine($"{prefix}This is a static method call");
        else
        {
            Console.WriteLine($"{prefix}The receiver (this) is:");
            var receiverVisitor = Visitor.CreateFromExpression(node.Object);
            receiverVisitor.Visit(prefix + "\t");
        }

        var methodInfo = node.Method;
        Console.WriteLine($"{prefix}The method name is {methodInfo.DeclaringType}.{methodInfo.Name}");
        // There is more here, like generic arguments, and so on.
        Console.WriteLine($"{prefix}The Arguments are:");
        foreach(var arg in node.Arguments)
        {
            var argVisitor = Visitor.CreateFromExpression(arg);
            argVisitor.Visit(prefix + "\t");
        }
    }
}
```

Und die Ausgabe für die Ausdrucksbaumstruktur wäre:

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: n, ByRef: False
The expression body is:
        This expression is a Conditional expression
        The Test for this expression is:
                This binary expression is a Equal expression
                The Left argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: n, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 0
        The True clause for this expression is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 1
        The False clause for this expression is:
                This expression is a Call expression
                This is a static method call
                The method name is System.Linq.Enumerable.Aggregate
                The Arguments are:
                        This expression is a Call expression
                        This is a static method call
                        The method name is System.Linq.Enumerable.Range
                        The Arguments are:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                                This is an Parameter expression type
                                Type: System.Int32, Name: n, ByRef: False
                        This expression is a Lambda expression type
                        The name of the lambda is <null>
                        The return type is System.Int32
                        The expression has 2 arguments. They are:
                                This is an Parameter expression type
                                Type: System.Int32, Name: product, ByRef: False
                                This is an Parameter expression type
                                Type: System.Int32, Name: factor, ByRef: False
                        The expression body is:
                                This binary expression is a Multiply expression
                                The Left argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: product, ByRef: False
                                The Right argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: factor, ByRef: False
```

## <a name="extending-the-sample-library"></a>Erweitern Sie die Beispielbibliothek

Die Beispiele in diesem Abschnitt zeigen die Kerntechniken, um Knoten in einer Ausdrucksbaumstruktur zu besuchen und zu untersuchen. Ich habe viele Aktionen ausgelassen, die Sie möglicherweise benötigen, um sich auf die wichtigsten Aufgaben beim Zugriff auf die Knoten in einer Ausdrucksbaumstruktur zu konzentrieren. 

Erstens behandelt der Besucher nur Konstanten, die ganze Zahlen sind. Konstante Werte können jeder andere numerische Typ sein, und die C#-Sprache unterstützt Konvertierungen und Werbeaktionen zwischen diesen Typen. Eine robustere Version dieses Codes würde alle diese Funktionen widerspiegeln.

Sogar das letzte Beispiel erkennt eine Teilmenge der möglichen Knotentypen.
Sie können weiterhin viele Ausdrücke eingeben, die Fehler verursachen werden.
Eine vollständige Implementierung ist in .NET Standard unter dem Namen <xref:System.Linq.Expressions.ExpressionVisitor> enthalten und kann alle möglichen Knotentypen verarbeiten.

Schließlich wurde die Bibliothek, die ich in diesem Artikel verwendet habe, für Demo- und Lernzwecke erstellt. Sie ist nicht optimiert. Ich habe sie geschrieben, um die verwendeten Strukturen klar zu machen und um die verwendeten Techniken für den Zugriff auf die Knoten hervorzuheben und zu analysieren, was sich dort befindet. Eine Produktionsimplementierung würde mehr Aufmerksamkeit auf die Leistung legen, als ich es habe.

Selbst mit diesen Einschränkungen sollten Sie sich auf dem richtigen Weg zum Schreiben von Algorithmen befinden, die Ausdrucksbaumstrukturen lesen und verstehen.

[Weiter – Erstellen von Ausdrücken](expression-trees-building.md)

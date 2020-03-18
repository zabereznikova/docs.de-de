---
title: Übersetzen von Ausdrucksbaumstrukturen
description: Hier erfahren Sie, wie Sie auf jeden Knoten in einer Ausdrucksbaumstruktur zugreifen, während eine geänderte Kopie dieser Ausdrucksbaumstruktur erstellt wird.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.openlocfilehash: f60c447d5c89aa83f85073e642e621608131ed8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76115780"
---
# <a name="translate-expression-trees"></a><span data-ttu-id="0a600-103">Übersetzen von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="0a600-103">Translate expression trees</span></span>

[<span data-ttu-id="0a600-104">Vorheriges – Erstellen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="0a600-104">Previous -- Building Expressions</span></span>](expression-trees-building.md)

<span data-ttu-id="0a600-105">In diesem letzten Abschnitt erfahren Sie, wie Sie auf jeden Knoten in einer Ausdrucksbaumstruktur zugreifen, während eine geänderte Kopie dieser Ausdrucksbaumstruktur erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0a600-105">In this final section, you'll learn how to visit each node in an expression tree while building a modified copy of that expression tree.</span></span> <span data-ttu-id="0a600-106">Dies sind die Techniken, die Sie in zwei wichtigen Szenarios verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="0a600-106">These are the techniques that you will use in two important scenarios.</span></span> <span data-ttu-id="0a600-107">Die erste besteht darin, die Algorithmen zu verstehen, die durch eine Ausdrucksbaumstruktur ausgedrückt werden, sodass sie in eine andere Umgebung übersetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="0a600-107">The first is to understand the algorithms expressed by an expression tree so that it can be translated into another environment.</span></span> <span data-ttu-id="0a600-108">Die zweite ist, wenn Sie den erstellten Algorithmus ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="0a600-108">The second is when you want to change the algorithm that has been created.</span></span> <span data-ttu-id="0a600-109">Dies könnte zum Beispiel dazu dienen, Protokollierung hinzuzufügen oder Methodenaufrufe abzufangen und zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="0a600-109">This might be to add logging, intercept method calls and track them, or other purposes.</span></span>

## <a name="translating-is-visiting"></a><span data-ttu-id="0a600-110">Übersetzen bedeutet Zugreifen</span><span class="sxs-lookup"><span data-stu-id="0a600-110">Translating is Visiting</span></span>

<span data-ttu-id="0a600-111">Der Code, den Sie erstellen, um eine Ausdrucksbaumstruktur zu übersetzen, ist eine Erweiterung von dem, was Sie bereits gesehen haben, um auf alle Knoten in einer Struktur zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0a600-111">The code you build to translate an expression tree is an extension of what you've already seen to visit all the nodes in a tree.</span></span> <span data-ttu-id="0a600-112">Wenn Sie eine Ausdrucksbaumstruktur übersetzen, greifen Sie auf alle Knoten zu, und erstellen während des Zugriffs auf diese die neue Struktur.</span><span class="sxs-lookup"><span data-stu-id="0a600-112">When you translate an expression tree, you visit all the nodes, and while visiting them, build the new tree.</span></span> <span data-ttu-id="0a600-113">Die neue Struktur enthält Verweise auf den ursprünglichen Knoten oder neue Knoten, die Sie in der Struktur platziert haben.</span><span class="sxs-lookup"><span data-stu-id="0a600-113">The new tree may contain references to the original nodes, or new nodes that you have placed in the tree.</span></span>

<span data-ttu-id="0a600-114">Betrachten wir dies in Aktion durch Zugriff auf eine Ausdrucksbaumstruktur und Erstellen einer neuen Struktur mit einigen Knoten zum Ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0a600-114">Let's see this in action by visiting an expression tree, and creating a new tree with some replacement nodes.</span></span> <span data-ttu-id="0a600-115">Ersetzen wir in diesem Beispiel jede Konstante durch eine Konstante, die zehnmal so groß ist.</span><span class="sxs-lookup"><span data-stu-id="0a600-115">In this example, let's replace any constant with a constant that is ten times larger.</span></span>
<span data-ttu-id="0a600-116">Ansonsten werden wir die Ausdrucksbaumstruktur intakt lassen.</span><span class="sxs-lookup"><span data-stu-id="0a600-116">Otherwise, we'll leave the expression tree intact.</span></span> <span data-ttu-id="0a600-117">Anstatt den Wert der Konstante zu lesen und sie durch eine neue Konstante zu ersetzen, führen wir diese Ersetzung durch Ersetzen des konstanten Knotens durch einen neuen Knoten durch, der die Multiplikation ausführt.</span><span class="sxs-lookup"><span data-stu-id="0a600-117">Rather than reading the value of the constant, and replacing it with a new constant, we'll make this replacement by replacing the constant node with a new node that performs the multiplication.</span></span>

<span data-ttu-id="0a600-118">Hier erstellen Sie, sobald Sie einen konstanten Knoten gefunden haben, einen neuen Multiplikationsknoten, dessen untergeordnete Elemente die ursprünglichen Konstanten sind, und die Konstante `10`:</span><span class="sxs-lookup"><span data-stu-id="0a600-118">Here, once you find a constant node, you create a new multiplication node whose children are the original constant, and the constant `10`:</span></span>

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

<span data-ttu-id="0a600-119">Durch Ersetzen des ursprünglichen Knotens durch den Ersatz wird eine neue Struktur gebildet, die unsere Änderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="0a600-119">By replacing the original node with the substitute, a new tree is formed that contains our modifications.</span></span> <span data-ttu-id="0a600-120">Wir können dies durch Kompilieren und Ausführen der ersetzten Struktur überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0a600-120">We can verify that by compiling and executing the replaced tree.</span></span>

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

<span data-ttu-id="0a600-121">Das Erstellen einer neuen Struktur ist eine Kombination aus dem Zugriff auf die Knoten in der vorhandenen Struktur und dem Erstellen und Einfügen neuer Knoten in die Struktur.</span><span class="sxs-lookup"><span data-stu-id="0a600-121">Building a new tree is a combination of visiting the nodes in the existing tree, and creating new nodes and inserting them into the tree.</span></span>

<span data-ttu-id="0a600-122">Dieses Beispiel zeigt, wie wichtig es ist, dass Ausdrucksbaumstrukturen unveränderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0a600-122">This example shows the importance of expression trees being immutable.</span></span> <span data-ttu-id="0a600-123">Beachten Sie, dass die weiter oben erstellte neue Struktur eine Mischung aus neu erstellten Knoten und Knoten aus der vorhandenen Struktur enthält.</span><span class="sxs-lookup"><span data-stu-id="0a600-123">Notice that the new tree created above contains a mixture of newly created nodes, and nodes from the existing tree.</span></span> <span data-ttu-id="0a600-124">Dies ist sicher, da die Knoten in der vorhandenen Struktur nicht geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="0a600-124">That's safe, because the nodes in the existing tree cannot be modified.</span></span> <span data-ttu-id="0a600-125">Dies kann zu beträchtlicher Effizienz beim Speicherplatz führen.</span><span class="sxs-lookup"><span data-stu-id="0a600-125">This can result in significant memory efficiencies.</span></span>
<span data-ttu-id="0a600-126">Die gleichen Knoten können in der gesamten Struktur oder in mehreren Ausdrucksbaumstrukturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a600-126">The same nodes can be used throughout a tree, or in multiple expression trees.</span></span> <span data-ttu-id="0a600-127">Da Knoten nicht geändert werden können, kann der gleiche Knoten wiederverwendet werden, wenn er benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a600-127">Since nodes can't be modified, the same node can be reused whenever it's needed.</span></span>

## <a name="traversing-and-executing-an-addition"></a><span data-ttu-id="0a600-128">Durchlaufen und Ausführen einer Addition</span><span class="sxs-lookup"><span data-stu-id="0a600-128">Traversing and Executing an Addition</span></span>

<span data-ttu-id="0a600-129">Lassen Sie uns dies überprüfen, indem Sie einen zweiten Besucher erstellen, der die Struktur der Additionsknoten durchläuft und das Ergebnis berechnet.</span><span class="sxs-lookup"><span data-stu-id="0a600-129">Let's verify this by building a second visitor that walks the tree of addition nodes and computes the result.</span></span> <span data-ttu-id="0a600-130">Hierzu können Sie einige Änderungen an dem Besucher vornehmen, den Sie bisher gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="0a600-130">You can do this by making a couple modifications to the visitor that you've seen so far.</span></span> <span data-ttu-id="0a600-131">In dieser neuen Version wird der Besucher die partielle Summe des Additionsvorgangs bis zu diesem Punkt zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0a600-131">In this new version, the visitor will return the partial sum of the addition operation up to this point.</span></span> <span data-ttu-id="0a600-132">Für einen konstanten Ausdruck ist dies einfach der Wert des konstanten Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="0a600-132">For a constant expression, that is simply the value of the constant expression.</span></span> <span data-ttu-id="0a600-133">Für einen Additionsausdruck ist das Ergebnis die Summe der linken und rechten Operanden, sobald diese Strukturen durchlaufen wurden.</span><span class="sxs-lookup"><span data-stu-id="0a600-133">For an addition expression, the result is the sum of the left and right operands, once those trees have been traversed.</span></span>

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

<span data-ttu-id="0a600-134">Es ist einiges an Code, aber die Konzepte sind sehr zugänglich.</span><span class="sxs-lookup"><span data-stu-id="0a600-134">There's quite a bit of code here, but the concepts are very approachable.</span></span>
<span data-ttu-id="0a600-135">Dieser Code besucht untergeordnete Elemente in einer ersten tiefgründigen Suche.</span><span class="sxs-lookup"><span data-stu-id="0a600-135">This code visits children in a depth first search.</span></span> <span data-ttu-id="0a600-136">Wenn er einen konstanten Knoten erkennt, gibt der Besucher den Wert der Konstanten zurück.</span><span class="sxs-lookup"><span data-stu-id="0a600-136">When it encounters a constant node, the visitor returns the value of the constant.</span></span> <span data-ttu-id="0a600-137">Nachdem der Besucher auf beide untergeordnete Elemente zugegriffen hat, werden diese untergeordneten Elemente die Summe für die Unterstruktur berechnet haben.</span><span class="sxs-lookup"><span data-stu-id="0a600-137">After the visitor has visited both children, those children will have computed the sum computed for that subtree.</span></span> <span data-ttu-id="0a600-138">Der Additionsknoten kann jetzt seine Summe berechnen.</span><span class="sxs-lookup"><span data-stu-id="0a600-138">The addition node can now compute its sum.</span></span>
<span data-ttu-id="0a600-139">Sobald alle Knoten in der Ausdrucksbaumstruktur aufgerufen wurden, wird die Summe berechnet worden sein.</span><span class="sxs-lookup"><span data-stu-id="0a600-139">Once all the nodes in the expression tree have been visited, the sum will have been computed.</span></span> <span data-ttu-id="0a600-140">Sie können die Ausführung verfolgen, indem Sie das Beispiel im Debugger ausführen und die Ausführung verfolgen.</span><span class="sxs-lookup"><span data-stu-id="0a600-140">You can trace the execution by running the sample in the debugger and tracing the execution.</span></span>

<span data-ttu-id="0a600-141">Wir erleichtern die Verfolgung, wie die Knoten analysiert werden und wie die Summe berechnet wird, indem wir die Struktur durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="0a600-141">Let's make it easier to trace how the nodes are analyzed and how the sum is computed by traversing the tree.</span></span> <span data-ttu-id="0a600-142">Hier ist eine aktualisierte Version der Aggregatmethode, die ziemlich viel Ablaufverfolgungsinformationen enthält:</span><span class="sxs-lookup"><span data-stu-id="0a600-142">Here's an updated version of the Aggregate method that includes quite a bit of tracing information:</span></span>

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

<span data-ttu-id="0a600-143">Es auf demselben Ausdruck auszuführen, ergibt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0a600-143">Running it on the same expression yields the following output:</span></span>

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

<span data-ttu-id="0a600-144">Verfolgen Sie die Ausgabe und folgen Sie dem obigen Code.</span><span class="sxs-lookup"><span data-stu-id="0a600-144">Trace the output and follow along in the code above.</span></span> <span data-ttu-id="0a600-145">Sie sollten in der Lage sein zu ermitteln, wie der Code auf jeden Knoten zugreift und die Summe berechnet, während er die Struktur durchläuft und die Summe ermittelt.</span><span class="sxs-lookup"><span data-stu-id="0a600-145">You should be able to work out how the code visits each node and computes the sum as it goes through the tree and finds the sum.</span></span>

<span data-ttu-id="0a600-146">Jetzt sehen wir uns eine andere Ausführung mit dem von `sum1` zur Verfügung gestellten Ausdruck an:</span><span class="sxs-lookup"><span data-stu-id="0a600-146">Now, let's look at a different run, with the expression given by `sum1`:</span></span>

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

<span data-ttu-id="0a600-147">Hier ist die Ausgabe von der Untersuchung dieses Ausdrucks:</span><span class="sxs-lookup"><span data-stu-id="0a600-147">Here's the output from examining this expression:</span></span>

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

<span data-ttu-id="0a600-148">Während die endgültige Antwort identisch ist, ist das Durchlaufen der Struktur unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="0a600-148">While the final answer is the same, the tree traversal is completely different.</span></span> <span data-ttu-id="0a600-149">Die Knoten werden in einer anderen Reihenfolge zurückgelegt, da die Struktur mit verschiedenen Vorgängen zuerst erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0a600-149">The nodes are traveled in a different order, because the tree was constructed with different operations occurring first.</span></span>

## <a name="learning-more"></a><span data-ttu-id="0a600-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a600-150">Learning More</span></span>

<span data-ttu-id="0a600-151">Dieses Beispiel zeigt eine kleine Teilmenge des Codes, den Sie erstellen möchten, um die durch eine Ausdrucksbaumstruktur dargestellten Algorithmen zu durchlaufen und zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="0a600-151">This sample shows a small subset of the code you would build to traverse and interpret the algorithms represented by an expression tree.</span></span> <span data-ttu-id="0a600-152">Für eine vollständige Beschreibung aller notwendigen Arbeiten zur Erstellung einer allgemeinen Bibliothek, die Ausdrucksbaumstrukturen in eine andere Sprache übersetzt, lesen Sie [diese Serie](https://docs.microsoft.com/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) von Matt Warren.</span><span class="sxs-lookup"><span data-stu-id="0a600-152">For a complete discussion of all the work necessary to build a general purpose library that translates expression trees into another language, please read [this series](https://docs.microsoft.com/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) by Matt Warren.</span></span> <span data-ttu-id="0a600-153">Es wird bis ins Detail erklärt, wie jeder Code übersetzt wird, den Sie in einer Ausdrucksbaumstruktur finden könnten.</span><span class="sxs-lookup"><span data-stu-id="0a600-153">It goes into great detail on how to translate any of the code you might find in an expression tree.</span></span>

<span data-ttu-id="0a600-154">Ich hoffe, dass Sie jetzt die tatsächliche Leistungsfähigkeit von Ausdrucksbaumstrukturen gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="0a600-154">I hope you've now seen the true power of expression trees.</span></span>
<span data-ttu-id="0a600-155">Sie können einen Satz von Code untersuchen, alle Änderungen vornehmen, die Sie für diesen Code haben möchten, und die geänderte Version ausführen.</span><span class="sxs-lookup"><span data-stu-id="0a600-155">You can examine a set of code, make any changes you'd like to that code, and execute the changed version.</span></span> <span data-ttu-id="0a600-156">Da die Ausdrucksbaumstrukturen unveränderlich sind, können Sie neue Strukturen mithilfe der Komponenten von vorhandenen Strukturen erstellen.</span><span class="sxs-lookup"><span data-stu-id="0a600-156">Because the expression trees are immutable, you can create new trees by using the components of existing trees.</span></span> <span data-ttu-id="0a600-157">Dies minimiert die Menge an erforderlichem Arbeitsspeicher, um geänderte Ausdrucksbaumstrukturen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0a600-157">This minimizes the amount of memory needed to create modified expression trees.</span></span>

[<span data-ttu-id="0a600-158">Weiter – Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="0a600-158">Next -- Summing up</span></span>](expression-trees-summary.md)

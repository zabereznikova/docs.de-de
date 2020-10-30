---
title: Interpretieren von Ausdrücken
description: Weitere Informationen zum Schreiben von Code, um die Struktur einer Ausdrucksbaumstruktur zu untersuchen.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: 39baf32c9c53d57227d52b9370f8165ff92d708d
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223674"
---
# <a name="interpreting-expressions"></a><span data-ttu-id="0fdfd-103">Interpretieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="0fdfd-103">Interpreting Expressions</span></span>

[<span data-ttu-id="0fdfd-104">Vorheriges – Ausführen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="0fdfd-104">Previous -- Executing Expressions</span></span>](expression-trees-execution.md)

<span data-ttu-id="0fdfd-105">Lassen Sie uns nun Code schreiben, um die Struktur einer *Ausdrucksbaumstruktur* zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-105">Now, let's write some code to examine the structure of an *expression tree* .</span></span> <span data-ttu-id="0fdfd-106">Jeder Knoten in einer Ausdrucksbaumstruktur ist ein Objekt einer Klasse, die von `Expression` abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-106">Every node in an expression tree will be an object of a class that is derived from `Expression`.</span></span>

<span data-ttu-id="0fdfd-107">Dieser Entwurf macht den Zugriff auf alle Knoten in einer Ausdrucksbaumstruktur zu einem relativ unkomplizierten rekursiven Vorgang.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-107">That design makes visiting all the nodes in an expression tree a relatively straight forward recursive operation.</span></span> <span data-ttu-id="0fdfd-108">Die allgemeine Strategie besteht darin, im Stammknoten zu starten und zu bestimmen, welche Art von Knoten es ist.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-108">The general strategy is to start at the root node and determine what kind of node it is.</span></span>

<span data-ttu-id="0fdfd-109">Wenn der Knotentyp untergeordnete Elemente besitzt, greifen Sie rekursiv auf die untergeordneten Elemente zu.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-109">If the node type has children, recursively visit the children.</span></span> <span data-ttu-id="0fdfd-110">Wiederholen Sie den beim Stammknoten verwendeten Prozess bei jedem untergeordneten Knoten: Bestimmen Sie den Typ, und wenn er untergeordnete Elemente aufweist, greifen Sie auf jedes der untergeordneten Elemente zu.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-110">At each child node, repeat the process used at the root node: determine the type, and if the type has children, visit each of the children.</span></span>

## <a name="examining-an-expression-with-no-children"></a><span data-ttu-id="0fdfd-111">Untersuchen eines Ausdrucks ohne untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0fdfd-111">Examining an Expression with No Children</span></span>

<span data-ttu-id="0fdfd-112">Beginnen wir damit, auf jeden Knoten in einer einfachen Ausdrucksbaumstruktur zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-112">Let's start by visiting each node in a simple expression tree.</span></span>
<span data-ttu-id="0fdfd-113">Hier ist der Code, der einen konstanten Ausdruck erstellt und anschließend seine Eigenschaften überprüft:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-113">Here's the code that creates a constant expression and then examines its properties:</span></span>

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

<span data-ttu-id="0fdfd-114">Dadurch wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-114">This will print the following:</span></span>

```output
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

<span data-ttu-id="0fdfd-115">Jetzt schreiben wir den Code, der diesen Ausdruck untersuchen und einige wichtige Eigenschaften darüber schreiben würde.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-115">Now, let's write the code that would examine this expression and write out some important properties about it.</span></span> <span data-ttu-id="0fdfd-116">Hier ist dieser Code:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-116">Here's that code:</span></span>

## <a name="examining-a-simple-addition-expression"></a><span data-ttu-id="0fdfd-117">Untersuchen eines einfachen Additionsausdrucks</span><span class="sxs-lookup"><span data-stu-id="0fdfd-117">Examining a simple Addition Expression</span></span>

<span data-ttu-id="0fdfd-118">Beginnen wir mit dem Hinzufügen-Beispiel aus der Einführung zu diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-118">Let's start with the addition sample from the introduction to this section.</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> <span data-ttu-id="0fdfd-119">Ich verwende kein `var`, um diese Ausdrucksbaumstruktur zu deklarieren, da es nicht möglich ist, weil die rechte Seite der Zuweisung implizit typisiert ist.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-119">I'm not using `var` to declare this expression tree, as it is not possible because the right-hand side of the assignment is implicitly typed.</span></span>

<span data-ttu-id="0fdfd-120">Der Stammknoten ist ein `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-120">The root node is a `LambdaExpression`.</span></span> <span data-ttu-id="0fdfd-121">Um interessanten Code auf der rechten Seite des `=>`-Operators zu erhalten, müssen Sie eines der untergeordneten Elemente des `LambdaExpression` finden.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-121">In order to get the interesting code on the right-hand side of the `=>` operator, you need to find one of the children of the `LambdaExpression`.</span></span> <span data-ttu-id="0fdfd-122">Wir werden dies mit allen Ausdrücken in diesem Abschnitt durchführen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-122">We'll do that with all the expressions in this section.</span></span> <span data-ttu-id="0fdfd-123">Der übergeordnete Knoten hilft uns beim Finden des Rückgabetyps des `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-123">The parent node does help us find the return type of the `LambdaExpression`.</span></span>

<span data-ttu-id="0fdfd-124">Wir müssen rekursiv auf eine Anzahl von Knoten zugreifen, um jeden Knoten in diesem Ausdruck zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-124">To examine each node in this expression, we'll need to recursively visit a number of nodes.</span></span> <span data-ttu-id="0fdfd-125">Hier ist eine einfache erste Implementierung:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-125">Here's a simple first implementation:</span></span>

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

<span data-ttu-id="0fdfd-126">Dieses Beispiel gibt die folgende Ausgabe zurück:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-126">This sample prints the following output:</span></span>

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

<span data-ttu-id="0fdfd-127">Sie werden viele Wiederholungen im obigen Codebeispiel sehen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-127">You'll notice a lot of repetition in the code sample above.</span></span>
<span data-ttu-id="0fdfd-128">Lassen Sie uns dies bereinigen und einen Ausdrucksknoten für Besucher für eine allgemeinere Verwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-128">Let's clean that up and build a more general purpose expression node visitor.</span></span> <span data-ttu-id="0fdfd-129">Dafür müssen wir einen rekursiven Algorithmus schreiben.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-129">That's going to require us to write a recursive algorithm.</span></span> <span data-ttu-id="0fdfd-130">Jeder Knoten kann ein Typ sein, der möglicherweise untergeordnete Elemente aufweist.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-130">Any node could be of a type that might have children.</span></span>
<span data-ttu-id="0fdfd-131">Jeder Knoten mit untergeordneten Elementen erfordert es, dass Sie auf diese untergeordneten Elemente zugreifen und bestimmen, was dieser Knoten ist.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-131">Any node that has children requires us to visit those children and determine what that node is.</span></span> <span data-ttu-id="0fdfd-132">Hier finden Sie die bereinigte Version, die Rekursion verwendet, um auf die Additionsvorgänge zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-132">Here's the cleaned up version that utilizes recursion to visit the addition operations:</span></span>

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

<span data-ttu-id="0fdfd-133">Dieser Algorithmus ist die Grundlage für einen Algorithmus, der jeden beliebigen `LambdaExpression` besuchen kann.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-133">This algorithm is the basis of an algorithm that can visit any arbitrary `LambdaExpression`.</span></span> <span data-ttu-id="0fdfd-134">Es gibt zahlreiche Löcher, da der Code, den ich erstellt habe, nur nach einem kleinen Teil der möglichen Sätze von Knoten in der Ausdrucksbaumstruktur sucht, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-134">There are many holes, namely that the code I created only looks for a very small sample of the possible sets of expression tree nodes that it may encounter.</span></span> <span data-ttu-id="0fdfd-135">Allerdings können Sie dennoch etwas von dem lernen, was er produziert.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-135">However, you can still learn quite a bit from what it produces.</span></span> <span data-ttu-id="0fdfd-136">(Der Standardfall in der `Visitor.CreateFromExpression`-Methode gibt eine Meldung an die Fehlerkonsole, wenn ein neuer Knotentyp gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-136">(The default case in the `Visitor.CreateFromExpression` method prints a message to the error console when a new node type is encountered.</span></span> <span data-ttu-id="0fdfd-137">Auf diese Weise wissen Sie, dass Sie einen neuen Ausdruck hinzufügen können.)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-137">That way, you know to add a new expression type.)</span></span>

<span data-ttu-id="0fdfd-138">Beim Ausführen dieser Besucher auf dem oben gezeigten Additionsausdruck erhalten Sie die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-138">When you run this visitor on the addition expression shown above, you get the following output:</span></span>

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

<span data-ttu-id="0fdfd-139">Nun, da Sie eine allgemeinere Besucherimplementierung erstellt haben, können Sie auf mehr verschiedene Ausdruckstypen zugreifen und diese verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-139">Now that you've built a more general visitor implementation, you can visit and process many more different types of expressions.</span></span>

## <a name="examining-an-addition-expression-with-many-levels"></a><span data-ttu-id="0fdfd-140">Untersuchen eines Additionsausdrucks mit vielen Ebenen</span><span class="sxs-lookup"><span data-stu-id="0fdfd-140">Examining an Addition Expression with Many Levels</span></span>

<span data-ttu-id="0fdfd-141">Wir versuchen ein etwas komplizierteres Beispiel, aber trotzdem beschränken wir die Knotentypen auf Addition:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-141">Let's try a more complicated example, yet still limit the node types to addition only:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

<span data-ttu-id="0fdfd-142">Bevor Sie dies auf dem Besucheralgorithmus ausführen, versuchen Sie eine Denkübung, um herauszufinden, was die Ausgabe sein könnte.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-142">Before you run this on the visitor algorithm, try a thought exercise to work out what the output might be.</span></span> <span data-ttu-id="0fdfd-143">Beachten Sie, dass der `+`-Operator ein *binärer Operator* ist: Er muss über zwei untergeordnete Elemente verfügen, die die linken und rechten Operanden darstellen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-143">Remember that the `+` operator is a *binary operator* : it must have two children, representing the left and right operands.</span></span> <span data-ttu-id="0fdfd-144">Es gibt mehrere Möglichkeiten, eine Struktur zu erstellen, die richtig sein könnte:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-144">There are several possible ways to construct a tree that could be correct:</span></span>

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

<span data-ttu-id="0fdfd-145">Sie sehen die Aufteilung in zwei mögliche Antworten, um die vielversprechendste zu markieren.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-145">You can see the separation into two possible answers to highlight the most promising.</span></span> <span data-ttu-id="0fdfd-146">Die erste stellt *rechtsassoziative* Ausdrücke dar.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-146">The first represents *right associative* expressions.</span></span> <span data-ttu-id="0fdfd-147">Die zweite stellt *linksassoziative* Ausdrücke dar.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-147">The second represent *left associative* expressions.</span></span>
<span data-ttu-id="0fdfd-148">Der Vorteil dieser beiden Formate ist, dass das Format auf jede beliebige Anzahl von Additionsausdrücken skaliert.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-148">The advantage of both of those two formats is that the format scales to any arbitrary number of addition expressions.</span></span>

<span data-ttu-id="0fdfd-149">Wenn Sie diesen Ausdruck über die Besucher ausführen, sehen Sie diese Ausgabe, die überprüft, ob der einfache Additionsausdruck *linksassoziativ* ist.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-149">If you do run this expression through the visitor, you will see this output, verifying that the simple addition expression is *left associative* .</span></span>

<span data-ttu-id="0fdfd-150">Um dieses Beispiel auszuführen und die vollständige Ausdrucksbaumstruktur anzuzeigen, musste ich eine Änderung an der Quelle der Ausdrucksbaumstruktur vornehmen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-150">In order to run this sample, and see the full expression tree, I had to make one change to the source expression tree.</span></span> <span data-ttu-id="0fdfd-151">Wenn die Ausdrucksbaumstruktur alle Konstanten enthält, enthält die resultierende Struktur einfach den konstanten Wert von `10`.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-151">When the expression tree contains all constants, the resulting tree simply contains the constant value of `10`.</span></span> <span data-ttu-id="0fdfd-152">Der Compiler führt alle Additionen aus und reduziert den Ausdruck auf seine einfachste Form.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-152">The compiler performs all the addition and reduces the expression to its simplest form.</span></span> <span data-ttu-id="0fdfd-153">Das Hinzufügen einer Variablen im Ausdruck ist ausreichend, um die ursprüngliche Struktur anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-153">Simply adding one variable in the expression is sufficient to see the original tree:</span></span>

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

<span data-ttu-id="0fdfd-154">Erstellen Sie einen Besucher für diese Summe, und führen Sie den Besucher aus, für den Sie diese Ausgabe sehen:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-154">Create a visitor for this sum and run the visitor you'll see this output:</span></span>

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

<span data-ttu-id="0fdfd-155">Sie können auch eines der anderen Beispiele über den Besuchercode ausführen und sehen, welche Struktur es darstellt.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-155">You can also run any of the other samples through the visitor code and see what tree it represents.</span></span> <span data-ttu-id="0fdfd-156">Hier ist ein Beispiel für den oben stehenden `sum3`-Ausdruck (mit einem zusätzlichen Parameter, um zu verhindern, dass der Compiler die Konstante berechnet):</span><span class="sxs-lookup"><span data-stu-id="0fdfd-156">Here's an example of the `sum3` expression above (with an additional parameter to prevent the compiler from computing the constant):</span></span>

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

<span data-ttu-id="0fdfd-157">Dies ist die Ausgabe vom Besucher:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-157">Here's the output from the visitor:</span></span>

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

<span data-ttu-id="0fdfd-158">Beachten Sie, dass die Klammern nicht Teil der Ausgabe sind.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-158">Notice that the parentheses are not part of the output.</span></span> <span data-ttu-id="0fdfd-159">Es sind keine Knoten in der Ausdrucksbaumstruktur vorhanden, die die Klammern im eingegebenen Ausdruck darstellen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-159">There are no nodes in the expression tree that represent the parentheses in the input expression.</span></span> <span data-ttu-id="0fdfd-160">Die Struktur der Ausdrucksbaumstruktur enthält alle Informationen, die erforderlich sind, um die Rangfolge zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-160">The structure of the expression tree contains all the information necessary to communicate the precedence.</span></span>

## <a name="extending-from-this-sample"></a><span data-ttu-id="0fdfd-161">Erweiterungen aus diesem Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fdfd-161">Extending from this sample</span></span>

<span data-ttu-id="0fdfd-162">Das Beispiel behandelt nur die elementarsten Ausdrucksbaumstrukturen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-162">The sample deals with only the most rudimentary expression trees.</span></span> <span data-ttu-id="0fdfd-163">Der Code, den Sie in diesem Abschnitt gesehen haben, behandelt nur konstante ganze Zahlen und den binären `+`-Operator.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-163">The code you've seen in this section only handles constant integers and the binary `+` operator.</span></span> <span data-ttu-id="0fdfd-164">Als letztes Beispiel aktualisieren wir den Besucher, um einen komplizierteren Ausdruck zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-164">As a final sample, let's update the visitor to handle a more complicated expression.</span></span> <span data-ttu-id="0fdfd-165">Lassen Sie uns dafür sorgen, dass es hierfür funktioniert:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-165">Let's make it work for this:</span></span>

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ?
    1 :
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

<span data-ttu-id="0fdfd-166">Dieser Code stellt eine mögliche Implementierung für die mathematische *Fakultät* -Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-166">This code represents one possible implementation for the mathematical *factorial* function.</span></span> <span data-ttu-id="0fdfd-167">So wie ich diesen Code geschrieben habe, werden zwei Einschränkungen beim Erstellen von Ausdrucksbaumstrukturen durch die Zuweisung von Lambdaausdrücken an Ausdrücke hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-167">The way I've written this code highlights two limitations of building expression trees by assigning lambda expressions to Expressions.</span></span> <span data-ttu-id="0fdfd-168">Erstens sind Anweisungslambdas nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-168">First, statement lambdas are not allowed.</span></span> <span data-ttu-id="0fdfd-169">Das bedeutet, ich kann keine Schleifen, Blöcke, if/else-Anweisungen und anderen allgemeinen Steuerungsstrukturen in C# verwenden.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-169">That means I can't use loops, blocks, if / else statements, and other control structures common in C#.</span></span> <span data-ttu-id="0fdfd-170">Ich kann nur Ausdrücke verwenden.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-170">I'm limited to using expressions.</span></span> <span data-ttu-id="0fdfd-171">Zweitens kann ich nicht denselben Ausdruck rekursiv aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-171">Second, I can't recursively call the same expression.</span></span>
<span data-ttu-id="0fdfd-172">Ich könnte dies, wenn er bereits ein Delegat wäre, aber ich kann ihn nicht in seiner Form der Ausdrucksbaumstruktur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-172">I could if it were already a delegate, but I can't call it in its expression tree form.</span></span> <span data-ttu-id="0fdfd-173">Im Abschnitt zum [Erstellen von Ausdrucksbaumstrukturen](expression-trees-building.md) werden Sie Techniken erlernen, um diese Einschränkung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-173">In the section on [building expression trees](expression-trees-building.md), you'll learn techniques to overcome these limitations.</span></span>

<span data-ttu-id="0fdfd-174">In diesem Ausdruck können Knoten all dieser Typen auftreten:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-174">In this expression, you'll encounter nodes of all these types:</span></span>

1. <span data-ttu-id="0fdfd-175">Gleich (binärer Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-175">Equal (binary expression)</span></span>
2. <span data-ttu-id="0fdfd-176">Multiplizieren (binärer Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-176">Multiply (binary expression)</span></span>
3. <span data-ttu-id="0fdfd-177">Bedingt (der ?</span><span class="sxs-lookup"><span data-stu-id="0fdfd-177">Conditional (the ?</span></span> <span data-ttu-id="0fdfd-178">: Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-178">: expression)</span></span>
4. <span data-ttu-id="0fdfd-179">Ausdruck des Methodenaufrufs (Aufrufen von `Range()` und `Aggregate()`)</span><span class="sxs-lookup"><span data-stu-id="0fdfd-179">Method Call Expression (calling `Range()` and `Aggregate()`)</span></span>

<span data-ttu-id="0fdfd-180">Eine Möglichkeit zum Ändern des Besucheralgorithmus besteht darin, ihn auszuführen, und den Knotentyp jedes Mal, wenn Sie Ihre `default`-Klausel erreichen, zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-180">One way to modify the visitor algorithm is to keep executing it, and write the node type every time you reach your `default` clause.</span></span> <span data-ttu-id="0fdfd-181">Nach einigen Iterationen haben Sie alle möglichen Knoten gesehen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-181">After a few iterations, you'll have seen each of the potential nodes.</span></span> <span data-ttu-id="0fdfd-182">Dann haben Sie alles, was Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-182">Then, you have all you need.</span></span> <span data-ttu-id="0fdfd-183">Das Ergebnis würde in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-183">The result would be something like this:</span></span>

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

<span data-ttu-id="0fdfd-184">ConditionalVisitor und MethodCallVisitor verarbeiten diese zwei Knoten:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-184">The ConditionalVisitor and MethodCallVisitor process those two nodes:</span></span>

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

<span data-ttu-id="0fdfd-185">Und die Ausgabe für die Ausdrucksbaumstruktur wäre:</span><span class="sxs-lookup"><span data-stu-id="0fdfd-185">And the output for the expression tree would be:</span></span>

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

## <a name="extending-the-sample-library"></a><span data-ttu-id="0fdfd-186">Erweitern Sie die Beispielbibliothek</span><span class="sxs-lookup"><span data-stu-id="0fdfd-186">Extending the Sample Library</span></span>

<span data-ttu-id="0fdfd-187">Die Beispiele in diesem Abschnitt zeigen die Kerntechniken, um Knoten in einer Ausdrucksbaumstruktur zu besuchen und zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-187">The samples in this section show the core techniques to visit and examine nodes in an expression tree.</span></span> <span data-ttu-id="0fdfd-188">Ich habe viele Aktionen ausgelassen, die Sie möglicherweise benötigen, um sich auf die wichtigsten Aufgaben beim Zugriff auf die Knoten in einer Ausdrucksbaumstruktur zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-188">I glossed over many actions you might need in order to concentrate on the core tasks of visiting and accessing nodes in an expression tree.</span></span>

<span data-ttu-id="0fdfd-189">Erstens behandelt der Besucher nur Konstanten, die ganze Zahlen sind.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-189">First, the visitors only handle constants that are integers.</span></span> <span data-ttu-id="0fdfd-190">Konstante Werte können jeder andere numerische Typ sein, und die C#-Sprache unterstützt Konvertierungen und Werbeaktionen zwischen diesen Typen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-190">Constant values could be any other numeric type, and the C# language supports conversions and promotions between those types.</span></span> <span data-ttu-id="0fdfd-191">Eine robustere Version dieses Codes würde alle diese Funktionen widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-191">A more robust version of this code would mirror all those capabilities.</span></span>

<span data-ttu-id="0fdfd-192">Sogar das letzte Beispiel erkennt eine Teilmenge der möglichen Knotentypen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-192">Even the last example recognizes a subset of the possible node types.</span></span>
<span data-ttu-id="0fdfd-193">Sie können weiterhin viele Ausdrücke eingeben, die Fehler verursachen werden.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-193">You can still feed it many expressions that will cause it to fail.</span></span>
<span data-ttu-id="0fdfd-194">Eine vollständige Implementierung ist in .NET Standard unter dem Namen <xref:System.Linq.Expressions.ExpressionVisitor> enthalten und kann alle möglichen Knotentypen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-194">A full implementation is included in .NET Standard under the name <xref:System.Linq.Expressions.ExpressionVisitor> and can handle all the possible node types.</span></span>

<span data-ttu-id="0fdfd-195">Schließlich wurde die Bibliothek, die ich in diesem Artikel verwendet habe, für Demo- und Lernzwecke erstellt.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-195">Finally, the library I used in this article was built for demonstration and learning.</span></span> <span data-ttu-id="0fdfd-196">Sie ist nicht optimiert.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-196">It's not optimized.</span></span> <span data-ttu-id="0fdfd-197">Ich habe sie geschrieben, um die verwendeten Strukturen klar zu machen und um die verwendeten Techniken für den Zugriff auf die Knoten hervorzuheben und zu analysieren, was sich dort befindet.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-197">I wrote it to make the structures used clear, and to highlight the techniques used to visit the nodes and analyze what's there.</span></span> <span data-ttu-id="0fdfd-198">Eine Produktionsimplementierung würde mehr Aufmerksamkeit auf die Leistung legen, als ich es habe.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-198">A production implementation would pay more attention to performance than I have.</span></span>

<span data-ttu-id="0fdfd-199">Selbst mit diesen Einschränkungen sollten Sie sich auf dem richtigen Weg zum Schreiben von Algorithmen befinden, die Ausdrucksbaumstrukturen lesen und verstehen.</span><span class="sxs-lookup"><span data-stu-id="0fdfd-199">Even with those limitations, you should be well on your way to writing algorithms that read and understand expression trees.</span></span>

[<span data-ttu-id="0fdfd-200">Weiter – Erstellen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="0fdfd-200">Next -- Building Expressions</span></span>](expression-trees-building.md)

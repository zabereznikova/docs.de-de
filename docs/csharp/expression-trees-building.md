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
# <a name="building-expression-trees"></a><span data-ttu-id="dc549-103">Erstellen von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="dc549-103">Building Expression Trees</span></span>

[<span data-ttu-id="dc549-104">Vorheriges - Interpretieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="dc549-104">Previous -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)

<span data-ttu-id="dc549-105">Alle Ausdrucksbaumstrukturen, die Sie bisher gesehen haben, wurden vom C#-Compiler erstellt.</span><span class="sxs-lookup"><span data-stu-id="dc549-105">All the expression trees you've seen so far have been created by the C# compiler.</span></span> <span data-ttu-id="dc549-106">Sie müssen einfach einen Lambdaausdruck erstellen, der einer typisierten Variable als `Expression<Func<T>>` oder als einen ähnlichen Typ zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="dc549-106">All you had to do was create a lambda expression that was assigned to a variable typed as an `Expression<Func<T>>` or some similar type.</span></span> <span data-ttu-id="dc549-107">Das ist nicht die einzige Möglichkeit, eine Ausdrucksbaumstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc549-107">That's not the only way to create an expression tree.</span></span> <span data-ttu-id="dc549-108">Für viele Szenarios stellen Sie möglicherweise fest, dass Sie einen Ausdruck im Arbeitsspeicher zur Laufzeit erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="dc549-108">For many scenarios you may find that you need to build an expression in memory at runtime.</span></span> 

<span data-ttu-id="dc549-109">Das Erstellen von Ausdrucksbaumstrukturen ist kompliziert, da diese Ausdrucksbaumstrukturen unveränderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dc549-109">Building Expression Trees is complicated by the fact that those expression trees are immutable.</span></span> <span data-ttu-id="dc549-110">Unveränderlich bedeutet, dass Sie die Struktur von den Blättern bis zum Stamm erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="dc549-110">Being immutable means that you must build the tree from the leaves up to the root.</span></span> <span data-ttu-id="dc549-111">Die APIs, die Sie zum Erstellen von Ausdrucksbaumstrukturen verwenden, spiegeln diese Tatsache wider: Die Methoden, die Sie verwenden, um einen Knoten zu erstellen, nehmen alle untergeordneten Elemente als Argumente.</span><span class="sxs-lookup"><span data-stu-id="dc549-111">The APIs you'll use to build expression trees reflect this fact: The methods you'll use to build a node take all its children as arguments.</span></span> <span data-ttu-id="dc549-112">Betrachten wir einige Beispiele, die Ihnen die Techniken zeigen.</span><span class="sxs-lookup"><span data-stu-id="dc549-112">Let's walk through a few examples to show you the techniques.</span></span>

## <a name="creating-nodes"></a><span data-ttu-id="dc549-113">Erstellen von Knoten</span><span class="sxs-lookup"><span data-stu-id="dc549-113">Creating Nodes</span></span>

<span data-ttu-id="dc549-114">Beginnen wir erneut relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="dc549-114">Let's start relatively simply again.</span></span> <span data-ttu-id="dc549-115">Wir verwenden den Additionsausdruck, mit dem ich in diesen Abschnitten arbeiten werde:</span><span class="sxs-lookup"><span data-stu-id="dc549-115">We'll use the addition expression I've been working with throughout these sections:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

<span data-ttu-id="dc549-116">Um diese Ausdrucksbaumstruktur zu erstellen, müssen Sie die Endknoten erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc549-116">To construct that expression tree, you must construct the leaf nodes.</span></span>
<span data-ttu-id="dc549-117">Die Endknoten sind Konstanten, damit Sie die `Expression.Constant`-Methode verwenden können, um die Knoten zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="dc549-117">The leaf nodes are constants, so you can use the `Expression.Constant` method to create the nodes:</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
```

<span data-ttu-id="dc549-118">Als Nächstes erstellen Sie den Additionsausdruck:</span><span class="sxs-lookup"><span data-stu-id="dc549-118">Next, you'll build the addition expression:</span></span>

```csharp
var addition = Expression.Add(one, two);
```

<span data-ttu-id="dc549-119">Sobald Sie den Additionsausdruck haben, können Sie den Lambdaausdruck erstellen:</span><span class="sxs-lookup"><span data-stu-id="dc549-119">Once you've got the addition expression, you can create the lambda expression:</span></span>

```csharp
var lambda = Expression.Lambda(addition);
```

<span data-ttu-id="dc549-120">Dies ist ein sehr einfacher Lambdaausdruck, da er keine Argumente enthält.</span><span class="sxs-lookup"><span data-stu-id="dc549-120">This is a very simple lambda expression, because it contains no arguments.</span></span>
<span data-ttu-id="dc549-121">In diesem Abschnitt erfahren Sie später, wie Sie Parametern Argumente zuordnen und kompliziertere Ausdrücke erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc549-121">Later in this section, you'll see how to map arguments to parameters and build more complicated expressions.</span></span>

<span data-ttu-id="dc549-122">Für Ausdrücke, die so einfach wie dieser sind, können Sie alle Aufrufe in einer einzelnen Anweisung kombinieren:</span><span class="sxs-lookup"><span data-stu-id="dc549-122">For expressions that are as simple as this one, you may combine all the calls into a single statement:</span></span>

```csharp
var lambda = Expression.Lambda(
    Expression.Add(
        Expression.Constant(1, typeof(int)),
        Expression.Constant(2, typeof(int))
    )
);
```

## <a name="building-a-tree"></a><span data-ttu-id="dc549-123">Erstellen einer Struktur</span><span class="sxs-lookup"><span data-stu-id="dc549-123">Building a Tree</span></span>

<span data-ttu-id="dc549-124">Das sind die Grundlagen der Erstellung einer Ausdrucksbaumstruktur im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="dc549-124">That's the basics of building an expression tree in memory.</span></span> <span data-ttu-id="dc549-125">Komplexere Strukturen bedeuten im Allgemeinen mehr Knotentypen und weitere Knoten in der Struktur.</span><span class="sxs-lookup"><span data-stu-id="dc549-125">More complex trees generally mean more node types, and more nodes in the tree.</span></span> <span data-ttu-id="dc549-126">Lassen Sie uns ein weiteres Beispiel ausführen, und zwei weitere Knotentypen, die Sie in der Regel beim Erstellen von Ausdrucksbaumstrukturen erstellen, anzeigen: Die Argumentknoten und Methodenaufrufknoten.</span><span class="sxs-lookup"><span data-stu-id="dc549-126">Let's run through one more example and show two more node types that you will typically build when you create expression trees: the argument nodes, and method call nodes.</span></span>

<span data-ttu-id="dc549-127">Wir erstellen eine Ausdrucksbaumstruktur, um diesen Ausdruck zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="dc549-127">Let's build an expression tree to create this expression:</span></span>

```csharp
Expression<Func<double, double, double>> distanceCalc =
    (x, y) => Math.Sqrt(x * x + y * y);
```
 
<span data-ttu-id="dc549-128">Sie beginnen mit dem Erstellen der Parameterausdrücke für `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="dc549-128">You'll start by creating parameter expressions for `x` and `y`:</span></span>

```csharp
var xParameter = Expression.Parameter(typeof(double), "x");
var yParameter = Expression.Parameter(typeof(double), "y");
```

<span data-ttu-id="dc549-129">Das Erstellen der Multiplikations- und Additionsausdrücke folgt dem Muster, das Sie bereits gesehen haben:</span><span class="sxs-lookup"><span data-stu-id="dc549-129">Creating the multiplication and addition expressions follows the pattern you've already seen:</span></span>

```csharp
var xSquared = Expression.Multiply(xParameter, xParameter);
var ySquared = Expression.Multiply(yParameter, yParameter);
var sum = Expression.Add(xSquared, ySquared);
```

<span data-ttu-id="dc549-130">Anschließend müssen Sie einen Ausdruck des Methodenaufrufs für den Aufruf von `Math.Sqrt` erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc549-130">Next, you need to create a method call expression for the call to `Math.Sqrt`.</span></span>

```csharp
var sqrtMethod = typeof(Math).GetMethod("Sqrt", new[] { typeof(double) });
var distance = Expression.Call(sqrtMethod, sum);
```

<span data-ttu-id="dc549-131">Und anschließend legen Sie den Methodenaufruf in einen Lambdaausdruck, und stellen sicher, dass Sie die Argumente für den Lambdaausdruck definieren:</span><span class="sxs-lookup"><span data-stu-id="dc549-131">And  then finally, you put the method call into a lambda expression, and make sure to define the arguments to the lambda expression:</span></span>

```csharp
var distanceLambda = Expression.Lambda(
    distance,
    xParameter,
    yParameter);
```

<span data-ttu-id="dc549-132">In diesem komplizierteren Beispiel sehen Sie ein paar weitere Verfahren, die Sie häufig benötigen, um Ausdrucksbaumstrukturen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc549-132">In this more complicated example, you see a couple more techniques that you will often need to create expression trees.</span></span>

<span data-ttu-id="dc549-133">Zunächst müssen Sie die Objekte erstellen, die Parameter oder lokale Variablen darstellen, bevor Sie sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc549-133">First, you need to create the objects that represent parameters or local variables before you use them.</span></span> <span data-ttu-id="dc549-134">Wenn Sie diese Objekte erstellt haben, können Sie diese in Ihrer Ausdrucksbaumstruktur verwenden, wo immer Sie sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="dc549-134">Once you've created those objects, you can use them in your expression tree wherever you need.</span></span>

<span data-ttu-id="dc549-135">Zweitens müssen Sie einen Teil der Reflektions-APIs verwenden, um ein `MethodInfo`-Objekt zu erstellen, sodass Sie eine Ausdrucksbaumstruktur für den Zugriff auf diese Methode erstellen können.</span><span class="sxs-lookup"><span data-stu-id="dc549-135">Second, you need to use a subset of the Reflection APIs to create a `MethodInfo` object so that you can create an expression tree to access that method.</span></span> <span data-ttu-id="dc549-136">Sie müssen sich auf die Teilmenge der Reflektions-APIs begrenzen, die auf der .NET Core-Plattform verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dc549-136">You must limit yourself to the subset of the Reflection APIs that are available on the .NET Core platform.</span></span> <span data-ttu-id="dc549-137">In diesem Fall werden diese Techniken auf andere Ausdrucksbaumstrukturen erweitert.</span><span class="sxs-lookup"><span data-stu-id="dc549-137">Again, these techniques will extend to other expression trees.</span></span>

## <a name="building-code-in-depth"></a><span data-ttu-id="dc549-138">Erstellen von Code im Detail</span><span class="sxs-lookup"><span data-stu-id="dc549-138">Building Code In Depth</span></span>

<span data-ttu-id="dc549-139">Sie sind nicht darin beschränkt, was Sie mithilfe dieser APIs erstellen können.</span><span class="sxs-lookup"><span data-stu-id="dc549-139">You aren't limited in what you can build using these APIs.</span></span> <span data-ttu-id="dc549-140">Je komplizierter jedoch die Ausdrucksbaumstruktur ist, die Sie erstellen möchten, desto schwieriger ist der Code zu verwalten und zu lesen.</span><span class="sxs-lookup"><span data-stu-id="dc549-140">However, the more complicated expression tree that you want to build, the more difficult the code is to manage and to read.</span></span> 

<span data-ttu-id="dc549-141">Wir erstellen eine Ausdrucksbaumstruktur, die diesem Code entspricht:</span><span class="sxs-lookup"><span data-stu-id="dc549-141">Let's build an expression tree that is the equivalent of this code:</span></span>

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

<span data-ttu-id="dc549-142">Beachten Sie oben, dass ich nicht die Ausdrucksbaumstruktur, aber einfach den Delegaten erstellt habe.</span><span class="sxs-lookup"><span data-stu-id="dc549-142">Notice above that I did not build the expression tree, but simply the delegate.</span></span> <span data-ttu-id="dc549-143">Mithilfe der `Expression`-Klasse können Sie keine Anweisungslambdas erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc549-143">Using the `Expression` class, you can't build statement lambdas.</span></span> <span data-ttu-id="dc549-144">Hier ist der Code, der erforderlich ist, um die gleiche Funktionalität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc549-144">Here's the code that is required to build the same functionality.</span></span> <span data-ttu-id="dc549-145">Es ist etwas kompliziert, dass es keine API zum Erstellen einer `while`-Schleife gibt. Stattdessen müssen Sie eine Schleife, die einen bedingten Test enthält, und ein Bezeichnungsziel erstellen, um die Schleife zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="dc549-145">It's complicated by the fact that there isn't an API to build a `while` loop, instead you need to build a loop that contains a conditional test, and a label target to break out of the loop.</span></span> 

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

<span data-ttu-id="dc549-146">Der Code zum Erstellen der Baumstruktur für die Fakultätsfunktion ist etwas länger, komplizierter, und er ist voll von Bezeichnungen und Break-Anweisungen und anderen Elemente, die wir in unseren täglichen Codieraufgaben vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="dc549-146">The code to build the expression tree for the factorial function is quite a bit longer, more complicated, and it's riddled with labels and break statements and other elements we'd like to avoid in our everyday coding tasks.</span></span> 

<span data-ttu-id="dc549-147">Für diesen Abschnitt habe ich auch den Besuchercode aktualisiert, um jeden Knoten in dieser Ausdrucksbaumstruktur zu finden, und Informationen zu den Knoten, die in diesem Beispiel erstellt wurden, zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="dc549-147">For this section, I've also updated the visitor code to visit every node in this expression tree and write out information about the nodes that are created in this sample.</span></span> <span data-ttu-id="dc549-148">Sie können den Beispielcode vom Repository „dotnet/docs“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/csharp/expression-trees).</span><span class="sxs-lookup"><span data-stu-id="dc549-148">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/csharp/expression-trees) at the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="dc549-149">Experimentieren Sie selbst, indem Sie die Beispiele erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="dc549-149">Experiment for yourself by building and running the samples.</span></span> <span data-ttu-id="dc549-150">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="dc549-150">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="examining-the-apis"></a><span data-ttu-id="dc549-151">Untersuchen der APIs</span><span class="sxs-lookup"><span data-stu-id="dc549-151">Examining the APIs</span></span>

<span data-ttu-id="dc549-152">Die Ausdrucksbaumstruktur-APIs sind einige der Schwierigeren zum Navigieren in .NET Core, aber das ist in Ordnung.</span><span class="sxs-lookup"><span data-stu-id="dc549-152">The expression tree APIs are some of the more difficult to navigate in .NET Core, but that's fine.</span></span> <span data-ttu-id="dc549-153">Ihr Zweck ist ein recht komplexes Unterfangen: Schreiben von Code, der Code zur Laufzeit generiert.</span><span class="sxs-lookup"><span data-stu-id="dc549-153">Their purpose is a rather complex undertaking: writing code that generates code at runtime.</span></span> <span data-ttu-id="dc549-154">Sie sind notwendigerweise kompliziert, um ein Gleichgewicht zwischen der Unterstützung aller verfügbaren Steuerungsstrukturen in der C#-Sprache bereitzustellen und um die Oberfläche der APIs so klein wie angemessenen zu halten.</span><span class="sxs-lookup"><span data-stu-id="dc549-154">They are necessarily complicated to provide a balance between supporting all the control structures available in the C# language and keeping the surface area of the APIs as small as reasonable.</span></span> <span data-ttu-id="dc549-155">Diese Balance bedeutet, dass viele Steuerungsstrukturen nicht über die C#-Konstrukte dargestellt werden, jedoch über Konstrukte, die die zugrunde liegende Logik darstellen, die der Compiler von diesen Konstrukten mit höherer Ebene generiert.</span><span class="sxs-lookup"><span data-stu-id="dc549-155">This balance means that many control structures are represented not by their C# constructs, but by constructs that represent the underlying logic that the compiler generates from these higher level constructs.</span></span> 

<span data-ttu-id="dc549-156">Außerdem sind zu diesem Zeitpunkt C#-Ausdrücke vorhanden, die nicht direkt mit `Expression`-Klassenmethoden erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="dc549-156">Also, at this time, there are C# expressions that cannot be built directly using `Expression` class methods.</span></span> <span data-ttu-id="dc549-157">Im Allgemeinen werden dies die neuesten Operatoren und Ausdrücke sein, die in C# 5 und C# 6 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dc549-157">In general, these will be the newest operators and expressions added in C# 5 and C# 6.</span></span> <span data-ttu-id="dc549-158">(Z.B. `async`-Ausdrücke können nicht erstellt werden, und der neue `?.`-Operator kann nicht direkt erstellt werden.)</span><span class="sxs-lookup"><span data-stu-id="dc549-158">(For example, `async` expressions cannot be built, and the new `?.` operator cannot be directly created.)</span></span>

[<span data-ttu-id="dc549-159">Weiter– Übersetzen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="dc549-159">Next -- Translating Expressions</span></span>](expression-trees-translating.md)

---
title: "Framework-Typen, die Ausdrucksbaumstrukturen unterstützen"
description: "Erfahren Sie mehr zu Frameworktypen, die Ausdrucksbaumstrukturen unterstützen, wie Sie diese erstellen können und Methoden zum Arbeiten mit Ausdrucksbaumstruktur-APIs."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ed89b286eee9b4c2e11bb27d18e50f777f94f33e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="framework-types-supporting-expression-trees"></a><span data-ttu-id="2e73b-104">Framework-Typen, die Ausdrucksbaumstrukturen unterstützen</span><span class="sxs-lookup"><span data-stu-id="2e73b-104">Framework Types Supporting Expression Trees</span></span>

[<span data-ttu-id="2e73b-105">Vorherige – Ausdrucksbaumstrukturen mit Erläuterung</span><span class="sxs-lookup"><span data-stu-id="2e73b-105">Previous -- Expression Trees Explained</span></span>](expression-trees-explained.md)

<span data-ttu-id="2e73b-106">Es gibt eine umfangreiche Liste von Klassen im .NET Core Framework, die mit Ausdrucksbaumstrukturen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2e73b-106">There is a large list of classes in the .NET Core framework that work with Expression Trees.</span></span>
<span data-ttu-id="2e73b-107">[Hier](/dotnet/core/api/System.Linq.Expressions) finden Sie die vollständige Liste.</span><span class="sxs-lookup"><span data-stu-id="2e73b-107">You can see the full list [here](/dotnet/core/api/System.Linq.Expressions).</span></span>
<span data-ttu-id="2e73b-108">Anstatt die vollständige Liste zu durchlaufen, sehen wir uns an, wie die Framework-Klassen entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="2e73b-108">Rather than run through the full list, let's understand how the framework classes have been designed.</span></span>

<span data-ttu-id="2e73b-109">Im Sprachentwurf ist ein Ausdruck ein Teil eines Codes, der ausgewertet wird und einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2e73b-109">In language design, an expression is a body of code that evaluates and returns a value.</span></span> <span data-ttu-id="2e73b-110">Ausdrücke können sehr einfach sein: Der konstante Ausdruck `1` gibt den konstanten Wert 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="2e73b-110">Expressions may be very simple: the constant expression `1` returns the constant value of 1.</span></span> <span data-ttu-id="2e73b-111">Sie sind möglicherweise komplizierter: Der Ausdruck `(-B + Math.Sqrt(B*B + 4 * A * C)) / (2 * A)` gibt ein Stammverzeichnis für eine quadratische Gleichung zurück (in dem Fall, in dem die Gleichung eine Lösung hat).</span><span class="sxs-lookup"><span data-stu-id="2e73b-111">They may be more complicated: The expression `(-B + Math.Sqrt(B*B + 4 * A * C)) / (2 * A)` returns one root for a quadratic equation (in the case where the equation has a solution).</span></span>  

## <a name="it-all-starts-with-systemlinqexpression"></a><span data-ttu-id="2e73b-112">Es beginnt alles mit System.Linq.Expression</span><span class="sxs-lookup"><span data-stu-id="2e73b-112">It all starts with System.Linq.Expression</span></span>

<span data-ttu-id="2e73b-113">Eine der Komplexitäten der Arbeit mit Ausdrucksbaumstrukturen ist, dass viele verschiedene Arten von Ausdrücken an vielen Stellen in Programmen gültig sind.</span><span class="sxs-lookup"><span data-stu-id="2e73b-113">One of the complexities of working with expression trees is that many different kinds of expressions are valid in many places in programs.</span></span> <span data-ttu-id="2e73b-114">Betrachten Sie einen Zuweisungsausdruck.</span><span class="sxs-lookup"><span data-stu-id="2e73b-114">Consider an assignment expression.</span></span> <span data-ttu-id="2e73b-115">Die rechte Seite einer Zuweisung kann ein konstanter Wert, eine Variable, ein Methodenaufrufausdruck oder anderes sein.</span><span class="sxs-lookup"><span data-stu-id="2e73b-115">The right hand side of an assignment could be a constant value, a variable, a method call expression, or others.</span></span> <span data-ttu-id="2e73b-116">Die Sprachflexibilität bedeutet, dass Sie viele unterschiedliche Ausdruckstypen an beliebigen Stellen in den Knoten einer Struktur erhalten können, wenn Sie eine Ausdrucksbaumstruktur durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-116">That language flexibility means that you may encounter many different expression types anywhere in the nodes of a tree when you traverse an expression tree.</span></span> <span data-ttu-id="2e73b-117">Wenn Sie mit dem Typ des Ausdrucks arbeiten können, ist dies daher der einfachste Weg zum Arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2e73b-117">Therefore, when you can work with the base expression type, that's the simplest way to work.</span></span> <span data-ttu-id="2e73b-118">Allerdings müssen Sie manchmal mehr wissen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-118">However, sometimes you need to know more.</span></span>
<span data-ttu-id="2e73b-119">Die Basisausdrucksklasse enthält eine `NodeType`-Eigenschaft für diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="2e73b-119">The base Expression class contains a `NodeType` property for this purpose.</span></span>
<span data-ttu-id="2e73b-120">Es gibt einen `ExpressionType` zurück, der eine Enumeration möglicher Ausdruckstypen ist.</span><span class="sxs-lookup"><span data-stu-id="2e73b-120">It returns an `ExpressionType` which is an enumeration of possible expression types.</span></span>
<span data-ttu-id="2e73b-121">Wenn Sie den Typ des Knotens kennen, können Sie es in diesen Typ umwandeln, und bestimmte Aktionen, die den Typ des Ausdrucksknotens kennen, durchführen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-121">Once you know the type of the node, you can cast it to that type, and perform specific actions knowing the type of the expression node.</span></span> <span data-ttu-id="2e73b-122">Sie können nach bestimmten Knoten suchen, und anschließend mit den bestimmten Eigenschaften dieser Art von Ausdruck arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2e73b-122">You can search for certain node types, and then work with the specific properties of that kind of expression.</span></span>

<span data-ttu-id="2e73b-123">Dieser Code wird z.B. den Namen einer Variablen für einen Variablenzugriff des Ausdrucks ausgeben.</span><span class="sxs-lookup"><span data-stu-id="2e73b-123">For example, this code will print the name of a variable for a variable access expression.</span></span> <span data-ttu-id="2e73b-124">Ich habe den Knotentyp überprüft, ihn anschließend in einen Variablenzugriff des Ausdrucks umgewandelt und die Eigenschaften des bestimmten Ausdruckstyps überprüft:</span><span class="sxs-lookup"><span data-stu-id="2e73b-124">I've followed the practice of checking the node type, then casting to a variable access expression and then checking the properties of the specific expression type:</span></span>

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

## <a name="creating-expression-trees"></a><span data-ttu-id="2e73b-125">Erstellen von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="2e73b-125">Creating Expression Trees</span></span>

<span data-ttu-id="2e73b-126">Die `System.Linq.Expression`-Klasse enthält außerdem viele statische Methoden zum Erstellen von Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="2e73b-126">The `System.Linq.Expression` class also contains many static methods to create expressions.</span></span> <span data-ttu-id="2e73b-127">Diese Methoden erstellen mithilfe der Argumente für seine untergeordneten Elemente einen Ausdrucksknoten.</span><span class="sxs-lookup"><span data-stu-id="2e73b-127">These methods create an expression node using the arguments supplied for its children.</span></span> <span data-ttu-id="2e73b-128">Auf diese Weise erstellen Sie einen Ausdruck über seine Endknoten.</span><span class="sxs-lookup"><span data-stu-id="2e73b-128">In this way, you build an expression up from its leaf nodes.</span></span> <span data-ttu-id="2e73b-129">Dieser Code erstellt z.B. einen Add-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="2e73b-129">For example, this code builds an Add expression:</span></span>

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

<span data-ttu-id="2e73b-130">Sie können in diesem einfachen Beispiel erkennen, dass viele Typen bei der Erstellung und beim Arbeiten mit Ausdrucksbaumstrukturen beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="2e73b-130">You can see from this simple example that many types are involved in creating and working with expression trees.</span></span> <span data-ttu-id="2e73b-131">Diese Komplexität ist erforderlich, um die Funktionalität des rich-Vokabulars der C#-Sprache bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-131">That complexity is necessary to provide the capabilities of the rich vocabulary provided by the C# language.</span></span>

## <a name="navigating-the-apis"></a><span data-ttu-id="2e73b-132">Navigieren in den APIs</span><span class="sxs-lookup"><span data-stu-id="2e73b-132">Navigating the APIs</span></span>
<span data-ttu-id="2e73b-133">Es gibt Ausdrucksknotentypen, die fast alle Elemente der Syntax der C#-Sprache zuordnen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-133">There are Expression node types that map to almost all of the syntax elements of the C# language.</span></span> <span data-ttu-id="2e73b-134">Jeder Typ verfügt über spezielle Methoden für diese Art von Sprachelement.</span><span class="sxs-lookup"><span data-stu-id="2e73b-134">Each type has specific methods for that type of language element.</span></span> <span data-ttu-id="2e73b-135">Es ist viel, was Sie sich gleichzeitig merken müssen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-135">It's a lot to keep in your head at one time.</span></span> <span data-ttu-id="2e73b-136">Anstatt sich alles zu merken, finden Sie hier die Techniken, die ich zum Arbeiten mit Ausdrucksbaumstrukturen verwende:</span><span class="sxs-lookup"><span data-stu-id="2e73b-136">Rather than try to memorize everything, here are the techniques I use to work with Expression trees:</span></span>
1. <span data-ttu-id="2e73b-137">Betrachten Sie die Member des `ExpressionType`-enum, um mögliche Knoten zu bestimmen, die Sie untersuchen sollten.</span><span class="sxs-lookup"><span data-stu-id="2e73b-137">Look at the members of the `ExpressionType` enum to determine possible nodes you should be examining.</span></span> <span data-ttu-id="2e73b-138">Dies ist wirklich hilfreich, wenn Sie eine Ausdrucksbaumstruktur durchlaufen und verstehen möchten.</span><span class="sxs-lookup"><span data-stu-id="2e73b-138">This really helps when you want to traverse and understand an expression tree.</span></span>
2. <span data-ttu-id="2e73b-139">Betrachten Sie die statischen Member der `Expression`-Klasse, um einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-139">Look at the static members of the `Expression` class to build an expression.</span></span> <span data-ttu-id="2e73b-140">Diese Methoden können jeden Ausdruckstyp aus einer Reihe von untergeordneten Knoten erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-140">Those methods can build any expression type from a set of its child nodes.</span></span>
3. <span data-ttu-id="2e73b-141">Sehen Sie sich die `ExpressionVisitor`-Klasse an, um eine geänderte Ausdrucksbaumstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-141">Look at the `ExpressionVisitor` class to build a modified expression tree.</span></span>

<span data-ttu-id="2e73b-142">Sie werden mehr finden, wenn Sie sich jeden dieser drei Bereiche ansehen.</span><span class="sxs-lookup"><span data-stu-id="2e73b-142">You'll find more as you look at each of those three areas.</span></span> <span data-ttu-id="2e73b-143">Unweigerlich, werden Sie feststellen, was Sie benötigen, wenn Sie mit einem dieser drei Schritte starten.</span><span class="sxs-lookup"><span data-stu-id="2e73b-143">Invariably, you will find what you need when you start with one of those three steps.</span></span>
 
 [<span data-ttu-id="2e73b-144">Weiter -- Ausführen von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="2e73b-144">Next -- Executing Expression Trees</span></span>](expression-trees-execution.md)
 


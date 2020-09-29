---
title: Framework-Typen, die Ausdrucksbaumstrukturen unterstützen
description: Erfahren Sie mehr zu Frameworktypen, die Ausdrucksbaumstrukturen unterstützen, wie Sie diese erstellen können und Methoden zum Arbeiten mit Ausdrucksbaumstruktur-APIs.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.openlocfilehash: 548f5ba6a2de00d9556621791515555b6f6a325c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180438"
---
# <a name="framework-types-supporting-expression-trees"></a><span data-ttu-id="8bed6-103">Framework-Typen, die Ausdrucksbaumstrukturen unterstützen</span><span class="sxs-lookup"><span data-stu-id="8bed6-103">Framework Types Supporting Expression Trees</span></span>

[<span data-ttu-id="8bed6-104">Vorherige – Ausdrucksbaumstrukturen mit Erläuterung</span><span class="sxs-lookup"><span data-stu-id="8bed6-104">Previous -- Expression Trees Explained</span></span>](expression-trees-explained.md)

<span data-ttu-id="8bed6-105">Es gibt eine umfangreiche Liste von Klassen im .NET Core Framework, die mit Ausdrucksbaumstrukturen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8bed6-105">There is a large list of classes in the .NET Core framework that work with Expression Trees.</span></span>
<span data-ttu-id="8bed6-106">Die vollständige Liste finden Sie unter <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="8bed6-106">You can see the full list at <xref:System.Linq.Expressions>.</span></span>
<span data-ttu-id="8bed6-107">Anstatt die vollständige Liste zu durchlaufen, sehen wir uns an, wie die Framework-Klassen entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="8bed6-107">Rather than run through the full list, let's understand how the framework classes have been designed.</span></span>

<span data-ttu-id="8bed6-108">Im Sprachentwurf ist ein Ausdruck ein Teil eines Codes, der ausgewertet wird und einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8bed6-108">In language design, an expression is a body of code that evaluates and returns a value.</span></span> <span data-ttu-id="8bed6-109">Ausdrücke können sehr einfach sein: Der konstante Ausdruck `1` gibt den konstanten Wert 1 zurück.</span><span class="sxs-lookup"><span data-stu-id="8bed6-109">Expressions may be very simple: the constant expression `1` returns the constant value of 1.</span></span> <span data-ttu-id="8bed6-110">Sie sind möglicherweise komplizierter: Der Ausdruck `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` gibt ein Stammverzeichnis für eine quadratische Gleichung zurück (in dem Fall, in dem die Gleichung eine Lösung hat).</span><span class="sxs-lookup"><span data-stu-id="8bed6-110">They may be more complicated: The expression `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` returns one root for a quadratic equation (in the case where the equation has a solution).</span></span>  

## <a name="it-all-starts-with-systemlinqexpression"></a><span data-ttu-id="8bed6-111">Es beginnt alles mit System.Linq.Expression</span><span class="sxs-lookup"><span data-stu-id="8bed6-111">It all starts with System.Linq.Expression</span></span>

<span data-ttu-id="8bed6-112">Eine der Komplexitäten der Arbeit mit Ausdrucksbaumstrukturen ist, dass viele verschiedene Arten von Ausdrücken an vielen Stellen in Programmen gültig sind.</span><span class="sxs-lookup"><span data-stu-id="8bed6-112">One of the complexities of working with expression trees is that many different kinds of expressions are valid in many places in programs.</span></span> <span data-ttu-id="8bed6-113">Betrachten Sie einen Zuweisungsausdruck.</span><span class="sxs-lookup"><span data-stu-id="8bed6-113">Consider an assignment expression.</span></span> <span data-ttu-id="8bed6-114">Die rechte Seite einer Zuweisung kann ein konstanter Wert, eine Variable, ein Methodenaufrufausdruck oder anderes sein.</span><span class="sxs-lookup"><span data-stu-id="8bed6-114">The right hand side of an assignment could be a constant value, a variable, a method call expression, or others.</span></span> <span data-ttu-id="8bed6-115">Die Sprachflexibilität bedeutet, dass Sie viele unterschiedliche Ausdruckstypen an beliebigen Stellen in den Knoten einer Struktur erhalten können, wenn Sie eine Ausdrucksbaumstruktur durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-115">That language flexibility means that you may encounter many different expression types anywhere in the nodes of a tree when you traverse an expression tree.</span></span> <span data-ttu-id="8bed6-116">Wenn Sie mit dem Typ des Ausdrucks arbeiten können, ist dies daher der einfachste Weg zum Arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8bed6-116">Therefore, when you can work with the base expression type, that's the simplest way to work.</span></span> <span data-ttu-id="8bed6-117">Allerdings müssen Sie manchmal mehr wissen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-117">However, sometimes you need to know more.</span></span>
<span data-ttu-id="8bed6-118">Die Basisausdrucksklasse enthält eine `NodeType`-Eigenschaft für diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="8bed6-118">The base Expression class contains a `NodeType` property for this purpose.</span></span>
<span data-ttu-id="8bed6-119">Es gibt einen `ExpressionType` zurück, der eine Enumeration möglicher Ausdruckstypen ist.</span><span class="sxs-lookup"><span data-stu-id="8bed6-119">It returns an `ExpressionType` which is an enumeration of possible expression types.</span></span>
<span data-ttu-id="8bed6-120">Wenn Sie den Typ des Knotens kennen, können Sie es in diesen Typ umwandeln, und bestimmte Aktionen, die den Typ des Ausdrucksknotens kennen, durchführen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-120">Once you know the type of the node, you can cast it to that type, and perform specific actions knowing the type of the expression node.</span></span> <span data-ttu-id="8bed6-121">Sie können nach bestimmten Knoten suchen, und anschließend mit den bestimmten Eigenschaften dieser Art von Ausdruck arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8bed6-121">You can search for certain node types, and then work with the specific properties of that kind of expression.</span></span>

<span data-ttu-id="8bed6-122">Dieser Code wird z.B. den Namen einer Variablen für einen Variablenzugriff des Ausdrucks ausgeben.</span><span class="sxs-lookup"><span data-stu-id="8bed6-122">For example, this code will print the name of a variable for a variable access expression.</span></span> <span data-ttu-id="8bed6-123">Ich habe den Knotentyp überprüft, ihn anschließend in einen Variablenzugriff des Ausdrucks umgewandelt und die Eigenschaften des bestimmten Ausdruckstyps überprüft:</span><span class="sxs-lookup"><span data-stu-id="8bed6-123">I've followed the practice of checking the node type, then casting to a variable access expression and then checking the properties of the specific expression type:</span></span>

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

## <a name="creating-expression-trees"></a><span data-ttu-id="8bed6-124">Erstellen von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="8bed6-124">Creating Expression Trees</span></span>

<span data-ttu-id="8bed6-125">Die `System.Linq.Expression`-Klasse enthält außerdem viele statische Methoden zum Erstellen von Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="8bed6-125">The `System.Linq.Expression` class also contains many static methods to create expressions.</span></span> <span data-ttu-id="8bed6-126">Diese Methoden erstellen mithilfe der Argumente für seine untergeordneten Elemente einen Ausdrucksknoten.</span><span class="sxs-lookup"><span data-stu-id="8bed6-126">These methods create an expression node using the arguments supplied for its children.</span></span> <span data-ttu-id="8bed6-127">Auf diese Weise erstellen Sie einen Ausdruck über seine Endknoten.</span><span class="sxs-lookup"><span data-stu-id="8bed6-127">In this way, you build an expression up from its leaf nodes.</span></span> <span data-ttu-id="8bed6-128">Dieser Code erstellt z.B. einen Add-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="8bed6-128">For example, this code builds an Add expression:</span></span>

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

<span data-ttu-id="8bed6-129">Sie können in diesem einfachen Beispiel erkennen, dass viele Typen bei der Erstellung und beim Arbeiten mit Ausdrucksbaumstrukturen beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="8bed6-129">You can see from this simple example that many types are involved in creating and working with expression trees.</span></span> <span data-ttu-id="8bed6-130">Diese Komplexität ist erforderlich, um die Funktionalität des rich-Vokabulars der C#-Sprache bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-130">That complexity is necessary to provide the capabilities of the rich vocabulary provided by the C# language.</span></span>

## <a name="navigating-the-apis"></a><span data-ttu-id="8bed6-131">Navigieren in den APIs</span><span class="sxs-lookup"><span data-stu-id="8bed6-131">Navigating the APIs</span></span>

<span data-ttu-id="8bed6-132">Es gibt Ausdrucksknotentypen, die fast alle Elemente der Syntax der C#-Sprache zuordnen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-132">There are Expression node types that map to almost all of the syntax elements of the C# language.</span></span> <span data-ttu-id="8bed6-133">Jeder Typ verfügt über spezielle Methoden für diese Art von Sprachelement.</span><span class="sxs-lookup"><span data-stu-id="8bed6-133">Each type has specific methods for that type of language element.</span></span> <span data-ttu-id="8bed6-134">Es ist viel, was Sie sich gleichzeitig merken müssen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-134">It's a lot to keep in your head at one time.</span></span> <span data-ttu-id="8bed6-135">Anstatt sich alles zu merken, finden Sie hier die Techniken, die ich zum Arbeiten mit Ausdrucksbaumstrukturen verwende:</span><span class="sxs-lookup"><span data-stu-id="8bed6-135">Rather than try to memorize everything, here are the techniques I use to work with Expression trees:</span></span>

1. <span data-ttu-id="8bed6-136">Betrachten Sie die Member des `ExpressionType`-enum, um mögliche Knoten zu bestimmen, die Sie untersuchen sollten.</span><span class="sxs-lookup"><span data-stu-id="8bed6-136">Look at the members of the `ExpressionType` enum to determine possible nodes you should be examining.</span></span> <span data-ttu-id="8bed6-137">Dies ist wirklich hilfreich, wenn Sie eine Ausdrucksbaumstruktur durchlaufen und verstehen möchten.</span><span class="sxs-lookup"><span data-stu-id="8bed6-137">This really helps when you want to traverse and understand an expression tree.</span></span>
2. <span data-ttu-id="8bed6-138">Betrachten Sie die statischen Member der `Expression`-Klasse, um einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-138">Look at the static members of the `Expression` class to build an expression.</span></span> <span data-ttu-id="8bed6-139">Diese Methoden können jeden Ausdruckstyp aus einer Reihe von untergeordneten Knoten erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-139">Those methods can build any expression type from a set of its child nodes.</span></span>
3. <span data-ttu-id="8bed6-140">Sehen Sie sich die `ExpressionVisitor`-Klasse an, um eine geänderte Ausdrucksbaumstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-140">Look at the `ExpressionVisitor` class to build a modified expression tree.</span></span>

<span data-ttu-id="8bed6-141">Sie werden mehr finden, wenn Sie sich jeden dieser drei Bereiche ansehen.</span><span class="sxs-lookup"><span data-stu-id="8bed6-141">You'll find more as you look at each of those three areas.</span></span> <span data-ttu-id="8bed6-142">Unweigerlich, werden Sie feststellen, was Sie benötigen, wenn Sie mit einem dieser drei Schritte starten.</span><span class="sxs-lookup"><span data-stu-id="8bed6-142">Invariably, you will find what you need when you start with one of those three steps.</span></span>

 [<span data-ttu-id="8bed6-143">Weiter -- Ausführen von Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="8bed6-143">Next -- Executing Expression Trees</span></span>](expression-trees-execution.md)

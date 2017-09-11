---
title: "Lokale Funktionen im Vergleich zu Lambdaausdrücken"
description: "Erfahren Sie, warum lokale Funktionen unter Umständen besser geeignet sind als Lambdaausdrücke."
keywords: "C#, .NET, .NET Core, neueste Funktionen, Neuigkeiten, lokale Funktionen, Lambdaausdrücke"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 0730e7b7d6e3ef7b5c534d16baacde6a7dafacfc
ms.contentlocale: de-de
ms.lasthandoff: 08/25/2017

---
# <a name="local-functions-compared-to-lambda-expressions"></a><span data-ttu-id="2270d-104">Lokale Funktionen im Vergleich zu Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="2270d-104">Local functions compared to Lambda expressions</span></span>

<span data-ttu-id="2270d-105">Auf den ersten Blick sind [lokale Funktionen](programming-guide/classes-and-structs/local-functions.md) und [Lambdaausdrücke](lambda-expressions.md) sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="2270d-105">At first glance, [local functions](programming-guide/classes-and-structs/local-functions.md) and [lambda expressions](lambda-expressions.md) are very similar.</span></span>
<span data-ttu-id="2270d-106">Je nach Ihren Anforderungen sind lokale Funktionen möglicherweise aber eine viel bessere und einfachere Lösung.</span><span class="sxs-lookup"><span data-stu-id="2270d-106">Depending on your needs, local functions may be a much better and simpler solution.</span></span>

<span data-ttu-id="2270d-107">Sehen wir uns die Unterschiede zwischen der Implementierungen des Fakultätsalgorithmus als lokale Funktion und als Lambdaausdruck an.</span><span class="sxs-lookup"><span data-stu-id="2270d-107">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="2270d-108">Erste die Version mit einer lokalen Funktion:</span><span class="sxs-lookup"><span data-stu-id="2270d-108">First the version using a local function:</span></span>

<span data-ttu-id="2270d-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Rekursive Fakultät mit lokaler Funktion")]</span><span class="sxs-lookup"><span data-stu-id="2270d-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]</span></span>

<span data-ttu-id="2270d-110">Vergleichen Sie diese Implementierung mit einer Version, die Lambdaausdrücke verwendet:</span><span class="sxs-lookup"><span data-stu-id="2270d-110">Contrast that implementation with a version that uses lambda expressions:</span></span>

<span data-ttu-id="2270d-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Rekursive Fakultät mit Lambdaausdrücken")]</span><span class="sxs-lookup"><span data-stu-id="2270d-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]</span></span>

<span data-ttu-id="2270d-112">Zuerst werden Lambdaausdrücke durch das Instanziieren und Abrufen eines Delegats implementiert.</span><span class="sxs-lookup"><span data-stu-id="2270d-112">First, lambda expressions are implemented by instantiating a delegate and invoking that delegate.</span></span> <span data-ttu-id="2270d-113">Lokale Funktionen werden als Methodenaufrufe implementiert.</span><span class="sxs-lookup"><span data-stu-id="2270d-113">Local functions are implemented as method calls.</span></span>
<span data-ttu-id="2270d-114">Die für Lambdaausdrücke erforderliche Instanziierung bedeutet zusätzliche Speicherbelegung, was ein Leistungsfaktor in zeitkritischen Codepfaden sein kann.</span><span class="sxs-lookup"><span data-stu-id="2270d-114">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time critical code paths.</span></span>
<span data-ttu-id="2270d-115">Lokale Funktionen erfordern diesen Mehraufwand nicht.</span><span class="sxs-lookup"><span data-stu-id="2270d-115">Local functions do not incur this overhead.</span></span> <span data-ttu-id="2270d-116">Im obigen Beispiel hat die Version mit der lokalen Funktion zwei Zuordnungen weniger als die Version mit dem Lambdaausdruck.</span><span class="sxs-lookup"><span data-stu-id="2270d-116">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

<span data-ttu-id="2270d-117">Diese rekursive Methode ist einfach genug, dass die lokale Funktion als private Methode mit einem vom Compiler generierten Namen implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="2270d-117">This recursive method is simple enough that the local function is implemented as a private method with a compiler generated name.</span></span> <span data-ttu-id="2270d-118">Der einzige Unterschied zu anderen privaten Methoden ist, dass sie semantisch innerhalb der äußeren Funktion begrenzt ist.</span><span class="sxs-lookup"><span data-stu-id="2270d-118">Its only difference from other private methods is that it is semantically scoped inside the outer function.</span></span>

<span data-ttu-id="2270d-119">Zweitens können lokale Funktionen aufgerufen werden, bevor sie definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2270d-119">Second, local functions can be called before they are defined.</span></span> <span data-ttu-id="2270d-120">Lambdaausdrücke müssen deklariert werden, bevor sie definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2270d-120">Lambda expressions must be declared before they are defined.</span></span> <span data-ttu-id="2270d-121">Dies bedeutet, dass lokale Funktionen wie oben dargestellt einfacher in rekursiven Algorithmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2270d-121">This means local functions are easier to use in recursive algorithms, as shown above.</span></span>

<span data-ttu-id="2270d-122">Beachten Sie, dass die Version mit Lambdaausdrücken den Lambdaausdruck `nthFactorial` deklarieren und initialisieren muss, bevor er definiert wird.</span><span class="sxs-lookup"><span data-stu-id="2270d-122">Notice that the version using the lambda expression must declare and initialize the lambda expression, `nthFactorial` before defining it.</span></span> <span data-ttu-id="2270d-123">Wird das nicht gemacht, führt dies zu einem Kompilierzeitfehler, weil auf `nthFactorial` verwiesen wurde, bevor es zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2270d-123">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>
<span data-ttu-id="2270d-124">Rekursiver Algorithmen sind einfacher mit lokalen Funktion zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2270d-124">Recursive algorithms are easier to create using local functions.</span></span>

<span data-ttu-id="2270d-125">Drittens muss der Compiler für Lambdaausdrücke zunächst immer eine anonyme Klasse und eine Instanz dieser Klasse erstellen, um alle Variablen zu speichern, die vom Abschluss erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="2270d-125">Third, for lambda expressions, the compiler must always create an anonymous class and an instance of that class to store any variables captured by the closure.</span></span> <span data-ttu-id="2270d-126">Betrachten Sie das folgende asynchrone Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2270d-126">Consider this async example:</span></span>

<span data-ttu-id="2270d-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Methode mit Lambdaausdruck, die Aufgabe zurückgibt")]</span><span class="sxs-lookup"><span data-stu-id="2270d-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]</span></span>

<span data-ttu-id="2270d-128">Der Abschluss dieses Lambdaausdrucks enthält die Variablen `address`, `index` und `name`.</span><span class="sxs-lookup"><span data-stu-id="2270d-128">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="2270d-129">Im Fall von lokalen Funktionen ist das Objekt, das den Abschluss implementiert, möglicherweise vom Typ `struct`.</span><span class="sxs-lookup"><span data-stu-id="2270d-129">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="2270d-130">Dadurch würde bei einer Zuweisung gespart.</span><span class="sxs-lookup"><span data-stu-id="2270d-130">That would save on an allocation.</span></span>

> [!NOTE]
> <span data-ttu-id="2270d-131">Die Entsprechung dieser Methode mit der lokalen Funktion verwendet auch eine Klasse für den Abschluss.</span><span class="sxs-lookup"><span data-stu-id="2270d-131">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="2270d-132">Ob der Abschluss für eine lokale Funktion als `class` oder `struct` implementiert wird, ist ein Implementierungsdetail.</span><span class="sxs-lookup"><span data-stu-id="2270d-132">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="2270d-133">Eine lokale Funktion verwendet möglicherweise `struct`, während ein Lambdaausdruck immer `class` nutzt.</span><span class="sxs-lookup"><span data-stu-id="2270d-133">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

<span data-ttu-id="2270d-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Aufgabenrückgabemethode mit lokaler Funktion ")]</span><span class="sxs-lookup"><span data-stu-id="2270d-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]</span></span>

<span data-ttu-id="2270d-135">Eine letzter Vorteil, der in diesem Beispiel zu kurz gekommen ist, besteht darin, dass lokale Funktionen mithilfe der `yield return`-Syntax als Iteratoren implementiert werden können, um eine Sequenz von Werten zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="2270d-135">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span>

<span data-ttu-id="2270d-136">Während lokale Funktionen für Lambdaausdrücke als überflüssig erscheinen, dienen sie tatsächlich anderen Zwecken und haben unterschiedliche Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="2270d-136">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span>
<span data-ttu-id="2270d-137">Lokale Funktionen sind effizienter, im Fall dass Sie eine Funktion schreiben möchten, die nur aus dem Kontext einer anderen Methode abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2270d-137">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>


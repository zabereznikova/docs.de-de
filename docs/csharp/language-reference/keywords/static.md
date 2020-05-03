---
title: static-Modifizierer – C#-Referenz
ms.date: 04/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 771bcfdac4c4bf27c15da4bc374d804405317a78
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102059"
---
# <a name="static-c-reference"></a><span data-ttu-id="b51e2-102">static (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b51e2-102">static (C# Reference)</span></span>

<span data-ttu-id="b51e2-103">Auf dieser Seite wird das Modifiziererschlüsselwort `static` behandelt.</span><span class="sxs-lookup"><span data-stu-id="b51e2-103">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="b51e2-104">Das Schlüsselwort `static` ist auch Teil der [`using static`](using-static.md)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b51e2-104">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="b51e2-105">Verwenden Sie den Modifizierer `static`, um einen statischen Member zu deklarieren, der zum Typ selbst gehört, anstatt zu einem bestimmten Objekt.</span><span class="sxs-lookup"><span data-stu-id="b51e2-105">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="b51e2-106">Der `static`-Modifizierer kann zum Deklarieren von `static`-Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b51e2-106">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="b51e2-107">In Klassen, Schnittstellen und Strukturen können Sie den Modifizierer `static` zu Feldern, Methoden, Eigenschaften, Operatoren, Ereignissen und Konstruktoren hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b51e2-107">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="b51e2-108">Der `static`-Modifizierer kann nicht mit Indexern oder Finalizern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b51e2-108">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="b51e2-109">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="b51e2-109">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example---static-class"></a><span data-ttu-id="b51e2-110">Beispiel: statische Klasse</span><span class="sxs-lookup"><span data-stu-id="b51e2-110">Example - static class</span></span>

<span data-ttu-id="b51e2-111">Die folgende Klasse wird als `static` deklariert und enthält nur `static`-Methoden:</span><span class="sxs-lookup"><span data-stu-id="b51e2-111">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="b51e2-112">Eine Konstante oder Typdeklaration ist implizit ein `static`-Member.</span><span class="sxs-lookup"><span data-stu-id="b51e2-112">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="b51e2-113">Ein `static`-Member kann nicht über eine Instanz verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b51e2-113">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="b51e2-114">Stattdessen wird er über den Typnamen verwiesen.</span><span class="sxs-lookup"><span data-stu-id="b51e2-114">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="b51e2-115">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="b51e2-115">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="b51e2-116">Verwenden Sie zum Verweisen auf einen `static`-Member `x` den vollqualifizierten Namen `MyBaseC.MyStruct.x`, außer es kann auf den Member vom selben Geltungsbereich zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="b51e2-116">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="b51e2-117">Während die Instanz einer Klasse eine separate Kopie aller Instanzfelder der Klasse enthält, gibt es nur eine Kopie von jedem `static`-Feld.</span><span class="sxs-lookup"><span data-stu-id="b51e2-117">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="b51e2-118">Es ist nicht möglich, [`this`](this.md) zum Verweis auf `static`-Methoden oder Eigenschaftenaccessoren zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b51e2-118">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="b51e2-119">Wenn das Schlüsselwort `static` auf eine Klasse angewandt wird, müssen alle Member der Klasse `static` sein.</span><span class="sxs-lookup"><span data-stu-id="b51e2-119">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="b51e2-120">Klassen, Schnittstellen und `static`-Klassen können `static`-Konstruktoren haben.</span><span class="sxs-lookup"><span data-stu-id="b51e2-120">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="b51e2-121">Ein `static`-Konstruktor wird irgendwann zwischen Programmstart und Klasseninstanziierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b51e2-121">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="b51e2-122">Die Verwendung des Schlüsselworts `static` ist in C# eingeschränkter als in C++.</span><span class="sxs-lookup"><span data-stu-id="b51e2-122">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="b51e2-123">Vergleiche mit dem C++-Schlüsselwort finden Sie unter [Speicherklassen (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="b51e2-123">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="b51e2-124">Stellen Sie sich zur Veranschaulichung von `static`-Membern eine Klasse vor, die einen Angestellten eines Unternehmens darstellt.</span><span class="sxs-lookup"><span data-stu-id="b51e2-124">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="b51e2-125">Es wird angenommen, dass die Klasse eine Methode zum Zählen von Angestellten sowie ein Feld enthält, in dem die Anzahl von Angestellten gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b51e2-125">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="b51e2-126">Sowohl die Methode als auch das Feld gehören nicht zu einer Instanz eines Angestellten.</span><span class="sxs-lookup"><span data-stu-id="b51e2-126">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="b51e2-127">Stattdessen gehören diese zur Klasse der Angestellten als Ganzes.</span><span class="sxs-lookup"><span data-stu-id="b51e2-127">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="b51e2-128">Diese sollten als `static`-Member der Klasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="b51e2-128">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="b51e2-129">Beispiel: statisches Feld und statische Methode</span><span class="sxs-lookup"><span data-stu-id="b51e2-129">Example - static field and method</span></span>

<span data-ttu-id="b51e2-130">In diesem Beispiel wird der Name und die ID eines neuen Angestellten gelesen, der Angestelltenzähler wird um 1 erhöht, und die Informationen zum neuen Angestellten sowie die neue Anzahl von Angestellten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b51e2-130">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="b51e2-131">Das Programm liest die aktuelle Anzahl von Angestellten von der Tastatur.</span><span class="sxs-lookup"><span data-stu-id="b51e2-131">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="b51e2-132">Beispiel: statische Initialisierung</span><span class="sxs-lookup"><span data-stu-id="b51e2-132">Example - static initialization</span></span>

<span data-ttu-id="b51e2-133">Dieses Beispiel zeigt, dass Sie ein `static`-Feld durch Verwendung eines anderen `static`-Felds initialisieren können, das noch nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="b51e2-133">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="b51e2-134">Die Ergebnisse sind undefiniert, bis Sie dem Feld `static` explizit einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b51e2-134">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="b51e2-135">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b51e2-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b51e2-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b51e2-136">See also</span></span>

- [<span data-ttu-id="b51e2-137">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b51e2-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b51e2-138">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b51e2-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b51e2-139">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b51e2-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b51e2-140">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="b51e2-140">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b51e2-141">using static-Direktive</span><span class="sxs-lookup"><span data-stu-id="b51e2-141">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="b51e2-142">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="b51e2-142">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

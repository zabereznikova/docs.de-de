---
description: static-Modifizierer – C#-Referenz
title: static-Modifizierer – C#-Referenz
ms.date: 09/25/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 239163fc2f91ccbfe8b1c111a358db87d36a8308
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654638"
---
# <a name="static-c-reference"></a><span data-ttu-id="60571-103">static (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="60571-103">static (C# Reference)</span></span>

<span data-ttu-id="60571-104">Auf dieser Seite wird das Modifiziererschlüsselwort `static` behandelt.</span><span class="sxs-lookup"><span data-stu-id="60571-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="60571-105">Das Schlüsselwort `static` ist auch Teil der [`using static`](using-static.md)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="60571-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="60571-106">Verwenden Sie den Modifizierer `static`, um einen statischen Member zu deklarieren, der zum Typ selbst gehört, anstatt zu einem bestimmten Objekt.</span><span class="sxs-lookup"><span data-stu-id="60571-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="60571-107">Der `static`-Modifizierer kann zum Deklarieren von `static`-Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60571-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="60571-108">In Klassen, Schnittstellen und Strukturen können Sie den Modifizierer `static` zu Feldern, Methoden, Eigenschaften, Operatoren, Ereignissen und Konstruktoren hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60571-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="60571-109">Der `static`-Modifizierer kann nicht mit Indexern oder Finalizern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60571-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="60571-110">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="60571-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

<span data-ttu-id="60571-111">Ab C# 8.0 können Sie den `static`-Modifizierer zu einer [lokalen Funktion](../../programming-guide/classes-and-structs/local-functions.md) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60571-111">Beginning with C# 8.0, you can add the `static` modifier to a [local function](../../programming-guide/classes-and-structs/local-functions.md).</span></span> <span data-ttu-id="60571-112">Eine statische lokale Funktion kann keine lokalen Variablen oder den Instanzzustand erfassen.</span><span class="sxs-lookup"><span data-stu-id="60571-112">A static local function can't capture local variables or instance state.</span></span>

<span data-ttu-id="60571-113">Ab C# 9.0 können Sie [Lambdaausdrücken](../operators/lambda-expressions.md) oder [anonymen Methoden](../operators/delegate-operator.md) den `static`-Modifizierer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60571-113">Beginning with C# 9.0, you can add the `static` modifier to a [lambda expression](../operators/lambda-expressions.md) or [anonymous method](../operators/delegate-operator.md).</span></span> <span data-ttu-id="60571-114">Eine statische Lambda- oder anonyme Methode kann keine lokalen Variablen bzw. keinen Instanzzustand erfassen.</span><span class="sxs-lookup"><span data-stu-id="60571-114">A static lambda or anonymous method can't capture local variables or instance state.</span></span>

## <a name="example---static-class"></a><span data-ttu-id="60571-115">Beispiel: statische Klasse</span><span class="sxs-lookup"><span data-stu-id="60571-115">Example - static class</span></span>

<span data-ttu-id="60571-116">Die folgende Klasse wird als `static` deklariert und enthält nur `static`-Methoden:</span><span class="sxs-lookup"><span data-stu-id="60571-116">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="60571-117">Eine Konstante oder Typdeklaration ist implizit ein `static`-Member.</span><span class="sxs-lookup"><span data-stu-id="60571-117">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="60571-118">Ein `static`-Member kann nicht über eine Instanz verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="60571-118">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="60571-119">Stattdessen wird er über den Typnamen verwiesen.</span><span class="sxs-lookup"><span data-stu-id="60571-119">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="60571-120">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="60571-120">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="60571-121">Verwenden Sie zum Verweisen auf einen `static`-Member `x` den vollqualifizierten Namen `MyBaseC.MyStruct.x`, außer es kann auf den Member vom selben Geltungsbereich zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="60571-121">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="60571-122">Während die Instanz einer Klasse eine separate Kopie aller Instanzfelder der Klasse enthält, gibt es nur eine Kopie von jedem `static`-Feld.</span><span class="sxs-lookup"><span data-stu-id="60571-122">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="60571-123">Es ist nicht möglich, [`this`](this.md) zum Verweis auf `static`-Methoden oder Eigenschaftenaccessoren zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="60571-123">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="60571-124">Wenn das Schlüsselwort `static` auf eine Klasse angewandt wird, müssen alle Member der Klasse `static` sein.</span><span class="sxs-lookup"><span data-stu-id="60571-124">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="60571-125">Klassen, Schnittstellen und `static`-Klassen können `static`-Konstruktoren haben.</span><span class="sxs-lookup"><span data-stu-id="60571-125">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="60571-126">Ein `static`-Konstruktor wird irgendwann zwischen Programmstart und Klasseninstanziierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="60571-126">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="60571-127">Die Verwendung des Schlüsselworts `static` ist in C# eingeschränkter als in C++.</span><span class="sxs-lookup"><span data-stu-id="60571-127">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="60571-128">Vergleiche mit dem C++-Schlüsselwort finden Sie unter [Speicherklassen (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="60571-128">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="60571-129">Stellen Sie sich zur Veranschaulichung von `static`-Membern eine Klasse vor, die einen Angestellten eines Unternehmens darstellt.</span><span class="sxs-lookup"><span data-stu-id="60571-129">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="60571-130">Es wird angenommen, dass die Klasse eine Methode zum Zählen von Angestellten sowie ein Feld enthält, in dem die Anzahl von Angestellten gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="60571-130">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="60571-131">Sowohl die Methode als auch das Feld gehören nicht zu einer Instanz eines Angestellten.</span><span class="sxs-lookup"><span data-stu-id="60571-131">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="60571-132">Stattdessen gehören diese zur Klasse der Angestellten als Ganzes.</span><span class="sxs-lookup"><span data-stu-id="60571-132">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="60571-133">Diese sollten als `static`-Member der Klasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="60571-133">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="60571-134">Beispiel: statisches Feld und statische Methode</span><span class="sxs-lookup"><span data-stu-id="60571-134">Example - static field and method</span></span>

<span data-ttu-id="60571-135">In diesem Beispiel wird der Name und die ID eines neuen Angestellten gelesen, der Angestelltenzähler wird um 1 erhöht, und die Informationen zum neuen Angestellten sowie die neue Anzahl von Angestellten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60571-135">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="60571-136">Das Programm liest die aktuelle Anzahl von Angestellten von der Tastatur.</span><span class="sxs-lookup"><span data-stu-id="60571-136">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="60571-137">Beispiel: statische Initialisierung</span><span class="sxs-lookup"><span data-stu-id="60571-137">Example - static initialization</span></span>

<span data-ttu-id="60571-138">Dieses Beispiel zeigt, dass Sie ein `static`-Feld durch Verwendung eines anderen `static`-Felds initialisieren können, das noch nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="60571-138">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="60571-139">Die Ergebnisse sind undefiniert, bis Sie dem Feld `static` explizit einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="60571-139">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="60571-140">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="60571-140">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="60571-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60571-141">See also</span></span>

- [<span data-ttu-id="60571-142">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="60571-142">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="60571-143">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="60571-143">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="60571-144">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="60571-144">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="60571-145">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="60571-145">Modifiers</span></span>](index.md)
- [<span data-ttu-id="60571-146">using static-Direktive</span><span class="sxs-lookup"><span data-stu-id="60571-146">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="60571-147">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="60571-147">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

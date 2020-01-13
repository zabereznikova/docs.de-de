---
title: static-Modifizierer – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: f4ca3fcf809e723d2144654f1da949eb4d6de1b4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713065"
---
# <a name="static-c-reference"></a><span data-ttu-id="b0b44-102">static (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b0b44-102">static (C# Reference)</span></span>

<span data-ttu-id="b0b44-103">Verwenden Sie den Modifizierer `static`, um einen statischen Member zu deklarieren, der zum Typ selbst gehört, anstatt zu einem bestimmten Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0b44-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="b0b44-104">Der Modifizierer `static` kann mit Klassen, Feldern, Methoden, Eigenschaften, Operatoren, Ereignissen und Konstruktoren verwendet werden, jedoch nicht mit Indexern, Finalizern oder Typen außer Klassen.</span><span class="sxs-lookup"><span data-stu-id="b0b44-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="b0b44-105">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="b0b44-105">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="b0b44-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0b44-106">Example</span></span>

<span data-ttu-id="b0b44-107">Die folgende Klasse wird als `static` deklariert und enthält nur `static`-Methoden:</span><span class="sxs-lookup"><span data-stu-id="b0b44-107">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="b0b44-108">Die Deklaration einer Konstante oder eines Typs ist implizit ein statischer Member.</span><span class="sxs-lookup"><span data-stu-id="b0b44-108">A constant or type declaration is implicitly a static member.</span></span>

<span data-ttu-id="b0b44-109">Ein statischer Member kann nicht über eine Instanz verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b0b44-109">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="b0b44-110">Stattdessen wird er über den Namen verwiesen.</span><span class="sxs-lookup"><span data-stu-id="b0b44-110">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="b0b44-111">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="b0b44-111">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="b0b44-112">Verwenden Sie zum Verweisen auf ein statischen Member `x` den vollqualifizierten Namen `MyBaseC.MyStruct.x`, außer es kann auf den Member vom selben Geltungsbereich zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="b0b44-112">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="b0b44-113">Während die Instanz einer Klasse eine separate Kopie aller Instanzfelder der Klasse enthält, gibt es nur eine Kopie von jedem statischen Feld.</span><span class="sxs-lookup"><span data-stu-id="b0b44-113">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>

<span data-ttu-id="b0b44-114">Es ist nicht möglich, [this](this.md) zum Verweis auf statische Methoden oder Eigenschaftenaccessoren zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0b44-114">It is not possible to use [this](this.md) to reference static methods or property accessors.</span></span>

<span data-ttu-id="b0b44-115">Wenn das Schlüsselwort `static` auf eine Klasse angewandt wird, müssen alle Member der Klasse statisch sein.</span><span class="sxs-lookup"><span data-stu-id="b0b44-115">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>

<span data-ttu-id="b0b44-116">Klassen und statische Klassen können über statische Konstruktoren verfügen.</span><span class="sxs-lookup"><span data-stu-id="b0b44-116">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="b0b44-117">Statische Konstruktoren werden irgendwann zwischen Programmstart und Klasseninstanziierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b0b44-117">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="b0b44-118">Die Verwendung des Schlüsselworts `static` ist in C# eingeschränkter als in C++.</span><span class="sxs-lookup"><span data-stu-id="b0b44-118">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="b0b44-119">Vergleiche mit dem C++-Schlüsselwort finden Sie unter [Speicherklassen (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="b0b44-119">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="b0b44-120">Stellen Sie sich zur Veranschaulichung von statischen Membern eine Klasse vor, die einen Angestellten eines Unternehmens darstellt.</span><span class="sxs-lookup"><span data-stu-id="b0b44-120">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="b0b44-121">Es wird angenommen, dass die Klasse eine Methode zum Zählen von Angestellten sowie ein Feld enthält, in dem die Anzahl von Angestellten gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b0b44-121">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="b0b44-122">Sowohl die Methode als auch das Feld gehören nicht zu einem Instanzangestellten.</span><span class="sxs-lookup"><span data-stu-id="b0b44-122">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="b0b44-123">Sie gehören stattdessen zur Unternehmensklasse.</span><span class="sxs-lookup"><span data-stu-id="b0b44-123">Instead they belong to the company class.</span></span> <span data-ttu-id="b0b44-124">Daher sollten sie als statische Member der Klasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="b0b44-124">Therefore, they should be declared as static members of the class.</span></span>

## <a name="example"></a><span data-ttu-id="b0b44-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0b44-125">Example</span></span>

<span data-ttu-id="b0b44-126">In diesem Beispiel wird der Name und die ID eines neuen Angestellten gelesen, der Angestelltenzähler wird um 1 erhöht, und die Informationen zum neuen Angestellten sowie die neue Anzahl von Angestellten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0b44-126">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="b0b44-127">Der Einfachheit halber liest das Programm die aktuelle Anzahl von Angestellten von der Tastatur.</span><span class="sxs-lookup"><span data-stu-id="b0b44-127">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="b0b44-128">Bei einer realen Anwendung sollten diese Informationen aus einer Datei gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="b0b44-128">In a real application, this information should be read from a file.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a><span data-ttu-id="b0b44-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0b44-129">Example</span></span>

<span data-ttu-id="b0b44-130">Dieses Beispiel zeigt, dass, obwohl Sie ein statisches Feld mit einem anderen noch nicht deklarierte, statischen Feld initialisieren können, die Ergebnisse undefiniert bleiben, bis Sie dem statischen Feld explizit einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b0b44-130">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="b0b44-131">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b0b44-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b0b44-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0b44-132">See also</span></span>

- [<span data-ttu-id="b0b44-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b0b44-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b0b44-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b0b44-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b0b44-135">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b0b44-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b0b44-136">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="b0b44-136">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b0b44-137">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="b0b44-137">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

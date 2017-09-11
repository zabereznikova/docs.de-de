---
title: static (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- static
- static_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8e46dc2f00d1c185379dba1017ca445b9ae5ae72
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="static-c-reference"></a><span data-ttu-id="fc5af-102">static (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fc5af-102">static (C# Reference)</span></span>
<span data-ttu-id="fc5af-103">Verwenden Sie den Modifizierer `static`, um einen statischen Member zu deklarieren, der zum Typ selbst gehört, anstatt zu einem bestimmten Objekt.</span><span class="sxs-lookup"><span data-stu-id="fc5af-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="fc5af-104">Der Modifizierer `static` kann mit Klassen, Feldern, Methoden, Eigenschaften, Operatoren, Ereignissen und Konstruktoren verwendet werden, jedoch nicht mit Indexern, Finalizern oder Typen außer Klassen.</span><span class="sxs-lookup"><span data-stu-id="fc5af-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="fc5af-105">Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="fc5af-105">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc5af-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc5af-106">Example</span></span>  
 <span data-ttu-id="fc5af-107">Die folgende Klasse wird als `static` deklariert und enthält nur `static`-Methoden:</span><span class="sxs-lookup"><span data-stu-id="fc5af-107">The following class is declared as `static` and contains only `static` methods:</span></span>  
  
 <span data-ttu-id="fc5af-108">[!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc5af-108">[!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]</span></span>  
  
 <span data-ttu-id="fc5af-109">Die Deklaration einer Konstante oder eines Typs ist implizit ein statischer Member.</span><span class="sxs-lookup"><span data-stu-id="fc5af-109">A constant or type declaration is implicitly a static member.</span></span>  
  
 <span data-ttu-id="fc5af-110">Ein statischer Member kann nicht über eine Instanz verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="fc5af-110">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="fc5af-111">Stattdessen wird er über den Namen verwiesen.</span><span class="sxs-lookup"><span data-stu-id="fc5af-111">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="fc5af-112">Betrachten Sie beispielsweise die folgende Klasse:</span><span class="sxs-lookup"><span data-stu-id="fc5af-112">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="fc5af-113">[!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc5af-113">[!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]</span></span>  
  
 <span data-ttu-id="fc5af-114">Verwenden Sie zum Verweisen auf ein statischen Member `x` den vollqualifizierten Namen `MyBaseC.MyStruct.x`, außer es kann auf den Member vom selben Geltungsbereich zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="fc5af-114">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 <span data-ttu-id="fc5af-115">Während die Instanz einer Klasse eine separate Kopie aller Instanzfelder der Klasse enthält, gibt es nur eine Kopie von jedem statischen Feld.</span><span class="sxs-lookup"><span data-stu-id="fc5af-115">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>  
  
 <span data-ttu-id="fc5af-116">Es ist nicht möglich, [this](../../../csharp/language-reference/keywords/this.md) zum Verweis auf statische Methoden oder Eigenschaftenaccessoren zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc5af-116">It is not possible to use [this](../../../csharp/language-reference/keywords/this.md) to reference static methods or property accessors.</span></span>  
  
 <span data-ttu-id="fc5af-117">Wenn das Schlüsselwort `static` auf eine Klasse angewandt wird, müssen alle Member der Klasse statisch sein.</span><span class="sxs-lookup"><span data-stu-id="fc5af-117">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>  
  
 <span data-ttu-id="fc5af-118">Klassen und statische Klassen können über statische Konstruktoren verfügen.</span><span class="sxs-lookup"><span data-stu-id="fc5af-118">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="fc5af-119">Statische Konstruktoren werden irgendwann zwischen Programmstart und Klasseninstanziierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fc5af-119">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc5af-120">Die Verwendung des Schlüsselworts `static` ist in C# eingeschränkter als in C++.</span><span class="sxs-lookup"><span data-stu-id="fc5af-120">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="fc5af-121">Vergleiche mit dem C++-Schlüsselwort finden Sie unter [Speicherklassen (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="fc5af-121">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>
  
 <span data-ttu-id="fc5af-122">Stellen Sie sich zur Veranschaulichung von statischen Membern eine Klasse vor, die einen Angestellten eines Unternehmens darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc5af-122">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="fc5af-123">Es wird angenommen, dass die Klasse eine Methode zum Zählen von Angestellten sowie ein Feld enthält, in dem die Anzahl von Angestellten gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fc5af-123">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="fc5af-124">Sowohl die Methode als auch das Feld gehören nicht zu einem Instanzangestellten.</span><span class="sxs-lookup"><span data-stu-id="fc5af-124">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="fc5af-125">Sie gehören stattdessen zur Unternehmensklasse.</span><span class="sxs-lookup"><span data-stu-id="fc5af-125">Instead they belong to the company class.</span></span> <span data-ttu-id="fc5af-126">Daher sollten sie als statische Member der Klasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="fc5af-126">Therefore, they should be declared as static members of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc5af-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc5af-127">Example</span></span>  
 <span data-ttu-id="fc5af-128">In diesem Beispiel wird der Name und die ID eines neuen Angestellten gelesen, der Angestelltenzähler wird um 1 erhöht, und die Informationen zum neuen Angestellten sowie die neue Anzahl von Angestellten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc5af-128">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="fc5af-129">Der Einfachheit halber liest das Programm die aktuelle Anzahl von Angestellten von der Tastatur.</span><span class="sxs-lookup"><span data-stu-id="fc5af-129">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="fc5af-130">Bei einer realen Anwendung sollten diese Informationen aus einer Datei gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="fc5af-130">In a real application, this information should be read from a file.</span></span>  
  
 <span data-ttu-id="fc5af-131">[!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc5af-131">[!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc5af-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc5af-132">Example</span></span>  
 <span data-ttu-id="fc5af-133">Dieses Beispiel zeigt, dass, obwohl Sie ein statisches Feld mit einem anderen noch nicht deklarierte, statischen Feld initialisieren können, die Ergebnisse undefiniert bleiben, bis Sie dem statischen Feld explizit einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fc5af-133">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>  
  
 <span data-ttu-id="fc5af-134">[!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc5af-134">[!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fc5af-135">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="fc5af-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc5af-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc5af-136">See Also</span></span>  
 <span data-ttu-id="fc5af-137">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc5af-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fc5af-138">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc5af-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fc5af-139">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc5af-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="fc5af-140">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="fc5af-140">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="fc5af-141">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="fc5af-141">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)


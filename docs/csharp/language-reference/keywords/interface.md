---
title: interface (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 0320b1e287f8c7a3eb7751b68b40120f74e8f61c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="interface-c-reference"></a><span data-ttu-id="6f4fd-102">interface (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6f4fd-102">interface (C# Reference)</span></span>
<span data-ttu-id="6f4fd-103">Eine Schnittstelle enthält nur die Signaturen von [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md), [Ereignissen](../../../csharp/programming-guide/events/index.md) oder [Indexern](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f4fd-103">An interface contains only the signatures of [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [events](../../../csharp/programming-guide/events/index.md) or [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="6f4fd-104">Eine Klasse oder eine Struktur, die die Schnittstelle implementiert, muss die Member der Schnittstelle implementieren, die in der Schnittstellendefinition angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="6f4fd-105">Im folgenden Beispiel muss die Klasse `ImplementationClass` eine Methode mit dem Namen `SampleMethod` implementieren, die keine Parameter hat und `void` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>  
  
 <span data-ttu-id="6f4fd-106">Weitere Informationen und Beispiele finden Sie unter [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f4fd-106">For more information and examples, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f4fd-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f4fd-107">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
 <span data-ttu-id="6f4fd-108">Eine Schnittstelle kann ein Member eines Namespaces oder einer Klasse sein und Signaturen der folgenden Member enthalten:</span><span class="sxs-lookup"><span data-stu-id="6f4fd-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>  
  
-   [<span data-ttu-id="6f4fd-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="6f4fd-109">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="6f4fd-110">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6f4fd-110">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="6f4fd-111">Indexer</span><span class="sxs-lookup"><span data-stu-id="6f4fd-111">Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="6f4fd-112">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="6f4fd-112">Events</span></span>](../../../csharp/language-reference/keywords/event.md)  
  
 <span data-ttu-id="6f4fd-113">Eine Schnittstelle kann von einer oder mehreren Basisschnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-113">An interface can inherit from one or more base interfaces.</span></span>  
  
 <span data-ttu-id="6f4fd-114">Wenn eine Basistypliste sowohl eine Basisklasse als auch Schnittstellen umfasst, muss die Basisklasse zuerst in der Liste stehen.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>  
  
 <span data-ttu-id="6f4fd-115">Eine Klasse, die eine Schnittstelle implementiert, kann Member dieser Schnittstelle explizit implementieren.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="6f4fd-116">Auf einen explizit implementierten Member kann nicht durch eine Klasseninstanz zugegriffen werden, sondern nur durch eine Schnittstelleninstanz.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>  
  
 <span data-ttu-id="6f4fd-117">Weitere Details und Codebeispiele zur expliziten Schnittstellenimplementierung finden Sie unter [Explizite Schnittstellenimplementierung](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="6f4fd-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f4fd-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f4fd-118">Example</span></span>  
 <span data-ttu-id="6f4fd-119">Das folgende Beispiel veranschaulicht die Schnittstellenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="6f4fd-120">In diesem Beispiel enthält die Schnittstelle die Eigenschaftendeklaration, und die Klasse enthält die Implementierung.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="6f4fd-121">Eine beliebige Instanz einer Klasse, die `IPoint` implementiert, hat die ganzzahligen Eigenschaften `x` und `y`.</span><span class="sxs-lookup"><span data-stu-id="6f4fd-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6f4fd-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="6f4fd-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f4fd-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f4fd-123">See Also</span></span>  
 [<span data-ttu-id="6f4fd-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6f4fd-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6f4fd-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6f4fd-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6f4fd-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6f4fd-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6f4fd-127">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="6f4fd-127">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="6f4fd-128">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6f4fd-128">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="6f4fd-129">Verwenden von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6f4fd-129">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [<span data-ttu-id="6f4fd-130">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="6f4fd-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
 [<span data-ttu-id="6f4fd-131">class</span><span class="sxs-lookup"><span data-stu-id="6f4fd-131">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="6f4fd-132">struct</span><span class="sxs-lookup"><span data-stu-id="6f4fd-132">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
 [<span data-ttu-id="6f4fd-133">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6f4fd-133">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

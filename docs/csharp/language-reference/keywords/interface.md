---
title: interface (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- interface_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
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
ms.openlocfilehash: 126e674a2c56f04f54f35a011c24ebf0f713ee8d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="interface-c-reference"></a><span data-ttu-id="91b1c-102">interface (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="91b1c-102">interface (C# Reference)</span></span>
<span data-ttu-id="91b1c-103">Eine Schnittstelle enthält nur die Signaturen von [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md), [Ereignissen](../../../csharp/programming-guide/events/index.md) oder [Indexern](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="91b1c-103">An interface contains only the signatures of [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [events](../../../csharp/programming-guide/events/index.md) or [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="91b1c-104">Eine Klasse oder eine Struktur, die die Schnittstelle implementiert, muss die Member der Schnittstelle implementieren, die in der Schnittstellendefinition angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="91b1c-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="91b1c-105">Im folgenden Beispiel muss die Klasse `ImplementationClass` eine Methode mit dem Namen `SampleMethod` implementieren, die keine Parameter hat und `void` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="91b1c-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>  
  
 <span data-ttu-id="91b1c-106">Weitere Informationen und Beispiele finden Sie unter [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="91b1c-106">For more information and examples, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91b1c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91b1c-107">Example</span></span>  
 <span data-ttu-id="91b1c-108">[!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="91b1c-108">[!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]</span></span>  
  
 <span data-ttu-id="91b1c-109">Eine Schnittstelle kann ein Member eines Namespaces oder einer Klasse sein und Signaturen der folgenden Member enthalten:</span><span class="sxs-lookup"><span data-stu-id="91b1c-109">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>  
  
-   [<span data-ttu-id="91b1c-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="91b1c-110">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="91b1c-111">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="91b1c-111">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="91b1c-112">Indexer</span><span class="sxs-lookup"><span data-stu-id="91b1c-112">Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="91b1c-113">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="91b1c-113">Events</span></span>](../../../csharp/language-reference/keywords/event.md)  
  
 <span data-ttu-id="91b1c-114">Eine Schnittstelle kann von einer oder mehreren Basisschnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="91b1c-114">An interface can inherit from one or more base interfaces.</span></span>  
  
 <span data-ttu-id="91b1c-115">Wenn eine Basistypliste sowohl eine Basisklasse als auch Schnittstellen umfasst, muss die Basisklasse zuerst in der Liste stehen.</span><span class="sxs-lookup"><span data-stu-id="91b1c-115">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>  
  
 <span data-ttu-id="91b1c-116">Eine Klasse, die eine Schnittstelle implementiert, kann Member dieser Schnittstelle explizit implementieren.</span><span class="sxs-lookup"><span data-stu-id="91b1c-116">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="91b1c-117">Auf einen explizit implementierten Member kann nicht durch eine Klasseninstanz zugegriffen werden, sondern nur durch eine Schnittstelleninstanz.</span><span class="sxs-lookup"><span data-stu-id="91b1c-117">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>  
  
 <span data-ttu-id="91b1c-118">Weitere Details und Codebeispiele zur expliziten Schnittstellenimplementierung finden Sie unter [Explizite Schnittstellenimplementierung](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="91b1c-118">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91b1c-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91b1c-119">Example</span></span>  
 <span data-ttu-id="91b1c-120">Das folgende Beispiel veranschaulicht die Schnittstellenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="91b1c-120">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="91b1c-121">In diesem Beispiel enthält die Schnittstelle die Eigenschaftendeklaration, und die Klasse enthält die Implementierung.</span><span class="sxs-lookup"><span data-stu-id="91b1c-121">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="91b1c-122">Eine beliebige Instanz einer Klasse, die `IPoint` implementiert, hat die ganzzahligen Eigenschaften `x` und `y`.</span><span class="sxs-lookup"><span data-stu-id="91b1c-122">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>  
  
 <span data-ttu-id="91b1c-123">[!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="91b1c-123">[!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="91b1c-124">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="91b1c-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="91b1c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91b1c-125">See Also</span></span>  
 <span data-ttu-id="91b1c-126">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="91b1c-127">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="91b1c-128">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="91b1c-129">[Verweistypen](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-129">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="91b1c-130">[Schnittstellen](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-130">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="91b1c-131">[Verwenden von Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-131">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="91b1c-132">[Verwenden von Indexern](../../../csharp/programming-guide/indexers/using-indexers.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-132">[Using Indexers](../../../csharp/programming-guide/indexers/using-indexers.md) </span></span>  
 <span data-ttu-id="91b1c-133">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-133">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="91b1c-134">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="91b1c-134">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="91b1c-135">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91b1c-135">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)


---
title: Generische Typen und Attribute (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
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
ms.openlocfilehash: 5136ae928a3a4b6f8ec4d86100d695f958d55858
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="8796d-102">Generische Typen und Attribute (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8796d-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="8796d-103">Das Anwenden von Attributen auf generische Typen erfolgt in derselben Weise wie auf nicht generische Typen.</span><span class="sxs-lookup"><span data-stu-id="8796d-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="8796d-104">Weitere Informationen zum Anwenden von Attributen finden Sie unter [Attribute](../../../csharp/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="8796d-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="8796d-105">Benutzerdefinierte Attribute dürfen nur auf offene generische Typen (generische Typen, für die keine Typargumente bereitgestellt werden) und auf geschlossene konstruierte generische Typen (generische Typen, die Argumente für alle Typparameter bereitstellen) verweisen.</span><span class="sxs-lookup"><span data-stu-id="8796d-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="8796d-106">In den folgenden Beispielen wird dieses benutzerdefinierte Attribut verwendet:</span><span class="sxs-lookup"><span data-stu-id="8796d-106">The following examples use this custom attribute:</span></span>  
  
 <span data-ttu-id="8796d-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8796d-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span></span>  
  
 <span data-ttu-id="8796d-108">Ein Attribut kann auf einen offenen generischen Typ verweisen:</span><span class="sxs-lookup"><span data-stu-id="8796d-108">An attribute can reference an open generic type:</span></span>  
  
 <span data-ttu-id="8796d-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8796d-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span></span>  
  
 <span data-ttu-id="8796d-110">Geben Sie mehrere Typparameter mit der entsprechenden Anzahl von Kommas an.</span><span class="sxs-lookup"><span data-stu-id="8796d-110">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="8796d-111">In diesem Beispiel verfügt `GenericClass2` über zwei Typparameter:</span><span class="sxs-lookup"><span data-stu-id="8796d-111">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 <span data-ttu-id="8796d-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8796d-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span></span>  
  
 <span data-ttu-id="8796d-113">Ein Attribut kann auf einen geschlossenen, konstruierten generischen Typ verweisen:</span><span class="sxs-lookup"><span data-stu-id="8796d-113">An attribute can reference a closed constructed generic type:</span></span>  
  
 <span data-ttu-id="8796d-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="8796d-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span></span>  
  
 <span data-ttu-id="8796d-115">Ein Attribut, das auf einen generischen Typparameter verweist, verursacht einen Kompilierungsfehler:</span><span class="sxs-lookup"><span data-stu-id="8796d-115">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 <span data-ttu-id="8796d-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="8796d-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span></span>  
  
 <span data-ttu-id="8796d-117">Ein generischer Typ kann nicht von <xref:System.Attribute> erben:</span><span class="sxs-lookup"><span data-stu-id="8796d-117">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 <span data-ttu-id="8796d-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="8796d-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span></span>  
  
 <span data-ttu-id="8796d-119">Um zur Laufzeit Informationen zu einem generischen Typ oder Typparameter abzurufen, können Sie die Methoden von <xref:System.Reflection> verwenden.</span><span class="sxs-lookup"><span data-stu-id="8796d-119">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="8796d-120">Weitere Informationen finden Sie unter [Generische Typen und Reflektion](../../../csharp/programming-guide/generics/generics-and-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="8796d-120">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8796d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8796d-121">See Also</span></span>  
 <span data-ttu-id="8796d-122">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8796d-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8796d-123">[Generika](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="8796d-123">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 [<span data-ttu-id="8796d-124">Attribute</span><span class="sxs-lookup"><span data-stu-id="8796d-124">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)


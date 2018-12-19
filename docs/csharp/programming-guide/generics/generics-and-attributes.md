---
title: Generische Typen und Attribute – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 35244ce33902760c2a0d3d8bda3181097f7ca38e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245180"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="9a64a-102">Generische Typen und Attribute (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9a64a-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="9a64a-103">Das Anwenden von Attributen auf generische Typen erfolgt in derselben Weise wie auf nicht generische Typen.</span><span class="sxs-lookup"><span data-stu-id="9a64a-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="9a64a-104">Weitere Informationen zum Anwenden von Attributen finden Sie unter [Attribute](../../../csharp/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="9a64a-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="9a64a-105">Benutzerdefinierte Attribute dürfen nur auf offene generische Typen (generische Typen, für die keine Typargumente bereitgestellt werden) und auf geschlossene konstruierte generische Typen (generische Typen, die Argumente für alle Typparameter bereitstellen) verweisen.</span><span class="sxs-lookup"><span data-stu-id="9a64a-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="9a64a-106">In den folgenden Beispielen wird dieses benutzerdefinierte Attribut verwendet:</span><span class="sxs-lookup"><span data-stu-id="9a64a-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 <span data-ttu-id="9a64a-107">Ein Attribut kann auf einen offenen generischen Typ verweisen:</span><span class="sxs-lookup"><span data-stu-id="9a64a-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 <span data-ttu-id="9a64a-108">Geben Sie mehrere Typparameter mit der entsprechenden Anzahl von Kommas an.</span><span class="sxs-lookup"><span data-stu-id="9a64a-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="9a64a-109">In diesem Beispiel verfügt `GenericClass2` über zwei Typparameter:</span><span class="sxs-lookup"><span data-stu-id="9a64a-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 <span data-ttu-id="9a64a-110">Ein Attribut kann auf einen geschlossenen, konstruierten generischen Typ verweisen:</span><span class="sxs-lookup"><span data-stu-id="9a64a-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 <span data-ttu-id="9a64a-111">Ein Attribut, das auf einen generischen Typparameter verweist, verursacht einen Kompilierungsfehler:</span><span class="sxs-lookup"><span data-stu-id="9a64a-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 <span data-ttu-id="9a64a-112">Ein generischer Typ kann nicht von <xref:System.Attribute> erben:</span><span class="sxs-lookup"><span data-stu-id="9a64a-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 <span data-ttu-id="9a64a-113">Um zur Laufzeit Informationen zu einem generischen Typ oder Typparameter abzurufen, können Sie die Methoden von <xref:System.Reflection> verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a64a-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="9a64a-114">Weitere Informationen finden Sie unter [Generische Typen und Reflektion](../../../csharp/programming-guide/generics/generics-and-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="9a64a-114">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a64a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a64a-115">See Also</span></span>

- [<span data-ttu-id="9a64a-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9a64a-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9a64a-117">Generika</span><span class="sxs-lookup"><span data-stu-id="9a64a-117">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
- [<span data-ttu-id="9a64a-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="9a64a-118">Attributes</span></span>](../../../../docs/standard/attributes/index.md)

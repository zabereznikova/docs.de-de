---
title: Generics und Attribute – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 47bf4e8f07a8b6778db8fa675d745d362dc10d7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75703025"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="d4dc6-102">Generics und Attribute (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d4dc6-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="d4dc6-103">Das Anwenden von Attributen auf generische Typen erfolgt in derselben Weise wie auf nicht generische Typen.</span><span class="sxs-lookup"><span data-stu-id="d4dc6-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="d4dc6-104">Weitere Informationen zum Anwenden von Attributen finden Sie unter [Attribute](../concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="d4dc6-104">For more information on applying attributes, see [Attributes](../concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="d4dc6-105">Benutzerdefinierte Attribute dürfen nur auf offene generische Typen (generische Typen, für die keine Typargumente bereitgestellt werden) und auf geschlossene konstruierte generische Typen (generische Typen, die Argumente für alle Typparameter bereitstellen) verweisen.</span><span class="sxs-lookup"><span data-stu-id="d4dc6-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="d4dc6-106">In den folgenden Beispielen wird dieses benutzerdefinierte Attribut verwendet:</span><span class="sxs-lookup"><span data-stu-id="d4dc6-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="d4dc6-107">Ein Attribut kann auf einen offenen generischen Typ verweisen:</span><span class="sxs-lookup"><span data-stu-id="d4dc6-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="d4dc6-108">Geben Sie mehrere Typparameter mit der entsprechenden Anzahl von Kommas an.</span><span class="sxs-lookup"><span data-stu-id="d4dc6-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="d4dc6-109">In diesem Beispiel verfügt `GenericClass2` über zwei Typparameter:</span><span class="sxs-lookup"><span data-stu-id="d4dc6-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="d4dc6-110">Ein Attribut kann auf einen geschlossenen, konstruierten generischen Typ verweisen:</span><span class="sxs-lookup"><span data-stu-id="d4dc6-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="d4dc6-111">Ein Attribut, das auf einen generischen Typparameter verweist, verursacht einen Kompilierungsfehler:</span><span class="sxs-lookup"><span data-stu-id="d4dc6-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="d4dc6-112">Ein generischer Typ kann nicht von <xref:System.Attribute> erben:</span><span class="sxs-lookup"><span data-stu-id="d4dc6-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="d4dc6-113">Um zur Laufzeit Informationen zu einem generischen Typ oder Typparameter abzurufen, können Sie die Methoden von <xref:System.Reflection> verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4dc6-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="d4dc6-114">Weitere Informationen finden Sie unter [Generics und Reflektion](./generics-and-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="d4dc6-114">For more information, see [Generics and Reflection](./generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4dc6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4dc6-115">See also</span></span>

- [<span data-ttu-id="d4dc6-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d4dc6-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d4dc6-117">Generics</span><span class="sxs-lookup"><span data-stu-id="d4dc6-117">Generics</span></span>](./index.md)
- [<span data-ttu-id="d4dc6-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="d4dc6-118">Attributes</span></span>](../../../standard/attributes/index.md)

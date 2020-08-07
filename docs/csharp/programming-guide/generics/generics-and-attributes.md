---
title: Generics und Attribute – C#-Programmierhandbuch
description: Erfahren Sie mehr über das Anwenden von Attributen auf generische Typen. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 17556af2e1bc2963de953cea242d7000509acbcd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299876"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="3c9e6-104">Generics und Attribute (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3c9e6-104">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="3c9e6-105">Das Anwenden von Attributen auf generische Typen erfolgt in derselben Weise wie auf nicht generische Typen.</span><span class="sxs-lookup"><span data-stu-id="3c9e6-105">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="3c9e6-106">Weitere Informationen zum Anwenden von Attributen finden Sie unter [Attribute](../concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c9e6-106">For more information on applying attributes, see [Attributes](../concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="3c9e6-107">Benutzerdefinierte Attribute dürfen nur auf offene generische Typen (generische Typen, für die keine Typargumente bereitgestellt werden) und auf geschlossene konstruierte generische Typen (generische Typen, die Argumente für alle Typparameter bereitstellen) verweisen.</span><span class="sxs-lookup"><span data-stu-id="3c9e6-107">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="3c9e6-108">In den folgenden Beispielen wird dieses benutzerdefinierte Attribut verwendet:</span><span class="sxs-lookup"><span data-stu-id="3c9e6-108">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="3c9e6-109">Ein Attribut kann auf einen offenen generischen Typ verweisen:</span><span class="sxs-lookup"><span data-stu-id="3c9e6-109">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="3c9e6-110">Geben Sie mehrere Typparameter mit der entsprechenden Anzahl von Kommas an.</span><span class="sxs-lookup"><span data-stu-id="3c9e6-110">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="3c9e6-111">In diesem Beispiel verfügt `GenericClass2` über zwei Typparameter:</span><span class="sxs-lookup"><span data-stu-id="3c9e6-111">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="3c9e6-112">Ein Attribut kann auf einen geschlossenen, konstruierten generischen Typ verweisen:</span><span class="sxs-lookup"><span data-stu-id="3c9e6-112">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="3c9e6-113">Ein Attribut, das auf einen generischen Typparameter verweist, verursacht einen Kompilierungsfehler:</span><span class="sxs-lookup"><span data-stu-id="3c9e6-113">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="3c9e6-114">Ein generischer Typ kann nicht von <xref:System.Attribute> erben:</span><span class="sxs-lookup"><span data-stu-id="3c9e6-114">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="3c9e6-115">Um zur Laufzeit Informationen zu einem generischen Typ oder Typparameter abzurufen, können Sie die Methoden von <xref:System.Reflection> verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c9e6-115">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="3c9e6-116">Weitere Informationen finden Sie unter [Generics und Reflektion](./generics-and-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="3c9e6-116">For more information, see [Generics and Reflection](./generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9e6-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c9e6-117">See also</span></span>

- [<span data-ttu-id="3c9e6-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3c9e6-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3c9e6-119">Generics</span><span class="sxs-lookup"><span data-stu-id="3c9e6-119">Generics</span></span>](./index.md)
- [<span data-ttu-id="3c9e6-120">Attribute</span><span class="sxs-lookup"><span data-stu-id="3c9e6-120">Attributes</span></span>](../../../standard/attributes/index.md)

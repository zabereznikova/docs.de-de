---
title: Generische Delegaten – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: ff19b3d71858552158a8ae5d0ab362a86dc98e65
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423497"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="aa3e9-102">Generische Delegaten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="aa3e9-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="aa3e9-103">Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) kann seine eigenen Typparameter definieren.</span><span class="sxs-lookup"><span data-stu-id="aa3e9-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can define its own type parameters.</span></span> <span data-ttu-id="aa3e9-104">Wie im folgenden Beispiel gezeigt, kann Code, der auf den generischen Delegaten verweist, das Typargument zum Erstellen eines geschlossenen konstruierten Typs angeben, genau wie wenn eine generische Klasse instanziiert oder eine generische Methode aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="aa3e9-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="aa3e9-105">C# 2.0 verfügt über ein neues Feature. Dieses Feature wird als Methodengruppenkonvertierung bezeichnet und gilt sowohl für konkrete als auch für generische Delegattypen. Damit können Sie die vorhergehende Zeile mit folgender vereinfachter Syntax schreiben:</span><span class="sxs-lookup"><span data-stu-id="aa3e9-105">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="aa3e9-106">Delegaten, die innerhalb einer generischen Klasse definiert sind, können die Typparameter der generischen Klasse auf die gleiche Weise wie Klassenmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa3e9-106">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="aa3e9-107">Code, der auf den Delegaten verweist, muss das Typargument der enthaltenden Klasse wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="aa3e9-107">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="aa3e9-108">Generische Delegaten sind besonders nützlich zum Definieren von Ereignissen, die auf dem typischen Entwurfsmuster basieren, denn das Absenderargument kann mit starker Typisierung versehen werden und muss nicht länger in das bzw. aus dem <xref:System.Object> umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="aa3e9-108">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="aa3e9-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa3e9-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="aa3e9-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="aa3e9-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="aa3e9-111">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="aa3e9-111">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="aa3e9-112">Generische Methoden</span><span class="sxs-lookup"><span data-stu-id="aa3e9-112">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)
- [<span data-ttu-id="aa3e9-113">Generische Klassen</span><span class="sxs-lookup"><span data-stu-id="aa3e9-113">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)
- [<span data-ttu-id="aa3e9-114">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="aa3e9-114">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)
- [<span data-ttu-id="aa3e9-115">Delegaten</span><span class="sxs-lookup"><span data-stu-id="aa3e9-115">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="aa3e9-116">Generics</span><span class="sxs-lookup"><span data-stu-id="aa3e9-116">Generics</span></span>](~/docs/standard/generics/index.md)

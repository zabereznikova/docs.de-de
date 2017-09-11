---
title: Generische Delegaten (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: 16
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
ms.openlocfilehash: be067e2a2e2a192da8ccc92b60af81f0999c449a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="21d73-102">Generische Delegaten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="21d73-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="21d73-103">Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) kann seine eigenen Typparameter definieren.</span><span class="sxs-lookup"><span data-stu-id="21d73-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can define its own type parameters.</span></span> <span data-ttu-id="21d73-104">Wie im folgenden Beispiel gezeigt, kann Code, der auf den generischen Delegaten verweist, das Typargument zum Erstellen eines geschlossenen konstruierten Typs angeben, genau wie wenn eine generische Klasse instanziiert oder eine generische Methode aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="21d73-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 <span data-ttu-id="21d73-105">[!code-cs[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="21d73-105">[!code-cs[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]</span></span>  
  
 <span data-ttu-id="21d73-106">C# 2.0 verfügt über ein neues Feature. Dieses Feature wird als Methodengruppenkonvertierung bezeichnet und gilt sowohl für konkrete als auch für generische Delegattypen. Damit können Sie die vorhergehende Zeile mit folgender vereinfachter Syntax schreiben:</span><span class="sxs-lookup"><span data-stu-id="21d73-106">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 <span data-ttu-id="21d73-107">[!code-cs[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="21d73-107">[!code-cs[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]</span></span>  
  
 <span data-ttu-id="21d73-108">Delegaten, die innerhalb einer generischen Klasse definiert sind, können die Typparameter der generischen Klasse auf die gleiche Weise wie Klassenmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="21d73-108">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 <span data-ttu-id="21d73-109">[!code-cs[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="21d73-109">[!code-cs[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]</span></span>  
  
 <span data-ttu-id="21d73-110">Code, der auf den Delegaten verweist, muss das Typargument der enthaltenden Klasse wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="21d73-110">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 <span data-ttu-id="21d73-111">[!code-cs[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="21d73-111">[!code-cs[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]</span></span>  
  
 <span data-ttu-id="21d73-112">Generische Delegaten sind besonders nützlich zum Definieren von Ereignissen, die auf dem typischen Entwurfsmuster basieren, denn das Absenderargument kann mit starker Typisierung versehen werden und muss nicht länger in das bzw. aus dem <xref:System.Object> umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="21d73-112">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="21d73-113">[!code-cs[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="21d73-113">[!code-cs[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d73-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21d73-114">See Also</span></span>  
 <span data-ttu-id="21d73-115"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="21d73-115"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="21d73-116">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="21d73-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="21d73-117">[Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="21d73-117">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="21d73-118">[Generische Methoden](../../../csharp/programming-guide/generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="21d73-118">[Generic Methods](../../../csharp/programming-guide/generics/generic-methods.md) </span></span>  
 <span data-ttu-id="21d73-119">[Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md) </span><span class="sxs-lookup"><span data-stu-id="21d73-119">[Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md) </span></span>  
 <span data-ttu-id="21d73-120">[Generic Interfaces (Generische Schnittstellen)](../../../csharp/programming-guide/generics/generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="21d73-120">[Generic Interfaces](../../../csharp/programming-guide/generics/generic-interfaces.md) </span></span>  
 <span data-ttu-id="21d73-121">[Delegaten](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="21d73-121">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 [<span data-ttu-id="21d73-122">Generika</span><span class="sxs-lookup"><span data-stu-id="21d73-122">Generics</span></span>](~/docs/standard/generics/index.md)


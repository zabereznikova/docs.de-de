---
title: partial (Methode) (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 03962a59d5dbe0146cad9835f81d41c06914795b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="5b80f-102">partial (Methode) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5b80f-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="5b80f-103">Bei partiellen Methoden wird die Signatur in einem Teil eines partiellen Typs definiert, und die Implementierung wird in einem anderen Teil des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="5b80f-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="5b80f-104">Mit partiellen Methoden können Klassen-Designer Methoden-Hooks bereitstellen, die Ereignis-Handlern ähneln und die Entwickler ggf. implementieren können.</span><span class="sxs-lookup"><span data-stu-id="5b80f-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="5b80f-105">Wenn der Entwickler keine Implementierung angibt, entfernt der Compiler die Signatur bei der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="5b80f-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="5b80f-106">Die folgenden Bedingungen gelten für partielle Methoden:</span><span class="sxs-lookup"><span data-stu-id="5b80f-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="5b80f-107">Die Signaturen in beiden Teilen des partiellen Typs müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5b80f-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="5b80f-108">Die Methode muss "void" zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5b80f-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="5b80f-109">Es sind keine Zugriffsmodifizierer zulässig.</span><span class="sxs-lookup"><span data-stu-id="5b80f-109">No access modifiers are allowed.</span></span> <span data-ttu-id="5b80f-110">Partielle Methoden sind implizit privat.</span><span class="sxs-lookup"><span data-stu-id="5b80f-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="5b80f-111">Im folgenden Beispiel wird eine partielle Methode veranschaulicht, die in zwei Teilen einer partiellen Klasse definiert ist:</span><span class="sxs-lookup"><span data-stu-id="5b80f-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 <span data-ttu-id="5b80f-112">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5b80f-112">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b80f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b80f-113">See Also</span></span>  
 [<span data-ttu-id="5b80f-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5b80f-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5b80f-115">partial (Typ)</span><span class="sxs-lookup"><span data-stu-id="5b80f-115">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)

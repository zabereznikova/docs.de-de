---
title: partial (Methode) (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 29b5d442a1aa33babc24aee987e749c93a5ec727
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269040"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="cb999-102">partial (Methode) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cb999-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="cb999-103">Bei partiellen Methoden wird die Signatur in einem Teil eines partiellen Typs definiert, und die Implementierung wird in einem anderen Teil des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="cb999-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="cb999-104">Mit partiellen Methoden können Klassen-Designer Methoden-Hooks bereitstellen, die Ereignis-Handlern ähneln und die Entwickler ggf. implementieren können.</span><span class="sxs-lookup"><span data-stu-id="cb999-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="cb999-105">Wenn der Entwickler keine Implementierung angibt, entfernt der Compiler die Signatur bei der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="cb999-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="cb999-106">Die folgenden Bedingungen gelten für partielle Methoden:</span><span class="sxs-lookup"><span data-stu-id="cb999-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="cb999-107">Die Signaturen in beiden Teilen des partiellen Typs müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cb999-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="cb999-108">Die Methode muss "void" zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cb999-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="cb999-109">Es sind keine Zugriffsmodifizierer zulässig.</span><span class="sxs-lookup"><span data-stu-id="cb999-109">No access modifiers are allowed.</span></span> <span data-ttu-id="cb999-110">Partielle Methoden sind implizit privat.</span><span class="sxs-lookup"><span data-stu-id="cb999-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="cb999-111">Im folgenden Beispiel wird eine partielle Methode veranschaulicht, die in zwei Teilen einer partiellen Klasse definiert ist:</span><span class="sxs-lookup"><span data-stu-id="cb999-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 <span data-ttu-id="cb999-112">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="cb999-112">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb999-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb999-113">See Also</span></span>  
 [<span data-ttu-id="cb999-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cb999-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="cb999-115">partial (Typ)</span><span class="sxs-lookup"><span data-stu-id="cb999-115">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)

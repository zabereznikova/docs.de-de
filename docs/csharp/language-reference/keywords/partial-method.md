---
title: partial (Methode) (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialmethod_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
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
ms.openlocfilehash: b6f8ecca01ebf681c906b73abefc94e9e45b8700
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="partial-method-c-reference"></a><span data-ttu-id="c28e0-102">partial (Methode) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c28e0-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="c28e0-103">Bei partiellen Methoden wird die Signatur in einem Teil eines partiellen Typs definiert, und die Implementierung wird in einem anderen Teil des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="c28e0-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="c28e0-104">Mit partiellen Methoden können Klassen-Designer Methoden-Hooks bereitstellen, die Ereignis-Handlern ähneln und die Entwickler ggf. implementieren können.</span><span class="sxs-lookup"><span data-stu-id="c28e0-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="c28e0-105">Wenn der Entwickler keine Implementierung angibt, entfernt der Compiler die Signatur bei der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="c28e0-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="c28e0-106">Die folgenden Bedingungen gelten für partielle Methoden:</span><span class="sxs-lookup"><span data-stu-id="c28e0-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="c28e0-107">Die Signaturen in beiden Teilen des partiellen Typs müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c28e0-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="c28e0-108">Die Methode muss "void" zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c28e0-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="c28e0-109">Es sind keine Zugriffsmodifizierer zulässig.</span><span class="sxs-lookup"><span data-stu-id="c28e0-109">No access modifiers are allowed.</span></span> <span data-ttu-id="c28e0-110">Partielle Methoden sind implizit privat.</span><span class="sxs-lookup"><span data-stu-id="c28e0-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="c28e0-111">Im folgenden Beispiel wird eine partielle Methode veranschaulicht, die in zwei Teilen einer partiellen Klasse definiert ist:</span><span class="sxs-lookup"><span data-stu-id="c28e0-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 <span data-ttu-id="c28e0-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c28e0-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span></span>  
  
 <span data-ttu-id="c28e0-113">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="c28e0-113">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c28e0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c28e0-114">See Also</span></span>  
 <span data-ttu-id="c28e0-115">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c28e0-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="c28e0-116">partial (Typ)</span><span class="sxs-lookup"><span data-stu-id="c28e0-116">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)


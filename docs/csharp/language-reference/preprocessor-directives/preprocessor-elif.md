---
title: '#elif – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 00a9298be6ecd6f5e775d930190ddb6e227e4711
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587228"
---
# <a name="elif-c-reference"></a><span data-ttu-id="bb261-102">#elif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bb261-102">#elif (C# Reference)</span></span>
<span data-ttu-id="bb261-103">Mit `#elif` können zusammengesetzte bedingte Direktiven erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bb261-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="bb261-104">Der `#elif`-Ausdruck wird ausgewertet, wenn weder der Ausdruck der vorangehenden [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisung noch der Ausdruck einer vorangehenden optionalen `#elif`-Anweisung zu `true` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="bb261-104">The `#elif` expression will be evaluated if neither the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="bb261-105">Wenn ein `#elif`-Ausdruck zu `true` ausgewertet wird, wird der gesamte Code zwischen der `#elif`-Anweisung und der nächsten bedingten Anweisung vom Compiler ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="bb261-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="bb261-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bb261-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="bb261-107">Die Operatoren `==` (Gleichheit), `!=` (Ungleichheit), `&&` (und) und `||` (oder) können zur Auswertung mehrerer Symbole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb261-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="bb261-108">Symbole und Operatoren können auch mit Klammern gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb261-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb261-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb261-109">Remarks</span></span>  
 <span data-ttu-id="bb261-110">`#elif` ist identisch mit der Verwendung von:</span><span class="sxs-lookup"><span data-stu-id="bb261-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="bb261-111">Die Verwendung von `#elif` ist einfacher, da für jedes `#if` ein [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) erforderlich ist, während ein `#elif` ohne ein entsprechendes `#endif` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb261-111">Using `#elif` is simpler, because each `#if` requires a [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="bb261-112">Unter [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#elif`.</span><span class="sxs-lookup"><span data-stu-id="bb261-112">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb261-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb261-113">See also</span></span>

- [<span data-ttu-id="bb261-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bb261-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="bb261-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bb261-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="bb261-116">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="bb261-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

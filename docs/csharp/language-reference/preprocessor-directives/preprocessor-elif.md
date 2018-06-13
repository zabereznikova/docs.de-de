---
title: '#elif (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: ecc5c4b48790d0cb6825883922f3903414bb2b26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275569"
---
# <a name="elif-c-reference"></a><span data-ttu-id="42218-102">#elif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="42218-102">#elif (C# Reference)</span></span>
<span data-ttu-id="42218-103">Mit `#elif` können zusammengesetzte bedingte Direktiven erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="42218-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="42218-104">Der `#elif`-Ausdruck wird ausgewertet, wenn weder der Ausdruck der vorangehenden [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisung noch der Ausdruck einer vorangehenden optionalen `#elif`-Anweisung zu `true` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="42218-104">The `#elif` expression will be evaluated if neither the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="42218-105">Wenn ein `#elif`-Ausdruck zu `true` ausgewertet wird, wird der gesamte Code zwischen der `#elif`-Direktive und der nächsten bedingten Direktive vom Compiler ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="42218-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="42218-106">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="42218-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="42218-107">Die Operatoren `==` (Gleichheit), `!=` (Ungleichheit), `&&` (und) und `||` (oder) können zur Auswertung mehrerer Symbole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42218-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="42218-108">Symbole und Operatoren können auch mit Klammern gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="42218-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42218-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42218-109">Remarks</span></span>  
 <span data-ttu-id="42218-110">`#elif` ist identisch mit der Verwendung von:</span><span class="sxs-lookup"><span data-stu-id="42218-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="42218-111">Die Verwendung von `#elif` ist einfacher, da für jedes `#if` ein [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) erforderlich ist, während ein `#elif` ohne ein entsprechendes `#endif` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="42218-111">Using `#elif` is simpler, because each `#if` requires a [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="42218-112">Unter [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#elif`.</span><span class="sxs-lookup"><span data-stu-id="42218-112">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42218-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42218-113">See Also</span></span>  
 [<span data-ttu-id="42218-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="42218-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="42218-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="42218-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="42218-116">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="42218-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

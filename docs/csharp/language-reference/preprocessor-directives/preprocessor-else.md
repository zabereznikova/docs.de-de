---
title: '#else – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: 67d3e6b8fc136e16fb0e307a9f8ceca494169bfc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696138"
---
# <a name="else-c-reference"></a><span data-ttu-id="36a04-102">#else (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="36a04-102">#else (C# Reference)</span></span>
<span data-ttu-id="36a04-103">Mit `#else` können Sie eine zusammengesetzte bedingte Anweisung erstellen, sodass der Compiler, wenn keiner der Ausdrücke in den vorangehenden [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisungen oder (optional) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)-Anweisungen auf `true` festgelegt ist, den gesamten Code zwischen `#else` und der darauffolgenden `#endif`-Anweisung auswertet.</span><span class="sxs-lookup"><span data-stu-id="36a04-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or (optional) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36a04-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36a04-104">Remarks</span></span>  
 <span data-ttu-id="36a04-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) muss die nächste Präprozessoranweisung nach `#else` sein.</span><span class="sxs-lookup"><span data-stu-id="36a04-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="36a04-106">Unter [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#else`.</span><span class="sxs-lookup"><span data-stu-id="36a04-106">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a04-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36a04-107">See also</span></span>

- [<span data-ttu-id="36a04-108">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="36a04-108">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="36a04-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="36a04-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="36a04-110">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="36a04-110">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

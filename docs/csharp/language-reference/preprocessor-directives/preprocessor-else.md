---
title: '#<a name="else-c-reference"></a>else (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#else'
dev_langs:
- CSharp
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
caps.latest.revision: 11
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
ms.openlocfilehash: c4b593c757180af22ce512be624e9ac94a2e1bc6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="else-c-reference"></a><span data-ttu-id="c77fa-102">#else (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c77fa-102">#else (C# Reference)</span></span>
<span data-ttu-id="c77fa-103">Mit `#else` können Sie eine zusammengesetzte bedingte Anweisung erstellen, sodass der Compiler, wenn keiner der Ausdrücke in den vorangehenden [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisungen oder (optional) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)-Anweisungen auf `true` festgelegt ist, den gesamten Code zwischen `#else` und der darauffolgenden `#endif`-Anweisung auswertet.</span><span class="sxs-lookup"><span data-stu-id="c77fa-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or (optional) [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) directives to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c77fa-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c77fa-104">Remarks</span></span>  
 <span data-ttu-id="c77fa-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) muss die nächste Präprozessoranweisung nach `#else` sein.</span><span class="sxs-lookup"><span data-stu-id="c77fa-105">[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="c77fa-106">Unter [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#else`.</span><span class="sxs-lookup"><span data-stu-id="c77fa-106">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77fa-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c77fa-107">See Also</span></span>  
 <span data-ttu-id="c77fa-108">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c77fa-108">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c77fa-109">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c77fa-109">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c77fa-110">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="c77fa-110">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)


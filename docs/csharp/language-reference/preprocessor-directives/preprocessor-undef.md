---
title: '#<a name="undef-c-reference"></a>undef (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#undef'
dev_langs:
- CSharp
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
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
ms.openlocfilehash: acdd043535ef319f2af40c809e7fe4af612cb17d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="undef-c-reference"></a><span data-ttu-id="983dc-102">#undef (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="983dc-102">#undef (C# Reference)</span></span>
<span data-ttu-id="983dc-103">Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if`false`-Anweisung verwendet wird, wird der Ausdruck als ](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="983dc-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="983dc-104">Ein Symbol kann entweder mit der [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)-Anweisung oder der Compileroption [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="983dc-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="983dc-105">Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="983dc-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="983dc-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="983dc-106">Example</span></span>  
  
```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass   
{  
    static void Main()   
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```  
  
 <span data-ttu-id="983dc-107">**DEBUG ist nicht definiert**</span><span class="sxs-lookup"><span data-stu-id="983dc-107">**DEBUG is not defined**</span></span>   
## <a name="see-also"></a><span data-ttu-id="983dc-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="983dc-108">See Also</span></span>  
 <span data-ttu-id="983dc-109">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="983dc-109">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="983dc-110">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="983dc-110">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="983dc-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="983dc-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)


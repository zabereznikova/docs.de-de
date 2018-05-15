---
title: '#undef (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 870b78580e5350f06fae33f2ac107dc3968b2c6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="undef-c-reference"></a><span data-ttu-id="f4d7b-102">#undef (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f4d7b-102">#undef (C# Reference)</span></span>
<span data-ttu-id="f4d7b-103">Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if`false`-Anweisung verwendet wird, wird der Ausdruck als ](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f4d7b-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="f4d7b-104">Ein Symbol kann entweder mit der [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)-Anweisung oder der Compileroption [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f4d7b-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="f4d7b-105">Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="f4d7b-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4d7b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4d7b-106">Example</span></span>  
  
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
  
 <span data-ttu-id="f4d7b-107">**DEBUG ist nicht definiert**</span><span class="sxs-lookup"><span data-stu-id="f4d7b-107">**DEBUG is not defined**</span></span>  
## <a name="see-also"></a><span data-ttu-id="f4d7b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4d7b-108">See Also</span></span>  
 [<span data-ttu-id="f4d7b-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f4d7b-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f4d7b-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f4d7b-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f4d7b-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="f4d7b-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

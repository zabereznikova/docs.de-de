---
title: '#undef (C#-Referenz)'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 3957d58f61e51fab01618f5e1146be9cd0da58fd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185966"
---
# <a name="undef-c-reference"></a><span data-ttu-id="e1c60-102">#undef (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e1c60-102">#undef (C# Reference)</span></span>
<span data-ttu-id="e1c60-103">Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if`false`-Anweisung verwendet wird, wird der Ausdruck als ](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e1c60-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="e1c60-104">Ein Symbol kann entweder mit der Anweisung [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) oder der Compileroption [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e1c60-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="e1c60-105">Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="e1c60-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1c60-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1c60-106">Example</span></span>  

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

<span data-ttu-id="e1c60-107">**DEBUG ist nicht definiert**</span><span class="sxs-lookup"><span data-stu-id="e1c60-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="e1c60-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1c60-108">See Also</span></span>

- [<span data-ttu-id="e1c60-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e1c60-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e1c60-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e1c60-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e1c60-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="e1c60-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

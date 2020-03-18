---
title: '#undef – C#-Referenz'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 21923412aa178c3b86e94a54bd911130e48e4deb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712441"
---
# <a name="undef-c-reference"></a><span data-ttu-id="9a9c0-102">#undef (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9a9c0-102">#undef (C# Reference)</span></span>
<span data-ttu-id="9a9c0-103">Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if](./preprocessor-if.md)-Anweisung verwendet wird, wird der Ausdruck als `false` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9a9c0-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="9a9c0-104">Ein Symbol kann entweder mit der Anweisung [#define](./preprocessor-define.md) oder der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a9c0-104">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="9a9c0-105">Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="9a9c0-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a9c0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a9c0-106">Example</span></span>  

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

<span data-ttu-id="9a9c0-107">**DEBUG ist nicht definiert**</span><span class="sxs-lookup"><span data-stu-id="9a9c0-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="9a9c0-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a9c0-108">See also</span></span>

- [<span data-ttu-id="9a9c0-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9a9c0-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9a9c0-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9a9c0-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9a9c0-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="9a9c0-111">C# Preprocessor Directives</span></span>](./index.md)

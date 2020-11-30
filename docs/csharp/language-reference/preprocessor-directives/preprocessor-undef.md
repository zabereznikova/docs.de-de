---
description: '#undef – C#-Referenz'
title: '#undef – C#-Referenz'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 7db79be7ea9d8462e09b6ae874bf0ae7d265afe2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91150556"
---
# <a name="undef-c-reference"></a><span data-ttu-id="aaa3d-103">#undef (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="aaa3d-103">#undef (C# Reference)</span></span>

<span data-ttu-id="aaa3d-104">Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if`false`-Anweisung verwendet wird, wird der Ausdruck als ](./preprocessor-if.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="aaa3d-104">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="aaa3d-105">Ein Symbol kann entweder mit der Anweisung [#define](./preprocessor-define.md) oder der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="aaa3d-105">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="aaa3d-106">Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="aaa3d-106">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaa3d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aaa3d-107">Example</span></span>  

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

<span data-ttu-id="aaa3d-108">**DEBUG ist nicht definiert**</span><span class="sxs-lookup"><span data-stu-id="aaa3d-108">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="aaa3d-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaa3d-109">See also</span></span>

- [<span data-ttu-id="aaa3d-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="aaa3d-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="aaa3d-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="aaa3d-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="aaa3d-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="aaa3d-112">C# Preprocessor Directives</span></span>](./index.md)

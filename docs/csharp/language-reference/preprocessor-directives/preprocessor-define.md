---
description: '#define – C#-Referenz'
title: '#define – C#-Referenz'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: 961c20c091a4a6d7da421d94500abd41d2d60a5b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160501"
---
# <a name="define-c-reference"></a><span data-ttu-id="8ea32-103">#define (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8ea32-103">#define (C# Reference)</span></span>

<span data-ttu-id="8ea32-104">Mit `#define` wird ein Symbol definiert.</span><span class="sxs-lookup"><span data-stu-id="8ea32-104">You use `#define` to define a symbol.</span></span> <span data-ttu-id="8ea32-105">Wenn Sie das Symbol als Ausdruck verwenden, der an die [#if](./preprocessor-if.md)-Anweisung übergeben wird, wird der Ausdruck als `true` ausgewertet, wie in folgendem Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8ea32-105">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="8ea32-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8ea32-106">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ea32-107">Die `#define`-Direktive kann nicht zur Deklaration konstanter Werte wie in C und C++ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ea32-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="8ea32-108">Definieren Sie Konstanten in C# als statische Member einer Klasse oder einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="8ea32-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="8ea32-109">Wenn Sie über mehrere solcher Konstanten verfügen, erwägen Sie, eine separate "Constants"-Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8ea32-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="8ea32-110">Symbole können verwendet werden, um Bedingungen für die Kompilierung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8ea32-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="8ea32-111">Ein Symbol kann entweder mit [#if](./preprocessor-if.md) oder mit [#elif](./preprocessor-elif.md) überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="8ea32-111">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="8ea32-112">Für die bedingte Kompilierung kann auch <xref:System.Diagnostics.ConditionalAttribute> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ea32-112">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="8ea32-113">Ein Symbol kann zwar definiert werden, aber es kann ihm kein Wert zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8ea32-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="8ea32-114">Die `#define`-Direktive muss in einer Datei vor allen Anweisungen, bei denen es sich nicht um Präprozessordirektiven handelt, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ea32-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="8ea32-115">Ein Symbol kann auch mit der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8ea32-115">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="8ea32-116">Die Definition eines Symbols kann mit [#undef](./preprocessor-undef.md) aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="8ea32-116">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="8ea32-117">Zwischen einem Symbol, das mit `-define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt.</span><span class="sxs-lookup"><span data-stu-id="8ea32-117">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="8ea32-118">Das bedeutet, dass ein Variablenname nicht an eine Präprozessordirektive übergeben werden sollte und ein Symbol nur von einer Präprozessordirektive ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8ea32-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="8ea32-119">Bei dem Gültigkeitsbereich eines mit `#define` erstellten Symbols handelt es sich um die Datei, in der es definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8ea32-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="8ea32-120">Wie im folgenden Beispiel dargestellt, müssen Sie die `#define`-Direktive am Anfang der Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="8ea32-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="8ea32-121">Ein Beispiel dafür, wie eine Symboldefinition aufgehoben wird, finden Sie unter [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="8ea32-121">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea32-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ea32-122">See also</span></span>

- [<span data-ttu-id="8ea32-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="8ea32-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8ea32-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8ea32-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8ea32-125">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="8ea32-125">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="8ea32-126">const</span><span class="sxs-lookup"><span data-stu-id="8ea32-126">const</span></span>](../keywords/const.md)
- [<span data-ttu-id="8ea32-127">How to: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen</span><span class="sxs-lookup"><span data-stu-id="8ea32-127">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="8ea32-128">#undef</span><span class="sxs-lookup"><span data-stu-id="8ea32-128">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="8ea32-129">#if</span><span class="sxs-lookup"><span data-stu-id="8ea32-129">#if</span></span>](./preprocessor-if.md)

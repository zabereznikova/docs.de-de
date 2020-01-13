---
title: '#define – C#-Referenz'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: 7457b05ae827675969398792bcb02f025f3028fb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712584"
---
# <a name="define-c-reference"></a><span data-ttu-id="e3760-102">#define (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e3760-102">#define (C# Reference)</span></span>
<span data-ttu-id="e3760-103">Mit `#define` wird ein Symbol definiert.</span><span class="sxs-lookup"><span data-stu-id="e3760-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="e3760-104">Wenn Sie das Symbol als Ausdruck verwenden, der an die [#if](./preprocessor-if.md)-Anweisung übergeben wird, wird der Ausdruck als `true` ausgewertet, wie in folgendem Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e3760-104">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="e3760-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3760-105">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3760-106">Die `#define`-Direktive kann nicht zur Deklaration konstanter Werte wie in C und C++ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3760-106">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="e3760-107">Definieren Sie Konstanten in C# als statische Member einer Klasse oder einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="e3760-107">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="e3760-108">Wenn Sie über mehrere solcher Konstanten verfügen, erwägen Sie, eine separate "Constants"-Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3760-108">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="e3760-109">Symbole können verwendet werden, um Bedingungen für die Kompilierung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e3760-109">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="e3760-110">Ein Symbol kann entweder mit [#if](./preprocessor-if.md) oder mit [#elif](./preprocessor-elif.md) überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="e3760-110">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="e3760-111">Für die bedingte Kompilierung kann auch <xref:System.Diagnostics.ConditionalAttribute> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3760-111">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="e3760-112">Ein Symbol kann zwar definiert werden, aber es kann ihm kein Wert zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e3760-112">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="e3760-113">Die `#define`-Direktive muss in einer Datei vor allen Anweisungen, bei denen es sich nicht um Präprozessordirektiven handelt, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3760-113">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="e3760-114">Ein Symbol kann auch mit der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e3760-114">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="e3760-115">Die Definition eines Symbols kann mit [#undef](./preprocessor-undef.md) aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="e3760-115">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="e3760-116">Zwischen einem Symbol, das mit `-define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt.</span><span class="sxs-lookup"><span data-stu-id="e3760-116">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="e3760-117">Das bedeutet, dass ein Variablenname nicht an eine Präprozessordirektive übergeben werden sollte und ein Symbol nur von einer Präprozessordirektive ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e3760-117">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="e3760-118">Bei dem Gültigkeitsbereich eines mit `#define` erstellten Symbols handelt es sich um die Datei, in der es definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e3760-118">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="e3760-119">Wie im folgenden Beispiel dargestellt, müssen Sie die `#define`-Direktive am Anfang der Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="e3760-119">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
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
  
 <span data-ttu-id="e3760-120">Ein Beispiel dafür, wie eine Symboldefinition aufgehoben wird, finden Sie unter [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="e3760-120">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3760-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3760-121">See also</span></span>

- [<span data-ttu-id="e3760-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e3760-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e3760-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e3760-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e3760-124">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="e3760-124">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="e3760-125">const</span><span class="sxs-lookup"><span data-stu-id="e3760-125">const</span></span>](../keywords/const.md)
- [<span data-ttu-id="e3760-126">Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen</span><span class="sxs-lookup"><span data-stu-id="e3760-126">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="e3760-127">#undef</span><span class="sxs-lookup"><span data-stu-id="e3760-127">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="e3760-128">#if</span><span class="sxs-lookup"><span data-stu-id="e3760-128">#if</span></span>](./preprocessor-if.md)

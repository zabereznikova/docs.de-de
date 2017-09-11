---
title: '#<a name="define-c-reference"></a>define (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
dev_langs:
- CSharp
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
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
ms.openlocfilehash: 8ace15f79480c9aeb0fcb4c7d46c207d4904cef0
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="define-c-reference"></a><span data-ttu-id="e4f85-102">#define (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e4f85-102">#define (C# Reference)</span></span>
<span data-ttu-id="e4f85-103">Mit `#define` wird ein Symbol definiert.</span><span class="sxs-lookup"><span data-stu-id="e4f85-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="e4f85-104">Wenn Sie das Symbol als Ausdruck verwenden, der an die [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisung übergeben wird, wird der Ausdruck als `true` ausgewertet, wie in folgendem Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e4f85-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
  
 <span data-ttu-id="e4f85-105">`#`  `define`   `DEBUG`</span><span class="sxs-lookup"><span data-stu-id="e4f85-105">`#`  `define`   `DEBUG`</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4f85-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4f85-106">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4f85-107">Die `#define`-Direktive kann nicht zur Deklaration konstanter Werte wie in C und C++ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4f85-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="e4f85-108">Definieren Sie Konstanten in C# als statische Member einer Klasse oder einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="e4f85-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="e4f85-109">Wenn Sie über mehrere solcher Konstanten verfügen, erwägen Sie, eine separate "Constants"-Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4f85-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="e4f85-110">Symbole können verwendet werden, um Bedingungen für die Kompilierung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e4f85-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="e4f85-111">Ein Symbol kann entweder mit [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) oder mit [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="e4f85-111">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="e4f85-112">Für bedingte Kompilierung kann auch das `conditional`-Attribut verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4f85-112">You can also use the `conditional` attribute to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="e4f85-113">Ein Symbol kann zwar definiert werden, aber es kann ihm kein Wert zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e4f85-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="e4f85-114">Die `#define`-Direktive muss in einer Datei vor allen Anweisungen, bei denen es sich nicht um Präprozessordirektiven handelt, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4f85-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="e4f85-115">Ein Symbol kann auch mit der Compileroption [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4f85-115">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="e4f85-116">Die Definition eines Symbols kann mit [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="e4f85-116">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="e4f85-117">Zwischen einem Symbol, das mit `/define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt.</span><span class="sxs-lookup"><span data-stu-id="e4f85-117">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="e4f85-118">Das bedeutet, dass ein Variablenname nicht an eine Präprozessordirektive übergeben werden sollte und ein Symbol nur von einer Präprozessordirektive ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4f85-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="e4f85-119">Bei dem Gültigkeitsbereich eines mit `#define` erstellten Symbols handelt es sich um die Datei, in der es definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e4f85-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="e4f85-120">Wie im folgenden Beispiel dargestellt, müssen Sie die `#define`-Direktive am Anfang der Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="e4f85-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
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
  
 <span data-ttu-id="e4f85-121">Ein Beispiel dafür, wie eine Symboldefinition aufgehoben wird, finden Sie unter [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="e4f85-121">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f85-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4f85-122">See Also</span></span>  
 <span data-ttu-id="e4f85-123">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4f85-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e4f85-124">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4f85-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e4f85-125">[C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4f85-125">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="e4f85-126">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="e4f85-126">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 <span data-ttu-id="e4f85-127">[Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span><span class="sxs-lookup"><span data-stu-id="e4f85-127">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span></span>  
 <span data-ttu-id="e4f85-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span><span class="sxs-lookup"><span data-stu-id="e4f85-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span></span>  
 [<span data-ttu-id="e4f85-129">#if</span><span class="sxs-lookup"><span data-stu-id="e4f85-129">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)


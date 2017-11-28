---
title: '#<a name="if-c-reference"></a>if (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#if'
helpviewer_keywords: '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4e3b79f64f5190d48d7248726ecdf031ad685e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="if-c-reference"></a><span data-ttu-id="5d26f-102">#if (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5d26f-102">#if (C# Reference)</span></span>
<span data-ttu-id="5d26f-103">Wenn der C#-Compiler eine `#if`-Direktive vorfindet, auf die möglicherweise eine [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)-Direktive folgt, wird der Code zwischen den Direktiven nur dann kompiliert, wenn das angegebene Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5d26f-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) directive, it will compile the code between the directives only if the specified symbol is defined.</span></span>  <span data-ttu-id="5d26f-104">Im Gegensatz zu C und C++ können Sie einem Symbol keinen numerischen Wert zuweisen. Die #if-Anweisung in C# ist ein boolescher Ausdruck und überprüft nur, ob das Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5d26f-104">Unlike C and C++, you cannot assign a numeric value to a symbol; the #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="5d26f-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d26f-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 <span data-ttu-id="5d26f-106">Sie können die Operatoren [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (Gleichheit), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (Ungleichheit) nur zur Überprüfung auf [true](../../../csharp/language-reference/keywords/true.md) oder [false](../../../csharp/language-reference/keywords/false.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d26f-106">You can use the operators [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (equality), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (inequality) only to test for [true](../../../csharp/language-reference/keywords/true.md) or [false](../../../csharp/language-reference/keywords/false.md) .</span></span> <span data-ttu-id="5d26f-107">„True“ bedeutet, dass das Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5d26f-107">True means the symbol is defined.</span></span> <span data-ttu-id="5d26f-108">Die `#if DEBUG`-Anweisung hat die gleiche Bedeutung wie `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="5d26f-108">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="5d26f-109">Sie können mithilfe der Operatoren [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (und), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (oder) und [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="5d26f-109">You can use the operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (and), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (or), and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="5d26f-110">(nicht ) auswerten, ob mehrere Symbole definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5d26f-110">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="5d26f-111">Symbole und Operatoren können auch mit Klammern gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d26f-111">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d26f-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d26f-112">Remarks</span></span>  
 <span data-ttu-id="5d26f-113">Wenn Sie `#if` mit den Direktiven [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) und [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) verwenden, können Sie Code je nach dem Vorhandensein eines oder mehrerer Symbole ein- oder ausschließen.</span><span class="sxs-lookup"><span data-stu-id="5d26f-113">`#if`, along with the [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), and [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="5d26f-114">Dies kann hilfreich sein, wenn Code für einen Debugbuild oder für eine bestimmte Konfiguration kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="5d26f-114">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>  
  
 <span data-ttu-id="5d26f-115">Eine bedingte Direktive, die mit einer `#if`-Direktive beginnt, muss explizit mit einer `#endif`-Direktive beendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d26f-115">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>  
  
 <span data-ttu-id="5d26f-116">Mit `#define` kann ein Symbol definiert werden. Wenn dieses Symbol dann als Ausdruck an die `#if`-Direktive übergeben wird, wird der Ausdruck als `true` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="5d26f-116">`#define` lets you define a symbol, such that, by using the symbol as the expression passed to the `#if` directive, the expression will evaluate to `true`.</span></span>  
  
 <span data-ttu-id="5d26f-117">Ein Symbol kann auch mit der [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)-Compileroption definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d26f-117">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="5d26f-118">Die Definition eines Symbols kann mit [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="5d26f-118">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="5d26f-119">Zwischen einem Symbol, das mit `/define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt.</span><span class="sxs-lookup"><span data-stu-id="5d26f-119">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="5d26f-120">Das bedeutet, dass ein Variablenname nicht an eine Präprozessordirektive übergeben werden sollte und ein Symbol nur von einer Präprozessordirektive ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5d26f-120">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="5d26f-121">Der Gültigkeitsbereich eines mit `#define` erstellten Symbols ist die Datei, in der es definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5d26f-121">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d26f-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d26f-122">Example</span></span>  
  
```csharp
// preprocessor_if.cs  
#define DEBUG
#define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
 <span data-ttu-id="5d26f-123">**DEBUG und MYTEST werden definiert.**</span><span class="sxs-lookup"><span data-stu-id="5d26f-123">**DEBUG and MYTEST are defined**</span></span>  
## <a name="see-also"></a><span data-ttu-id="5d26f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d26f-124">See Also</span></span>  
 [<span data-ttu-id="5d26f-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5d26f-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5d26f-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5d26f-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5d26f-127">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="5d26f-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

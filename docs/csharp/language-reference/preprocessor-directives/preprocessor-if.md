---
title: '##if-Präprozessoranweisung (C#-Referenz)'
ms.date: 06/30/2018
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: c54a1fe0dba5f6d57b03b2ffeb4f1737fadfe039
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000936"
---
# <a name="if-c-reference"></a><span data-ttu-id="6e2cb-102">#if (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6e2cb-102">#if (C# Reference)</span></span>

<span data-ttu-id="6e2cb-103">Wenn der C#-Compiler eine `#if`-Anweisung vorfindet, auf die möglicherweise eine [#endif](preprocessor-endif.md)-Anweisung folgt, wird der Code zwischen den Anweisungen nur dann kompiliert, wenn das angegebene Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="6e2cb-104">Im Gegensatz zu C und C++ können Sie einem Symbol keinen numerischen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-104">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="6e2cb-105">Die #if-Anweisung in C# ist ein boolescher Wert und überprüft nur, ob das Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-105">The #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="6e2cb-106">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e2cb-106">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="6e2cb-107">Sie können die Operatoren [==](../operators/equality-comparison-operator.md) (Gleichheit) und [!=](../operators/not-equal-operator.md) (Ungleichheit) nur zur Überprüfung auf [true](../keywords/true.md) oder [false](../keywords/false.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-107">You can use the operators [==](../operators/equality-comparison-operator.md) (equality) and [!=](../operators/not-equal-operator.md) (inequality) only to test for [true](../keywords/true.md) or [false](../keywords/false.md).</span></span> <span data-ttu-id="6e2cb-108">„True“ bedeutet, dass das Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-108">True means the symbol is defined.</span></span> <span data-ttu-id="6e2cb-109">Die `#if DEBUG`-Anweisung hat die gleiche Bedeutung wie `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-109">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="6e2cb-110">Sie können mithilfe der Operatoren [&&](../operators/conditional-and-operator.md) (und), [&#124;&#124;](../operators/conditional-or-operator.md) (oder) und [!](../operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="6e2cb-110">You can use the operators [&&](../operators/conditional-and-operator.md) (and), [&#124;&#124;](../operators/conditional-or-operator.md) (or), and [!](../operators/logical-negation-operator.md)</span></span> <span data-ttu-id="6e2cb-111">(nicht ) auswerten, ob mehrere Symbole definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-111">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="6e2cb-112">Symbole und Operatoren können auch mit Klammern gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-112">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e2cb-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e2cb-113">Remarks</span></span>

<span data-ttu-id="6e2cb-114">Wenn Sie `#if` mit den Direktiven [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) und [#undef](preprocessor-undef.md) verwenden, können Sie Code je nach dem Vorhandensein eines oder mehrerer Symbole ein- oder ausschließen.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-114">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="6e2cb-115">Dies kann hilfreich sein, wenn Code für einen Debugbuild oder für eine bestimmte Konfiguration kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-115">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="6e2cb-116">Eine bedingte Direktive, die mit einer `#if`-Direktive beginnt, muss explizit mit einer `#endif`-Direktive beendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-116">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="6e2cb-117">Über `#define` können Sie ein Symbol definieren.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-117">`#define` lets you define a symbol.</span></span> <span data-ttu-id="6e2cb-118">Wenn dieses Symbol dann als Ausdruck an die `#if`-Anweisung übergeben wird, wird der Ausdruck als `true` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-118">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="6e2cb-119">Ein Symbol kann auch mit der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-119">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="6e2cb-120">Die Definition eines Symbols kann mit [#undef](preprocessor-undef.md) aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-120">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="6e2cb-121">Zwischen einem Symbol, das mit `-define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-121">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="6e2cb-122">Das bedeutet, dass ein Variablenname nicht an eine Präprozessoranweisung übergeben werden sollte und ein Symbol nur von einer Präprozessoranweisung ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-122">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="6e2cb-123">Der Gültigkeitsbereich eines mit `#define` erstellten Symbols ist die Datei, in der es definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-123">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="6e2cb-124">Das Buildsystem kennt zudem vordefinierte Präprozessorsymbole, die verschiedene [Zielframeworks](../../../standard/frameworks.md) darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-124">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md).</span></span> <span data-ttu-id="6e2cb-125">Diese sind hilfreich, wenn Sie Anwendungen erstellen, die für mehrere .NET-Implementierungen oder -Versionen bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-125">They're useful when creating applications that can target more than one .NET implementation or version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

<span data-ttu-id="6e2cb-126">Weitere vordefinierte Symbole sind die Konstanten DEBUG und TRACE.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-126">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="6e2cb-127">Sie können die für das Projekt festgelegten Werte mit `#define` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-127">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="6e2cb-128">Das DEBUG-Symbol beispielsweise wird abhängig von den Buildkonfigurationseigenschaften (Modus „Debug“ oder „Release“) automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-128">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="6e2cb-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6e2cb-129">Examples</span></span>

<span data-ttu-id="6e2cb-130">Im folgenden Beispiel wird gezeigt, wie Sie ein MYTEST-Symbol für eine Datei definieren und dann die Werte der Symbole MYTEST und DEBUG testen.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-130">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="6e2cb-131">Die Ausgabe dieses Beispiels hängt davon ab, ob Sie das Projekt im Debug- oder im Release-Konfigurationsmodus erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e2cb-131">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

```csharp
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

<span data-ttu-id="6e2cb-132">Im folgenden Beispiel wird gezeigt, wie für andere Zielframeworks zu testen, damit Sie neuere APIs möglichst verwenden können:</span><span class="sxs-lookup"><span data-stu-id="6e2cb-132">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a><span data-ttu-id="6e2cb-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e2cb-133">See also</span></span>

- [<span data-ttu-id="6e2cb-134">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6e2cb-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6e2cb-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6e2cb-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6e2cb-136">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="6e2cb-136">C# Preprocessor Directives</span></span>](index.md)  
- <span data-ttu-id="6e2cb-137">[Gewusst wie: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)</span><span class="sxs-lookup"><span data-stu-id="6e2cb-137">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).</span></span>

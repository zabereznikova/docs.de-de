---
description: '#if-Präprozessoranweisung – C#-Referenz'
title: '#if-Präprozessoranweisung – C#-Referenz'
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: dc3e235db49279691203a0db4d124239fb972c69
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065232"
---
# <a name="if-c-reference"></a><span data-ttu-id="7e6b1-103">#if (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7e6b1-103">#if (C# reference)</span></span>

<span data-ttu-id="7e6b1-104">Wenn der C#-Compiler eine `#if`-Anweisung vorfindet, auf die möglicherweise eine [#endif](preprocessor-endif.md)-Anweisung folgt, wird der Code zwischen den Anweisungen nur dann kompiliert, wenn das angegebene Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-104">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="7e6b1-105">Im Gegensatz zu C und C++ können Sie einem Symbol keinen numerischen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-105">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="7e6b1-106">Die `#if`-Anweisung in C# ist ein boolescher Wert und überprüft nur, ob das Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-106">The `#if` statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="7e6b1-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e6b1-107">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="7e6b1-108">Sie können die Operatoren [==](../operators/equality-operators.md#equality-operator-) (Gleichheit) und [!=](../operators/equality-operators.md#inequality-operator-) (Ungleichheit) nur zum Testen auf die [booleschen Werte](../builtin-types/bool.md)`true` oder `false` verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-108">You can use the operators [==](../operators/equality-operators.md#equality-operator-) (equality) and [!=](../operators/equality-operators.md#inequality-operator-) (inequality) only to test for the [bool](../builtin-types/bool.md) values `true` or `false`.</span></span> <span data-ttu-id="7e6b1-109">`true` bedeutet, dass das Symbol definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-109">`true` means the symbol is defined.</span></span> <span data-ttu-id="7e6b1-110">Die `#if DEBUG`-Anweisung hat die gleiche Bedeutung wie `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-110">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="7e6b1-111">Sie können die Operatoren [&& (und)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (oder)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) und [! (nicht)](../operators/boolean-logical-operators.md#logical-negation-operator-) verwenden, um auszuwerten, ob mehrere Symbole definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-111">You can use the [&& (and)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (or)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-), and [! (not)](../operators/boolean-logical-operators.md#logical-negation-operator-) operators to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="7e6b1-112">Symbole und Operatoren können auch mit Klammern gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-112">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e6b1-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7e6b1-113">Remarks</span></span>

<span data-ttu-id="7e6b1-114">Wenn Sie `#if` mit den Direktiven [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) und [#undef](preprocessor-undef.md) verwenden, können Sie Code je nach dem Vorhandensein eines oder mehrerer Symbole ein- oder ausschließen.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-114">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="7e6b1-115">Dies kann hilfreich sein, wenn Code für einen Debugbuild oder für eine bestimmte Konfiguration kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-115">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="7e6b1-116">Eine bedingte Direktive, die mit einer `#if`-Direktive beginnt, muss explizit mit einer `#endif`-Direktive beendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-116">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="7e6b1-117">Über `#define` können Sie ein Symbol definieren.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-117">`#define` lets you define a symbol.</span></span> <span data-ttu-id="7e6b1-118">Wenn dieses Symbol dann als Ausdruck an die `#if`-Anweisung übergeben wird, wird der Ausdruck als `true` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-118">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="7e6b1-119">Ein Symbol kann auch mit der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-119">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="7e6b1-120">Die Definition eines Symbols kann mit [#undef](preprocessor-undef.md) aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-120">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="7e6b1-121">Zwischen einem Symbol, das mit `-define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-121">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="7e6b1-122">Das bedeutet, dass ein Variablenname nicht an eine Präprozessoranweisung übergeben werden sollte und ein Symbol nur von einer Präprozessoranweisung ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-122">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="7e6b1-123">Der Gültigkeitsbereich eines mit `#define` erstellten Symbols ist die Datei, in der es definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-123">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="7e6b1-124">Das Buildsystem kennt zudem vordefinierte Präprozessorsymbole, die verschiedene [Zielframeworks](../../../standard/frameworks.md) in Projekten im SDK-Format darstellen.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-124">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md) in SDK-style projects.</span></span> <span data-ttu-id="7e6b1-125">Diese sind hilfreich, wenn Sie Anwendungen erstellen, die für mehr als eine .NET-Version bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-125">They're useful when creating applications that can target more than one .NET version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> <span data-ttu-id="7e6b1-126">Für herkömmliche Projekte, die kein SDK-Format aufweisen, müssen Sie die Symbole für die bedingte Kompilierung für die verschiedenen Zielframeworks in Visual Studio über die Eigenschaftenseite des Projekts manuell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-126">For traditional, non-SDK-style projects, you have to manually configure the conditional compilation symbols for the different target frameworks in Visual Studio via the project's properties pages.</span></span>

<span data-ttu-id="7e6b1-127">Weitere vordefinierte Symbole sind die Konstanten DEBUG und TRACE.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-127">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="7e6b1-128">Sie können die für das Projekt festgelegten Werte mit `#define` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-128">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="7e6b1-129">Das DEBUG-Symbol beispielsweise wird abhängig von den Buildkonfigurationseigenschaften (Modus „Debug“ oder „Release“) automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-129">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="7e6b1-130">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7e6b1-130">Examples</span></span>

<span data-ttu-id="7e6b1-131">Im folgenden Beispiel wird gezeigt, wie Sie ein MYTEST-Symbol für eine Datei definieren und dann die Werte der Symbole MYTEST und DEBUG testen.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-131">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="7e6b1-132">Die Ausgabe dieses Beispiels hängt davon ab, ob Sie das Projekt im Debug- oder im Release-Konfigurationsmodus erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-132">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

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

<span data-ttu-id="7e6b1-133">Im folgenden Beispiel wird gezeigt, wie für andere Zielframeworks zu testen, damit Sie neuere APIs möglichst verwenden können:</span><span class="sxs-lookup"><span data-stu-id="7e6b1-133">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7e6b1-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e6b1-134">See also</span></span>

- [<span data-ttu-id="7e6b1-135">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7e6b1-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7e6b1-136">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7e6b1-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7e6b1-137">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="7e6b1-137">C# Preprocessor Directives</span></span>](index.md)
- [<span data-ttu-id="7e6b1-138">How to: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen</span><span class="sxs-lookup"><span data-stu-id="7e6b1-138">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

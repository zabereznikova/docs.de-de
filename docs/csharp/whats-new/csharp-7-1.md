---
title: Neues in C# 7.1
description: Eine Übersicht der neuen Features in C# 7.1
ms.date: 04/09/2019
ms.openlocfilehash: a95111b6f217a2ca5c520c2d4d70efa0e23742f9
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347616"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="ea413-103">Neues in C# 7.1</span><span class="sxs-lookup"><span data-stu-id="ea413-103">What's new in C# 7.1</span></span>

<span data-ttu-id="ea413-104">C# 7.1 ist die erste Punktversion der C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="ea413-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="ea413-105">Das bedeutet schnellere Releaserhythmen für die Sprache.</span><span class="sxs-lookup"><span data-stu-id="ea413-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="ea413-106">Sie können die neuen Features früher benutzen, im Idealfall sobald ein neues Feature bereit ist.</span><span class="sxs-lookup"><span data-stu-id="ea413-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="ea413-107">Mit C# 7.1 wird die Fähigkeit hinzugefügt, den Compiler so zu konfigurieren, dass er einer bestimmten Version der Sprache entspricht.</span><span class="sxs-lookup"><span data-stu-id="ea413-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="ea413-108">Damit können Sie die Entscheidung, Tools upzugraden, von der Entscheidung unterscheiden, Upgrades für Sprachversionen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ea413-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="ea413-109">Mit C# 7.1 wird ein Konfigurationselement zum [Auswählen der Sprachversion](../language-reference/configure-language-version.md), drei neue Sprachfeatures und neues Compilerverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ea413-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="ea413-110">Die neuen Sprachfeatures in diesem Release umfassen:</span><span class="sxs-lookup"><span data-stu-id="ea413-110">The new language features in this release are:</span></span>

* <span data-ttu-id="ea413-111">Die [`async``Main`-Methode](#async-main)</span><span class="sxs-lookup"><span data-stu-id="ea413-111">[`async` `Main` method](#async-main)</span></span>
  - <span data-ttu-id="ea413-112">Der Einstiegspunkt für eine Anwendung kann über den Modifizierer `async` verfügen.</span><span class="sxs-lookup"><span data-stu-id="ea413-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="ea413-113">`default`Literale Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ea413-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="ea413-114">Sie können literale Standardausdrücke in Standardwertausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea413-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="ea413-115">Abgeleitete Tupelelementnamen</span><span class="sxs-lookup"><span data-stu-id="ea413-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="ea413-116">Die Namen von Tupelelementen können in den meisten Fällen von der Initialisierung eines Tupels abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ea413-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
* [<span data-ttu-id="ea413-117">Musterabgleich für generische Typparameter</span><span class="sxs-lookup"><span data-stu-id="ea413-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="ea413-118">Sie können Musterabgleichsausdrücke für Variablen verwenden, deren Typ ein generischer Typparameter ist.</span><span class="sxs-lookup"><span data-stu-id="ea413-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="ea413-119">Außerdem verfügt der Compiler über die zwei Optionen `-refout` und `-refonly`, mit denen die [Generierung der Referenzassembly](#reference-assembly-generation) gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="ea413-119">Finally, the compiler has two options `-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="ea413-120">Sie müssen [die Sprachversion des Compilers konfigurieren](../language-reference/configure-language-version.md) und die Version auswählen, um die neuesten Features in einer Punktversion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea413-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

<span data-ttu-id="ea413-121">Dieser Artikel enthält im Folgenden eine Übersicht über die einzelnen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="ea413-121">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="ea413-122">Sie werden die Hintergründe jeder einzelnen Funktion erfahren.</span><span class="sxs-lookup"><span data-stu-id="ea413-122">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="ea413-123">Sie werden die Syntax erlernen.</span><span class="sxs-lookup"><span data-stu-id="ea413-123">You'll learn the syntax.</span></span> <span data-ttu-id="ea413-124">Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:</span><span class="sxs-lookup"><span data-stu-id="ea413-124">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="ea413-125">Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.</span><span class="sxs-lookup"><span data-stu-id="ea413-125">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="ea413-126">Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.</span><span class="sxs-lookup"><span data-stu-id="ea413-126">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="ea413-127">Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.</span><span class="sxs-lookup"><span data-stu-id="ea413-127">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="ea413-128">Führen Sie aus `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="ea413-128">Run `dotnet try`.</span></span>

## <a name="async-main"></a><span data-ttu-id="ea413-129">Async Main</span><span class="sxs-lookup"><span data-stu-id="ea413-129">Async main</span></span>

<span data-ttu-id="ea413-130">Mithilfe einer *async main*-Methode können Sie `await` in Ihrer `Main`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea413-130">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="ea413-131">Vorher hätten Sie das Folgende schreiben müssen:</span><span class="sxs-lookup"><span data-stu-id="ea413-131">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="ea413-132">Nun können Sie das Folgende schreiben:</span><span class="sxs-lookup"><span data-stu-id="ea413-132">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="ea413-133">Wenn Ihr Programm keinen Exitcode zurückgibt, können Sie eine `Main`-Methode deklarieren, die einen <xref:System.Threading.Tasks.Task> zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="ea413-133">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="ea413-134">Ausführliche Informationen finden Sie unter [Async Main](../programming-guide/main-and-command-args/index.md) im Programmierhandbuch.</span><span class="sxs-lookup"><span data-stu-id="ea413-134">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="ea413-135">Literale Standardausdrücke</span><span class="sxs-lookup"><span data-stu-id="ea413-135">Default literal expressions</span></span>

<span data-ttu-id="ea413-136">Literale Standardausdrücke sind eine Erweiterung von Ausdrücken mit Standardwert.</span><span class="sxs-lookup"><span data-stu-id="ea413-136">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="ea413-137">Diese Ausdrücke initialisieren eine Variable auf dem Standardwert.</span><span class="sxs-lookup"><span data-stu-id="ea413-137">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="ea413-138">Dort, wo Sie vorher das Folgende geschrieben haben:</span><span class="sxs-lookup"><span data-stu-id="ea413-138">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="ea413-139">Können Sie nun den Typ weglassen, der auf der rechten Seite der Initialisierung steht.</span><span class="sxs-lookup"><span data-stu-id="ea413-139">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="ea413-140">Weitere Informationen zu dieser Erweiterung finden Sie unter [Standardwertausdrücke](../programming-guide/statements-expressions-operators/default-value-expressions.md) im C#-Programmierhandbuch.</span><span class="sxs-lookup"><span data-stu-id="ea413-140">You can learn more about this enhancement in the C# Programming Guide article on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="ea413-141">Diese Erweiterung ändert auch einige Regeln der Analyse für das [Schlüsselwort „default“](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="ea413-141">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="ea413-142">Abgeleitete Tupelelementnamen</span><span class="sxs-lookup"><span data-stu-id="ea413-142">Inferred tuple element names</span></span>

<span data-ttu-id="ea413-143">Dieses Feature ist eine kleine Erweiterung des Tupelfeatures, das in C# 7.0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ea413-143">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="ea413-144">Wenn Sie einen Tupel initialisieren, sind die Variablen, die für die rechte Seite der Zuweisung verwendet werden, oft dieselben, wie die Namen, die Sie den Tupelelementen geben möchten.</span><span class="sxs-lookup"><span data-stu-id="ea413-144">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="ea413-145">Die Namen von Tupelelementen können von den Variablen abgeleitet werden, die zum Initialisieren der Tupel in C# 7.1 verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ea413-145">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="ea413-146">Weitere Informationen über dieses Feature finden Sie im Artikel [Tupel](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="ea413-146">You can learn more about this feature in the [Tuples](../tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="ea413-147">Musterabgleich für generische Typparameter</span><span class="sxs-lookup"><span data-stu-id="ea413-147">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="ea413-148">Ab C# 7.1 kann der Musterausdruck für `is` und das `switch`-Typmuster den Typ eines generischen Typparameters haben.</span><span class="sxs-lookup"><span data-stu-id="ea413-148">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="ea413-149">Dies kann sehr nützlich sein, wenn Sie Typen überprüfen, die entweder `struct`- oder `class`-Typen sein können, und Sie Boxing vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="ea413-149">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="ea413-150">Generierung der Referenzassembly</span><span class="sxs-lookup"><span data-stu-id="ea413-150">Reference assembly generation</span></span>

<span data-ttu-id="ea413-151">Es gibt zwei neue Compileroptionen, die *Assemblys nur für Referenzen* generieren: [-refout](../language-reference/compiler-options/refout-compiler-option.md) und [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ea413-151">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="ea413-152">In den verlinkten Artikeln werden diese Optionen und Referenzassemblys ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea413-152">The linked articles explain these options and reference assemblies in more detail.</span></span>

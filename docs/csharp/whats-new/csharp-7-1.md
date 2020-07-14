---
title: Neues in C# 7.1
description: Eine Übersicht der neuen Features in C# 7.1
ms.date: 04/09/2019
ms.openlocfilehash: fe6e49eb01e24a27bc7970900c05150378ab194a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174769"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="4d767-103">Neues in C# 7.1</span><span class="sxs-lookup"><span data-stu-id="4d767-103">What's new in C# 7.1</span></span>

<span data-ttu-id="4d767-104">C# 7.1 ist die erste Punktversion der C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="4d767-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="4d767-105">Das bedeutet schnellere Releaserhythmen für die Sprache.</span><span class="sxs-lookup"><span data-stu-id="4d767-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="4d767-106">Sie können die neuen Features früher benutzen, im Idealfall sobald ein neues Feature bereit ist.</span><span class="sxs-lookup"><span data-stu-id="4d767-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="4d767-107">Mit C# 7.1 wird die Fähigkeit hinzugefügt, den Compiler so zu konfigurieren, dass er einer bestimmten Version der Sprache entspricht.</span><span class="sxs-lookup"><span data-stu-id="4d767-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="4d767-108">Damit können Sie die Entscheidung, Tools upzugraden, von der Entscheidung unterscheiden, Upgrades für Sprachversionen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="4d767-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="4d767-109">Mit C# 7.1 wird ein Konfigurationselement zum [Auswählen der Sprachversion](../language-reference/configure-language-version.md), drei neue Sprachfeatures und neues Compilerverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4d767-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="4d767-110">Die neuen Sprachfeatures in diesem Release umfassen:</span><span class="sxs-lookup"><span data-stu-id="4d767-110">The new language features in this release are:</span></span>

- [<span data-ttu-id="4d767-111">`async` `Main`-Methode</span><span class="sxs-lookup"><span data-stu-id="4d767-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="4d767-112">Der Einstiegspunkt für eine Anwendung kann über den Modifizierer `async` verfügen.</span><span class="sxs-lookup"><span data-stu-id="4d767-112">The entry point for an application can have the `async` modifier.</span></span>
- [<span data-ttu-id="4d767-113">`default`Literale Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4d767-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="4d767-114">Sie können literale Standardausdrücke in Standardwertausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4d767-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
- [<span data-ttu-id="4d767-115">Abgeleitete Tupelelementnamen</span><span class="sxs-lookup"><span data-stu-id="4d767-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="4d767-116">Die Namen von Tupelelementen können in den meisten Fällen von der Initialisierung eines Tupels abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4d767-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
- [<span data-ttu-id="4d767-117">Musterabgleich für generische Typparameter</span><span class="sxs-lookup"><span data-stu-id="4d767-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="4d767-118">Sie können Musterabgleichsausdrücke für Variablen verwenden, deren Typ ein generischer Typparameter ist.</span><span class="sxs-lookup"><span data-stu-id="4d767-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="4d767-119">Außerdem verfügt der Compiler über die zwei Optionen `-refout` und `-refonly`, mit denen die [Generierung der Referenzassembly](#reference-assembly-generation) gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="4d767-119">Finally, the compiler has two options `-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="4d767-120">Sie müssen [die Sprachversion des Compilers konfigurieren](../language-reference/configure-language-version.md) und die Version auswählen, um die neuesten Features in einer Punktversion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d767-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

<span data-ttu-id="4d767-121">Dieser Artikel enthält im Folgenden eine Übersicht über die einzelnen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4d767-121">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="4d767-122">Sie werden die Hintergründe jeder einzelnen Funktion erfahren.</span><span class="sxs-lookup"><span data-stu-id="4d767-122">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="4d767-123">Sie werden die Syntax erlernen.</span><span class="sxs-lookup"><span data-stu-id="4d767-123">You'll learn the syntax.</span></span> <span data-ttu-id="4d767-124">Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:</span><span class="sxs-lookup"><span data-stu-id="4d767-124">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="4d767-125">Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.</span><span class="sxs-lookup"><span data-stu-id="4d767-125">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="4d767-126">Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.</span><span class="sxs-lookup"><span data-stu-id="4d767-126">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="4d767-127">Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.</span><span class="sxs-lookup"><span data-stu-id="4d767-127">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="4d767-128">Führen Sie aus `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="4d767-128">Run `dotnet try`.</span></span>

## <a name="async-main"></a><span data-ttu-id="4d767-129">Async Main</span><span class="sxs-lookup"><span data-stu-id="4d767-129">Async main</span></span>

<span data-ttu-id="4d767-130">Mithilfe einer *async main*-Methode können Sie `await` in Ihrer `Main`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d767-130">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="4d767-131">Vorher hätten Sie das Folgende schreiben müssen:</span><span class="sxs-lookup"><span data-stu-id="4d767-131">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="4d767-132">Nun können Sie das Folgende schreiben:</span><span class="sxs-lookup"><span data-stu-id="4d767-132">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="4d767-133">Wenn Ihr Programm keinen Exitcode zurückgibt, können Sie eine `Main`-Methode deklarieren, die einen <xref:System.Threading.Tasks.Task> zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="4d767-133">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="4d767-134">Ausführliche Informationen finden Sie unter [Async Main](../programming-guide/main-and-command-args/index.md) im Programmierhandbuch.</span><span class="sxs-lookup"><span data-stu-id="4d767-134">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="4d767-135">Literale Standardausdrücke</span><span class="sxs-lookup"><span data-stu-id="4d767-135">Default literal expressions</span></span>

<span data-ttu-id="4d767-136">Literale Standardausdrücke sind eine Erweiterung von Ausdrücken mit Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4d767-136">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="4d767-137">Diese Ausdrücke initialisieren eine Variable auf dem Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4d767-137">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="4d767-138">Dort, wo Sie vorher das Folgende geschrieben haben:</span><span class="sxs-lookup"><span data-stu-id="4d767-138">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="4d767-139">Können Sie nun den Typ weglassen, der auf der rechten Seite der Initialisierung steht.</span><span class="sxs-lookup"><span data-stu-id="4d767-139">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="4d767-140">Weitere Informationen finden Sie im Abschnitt [Standardliteral](../language-reference/operators/default.md#default-literal) des Artikels zum [default-Operator](../language-reference/operators/default.md).</span><span class="sxs-lookup"><span data-stu-id="4d767-140">For more information, see the [default literal](../language-reference/operators/default.md#default-literal) section of the [default operator](../language-reference/operators/default.md) article.</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="4d767-141">Abgeleitete Tupelelementnamen</span><span class="sxs-lookup"><span data-stu-id="4d767-141">Inferred tuple element names</span></span>

<span data-ttu-id="4d767-142">Dieses Feature ist eine kleine Erweiterung des Tupelfeatures, das in C# 7.0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="4d767-142">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="4d767-143">Wenn Sie einen Tupel initialisieren, sind die Variablen, die für die rechte Seite der Zuweisung verwendet werden, oft dieselben, wie die Namen, die Sie den Tupelelementen geben möchten.</span><span class="sxs-lookup"><span data-stu-id="4d767-143">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="4d767-144">Die Namen von Tupelelementen können von den Variablen abgeleitet werden, die zum Initialisieren der Tupel in C# 7.1 verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4d767-144">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="4d767-145">Weitere Informationen zu diesem Feature finden Sie im Artikel [Tupeltypen](../language-reference/builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="4d767-145">You can learn more about this feature in the [Tuple types](../language-reference/builtin-types/value-tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="4d767-146">Musterabgleich für generische Typparameter</span><span class="sxs-lookup"><span data-stu-id="4d767-146">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="4d767-147">Ab C# 7.1 kann der Musterausdruck für `is` und das `switch`-Typmuster den Typ eines generischen Typparameters haben.</span><span class="sxs-lookup"><span data-stu-id="4d767-147">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="4d767-148">Dies kann sehr nützlich sein, wenn Sie Typen überprüfen, die entweder `struct`- oder `class`-Typen sein können, und Sie Boxing vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="4d767-148">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="4d767-149">Generierung der Referenzassembly</span><span class="sxs-lookup"><span data-stu-id="4d767-149">Reference assembly generation</span></span>

<span data-ttu-id="4d767-150">Es gibt zwei neue Compileroptionen, die *Assemblys nur für Referenzen* generieren: [-refout](../language-reference/compiler-options/refout-compiler-option.md) und [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4d767-150">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="4d767-151">In den verlinkten Artikeln werden diese Optionen und Referenzassemblys ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d767-151">The linked articles explain these options and reference assemblies in more detail.</span></span>

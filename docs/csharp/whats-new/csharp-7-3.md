---
title: Neuerungen in C# 7.3
description: Eine Übersicht der neuen Features in C# 7.3
ms.date: 05/16/2018
ms.openlocfilehash: 768070ead2b180d5f4491ac87be6c248c39e9944
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397780"
---
# <a name="whats-new-in-c-73"></a><span data-ttu-id="8b3e4-103">Neuerungen in C# 7.3</span><span class="sxs-lookup"><span data-stu-id="8b3e4-103">What's new in C# 7.3</span></span>

<span data-ttu-id="8b3e4-104">Es gibt zwei Hauptdesigns in der C# 7.3-Version.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-104">There are two main themes to the C# 7.3 release.</span></span> <span data-ttu-id="8b3e4-105">Ein Design bietet Features, die ermöglichen, dass sicherer Code so leistungsfähig ist wie unsicherer Code.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-105">One theme provides features that enable safe code to be as performant as unsafe code.</span></span> <span data-ttu-id="8b3e4-106">Das zweite Design bietet inkrementelle Verbesserungen vorhandener Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-106">The second theme provides incremental improvements to existing features.</span></span> <span data-ttu-id="8b3e4-107">Darüber hinaus wurden in diesem Release neue Compileroptionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-107">In addition, new compiler options were added in this release.</span></span>

<span data-ttu-id="8b3e4-108">Die folgenden neuen Features unterstützen das Design der besseren Leistung für sicheren Code:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-108">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="8b3e4-109">Sie können ohne Anheften auf feste Felder zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-109">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="8b3e4-110">Sie können `ref` erneut lokale Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-110">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="8b3e4-111">Sie können Initialisierer auf `stackalloc`-Arrays verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-111">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="8b3e4-112">Sie können `fixed`-Anweisungen mit jedem Typ verwenden, der ein Muster unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-112">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="8b3e4-113">Sie können zusätzliche generische Einschränkungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-113">You can use additional generic constraints.</span></span>

<span data-ttu-id="8b3e4-114">Die folgenden Verbesserungen wurden an vorhandenen Features vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-114">The following enhancements were made to existing features:</span></span>

- <span data-ttu-id="8b3e4-115">Sie können `==` und `!=` mit Tupeltypen testen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-115">You can test `==` and `!=` with tuple types.</span></span>
- <span data-ttu-id="8b3e4-116">Sie können Ausdrucksvariablen an mehreren Standorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-116">You can use expression variables in more locations.</span></span>
- <span data-ttu-id="8b3e4-117">Sie können Attribute dem Unterstützungsfeld automatisch implementierter Eigenschaften anfügen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-117">You may attach attributes to the backing field of auto-implemented properties.</span></span>
- <span data-ttu-id="8b3e4-118">Die Auflösung der Methode, wenn Argumente um `in` differieren, wurde verbessert.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-118">Method resolution when arguments differ by `in` has been improved.</span></span>
- <span data-ttu-id="8b3e4-119">Die Auflösung von Überladungen weist jetzt weniger mehrdeutige Fälle auf.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-119">Overload resolution now has fewer ambiguous cases.</span></span>

<span data-ttu-id="8b3e4-120">Die neuen Compileroptionen lauten:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-120">The new compiler options are:</span></span>

- <span data-ttu-id="8b3e4-121">`-publicsign`, um das Signieren von Assemblys durch Open Source Software (OSS) zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-121">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="8b3e4-122">`-pathmap`, um eine Zuordnung für Quellverzeichnisse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-122">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="8b3e4-123">Der übrige Teil dieses Artikels enthält Informationen und Links, über die Sie mehr zu den einzelnen Verbesserungen erfahren.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-123">The remainder of this article provides details and links to learn more about each of the improvements.</span></span> <span data-ttu-id="8b3e4-124">Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-124">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="8b3e4-125">Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-125">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="8b3e4-126">Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-126">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="8b3e4-127">Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-127">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="8b3e4-128">Führen Sie aus `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-128">Run `dotnet try`.</span></span>

## <a name="enabling-more-efficient-safe-code"></a><span data-ttu-id="8b3e4-129">Ermöglichen von effizienterem sicherem Code</span><span class="sxs-lookup"><span data-stu-id="8b3e4-129">Enabling more efficient safe code</span></span>

<span data-ttu-id="8b3e4-130">Sie sollten C#-Code sicher schreiben können, der so leistungsstark ist wie unsicherer Code.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-130">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="8b3e4-131">Sicherer Code vermeidet Fehlerklassen, z.B. Pufferüberläufe, verirrte Zeiger und andere Fehler beim Arbeitsspeicherzugriff.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-131">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="8b3e4-132">Diese neuen Features erweitern die Funktionen des überprüfbaren sicheren Codes.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-132">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="8b3e4-133">Schreiben Sie mithilfe sicherer Konstrukte mehr Code.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-133">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="8b3e4-134">Diese Features erleichtern dies.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-134">These features make that easier.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="8b3e4-135">Indizieren von `fixed`-Feldern erfordert kein Anheften</span><span class="sxs-lookup"><span data-stu-id="8b3e4-135">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="8b3e4-136">Betrachten Sie diese Struktur:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-136">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="8b3e4-137">In früheren Versionen von C# mussten Sie eine Variable für den Zugriff auf eine der ganzen Zahlen anheften, die Teil von `myFixedField` sind.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-137">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="8b3e4-138">Der folgende Code wird kompiliert, ohne die Variable `p` in einer separaten `fixed`-Anweisung anzuheften:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-138">Now, the following code compiles without pinning the variable `p` inside a separate `fixed` statement:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="8b3e4-139">Die Variable `p` greift auf ein Element in `myFixedField` zu.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-139">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="8b3e4-140">Sie müssen keine separate `int*`-Variable deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-140">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="8b3e4-141">Beachten Sie, dass Sie immer noch einen `unsafe`-Kontext benötigen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-141">Note that you still need an `unsafe` context.</span></span> <span data-ttu-id="8b3e4-142">In früheren Versionen von C# müssen Sie einen zweiten festen Zeiger deklarieren:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-142">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="8b3e4-143">Weitere Informationen finden Sie im Artikel zur [`fixed`-Anweisung](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-143">For more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="ref-local-variables-may-be-reassigned"></a><span data-ttu-id="8b3e4-144">Lokale `ref`-Variablen werden möglicherweise neu zugewiesen</span><span class="sxs-lookup"><span data-stu-id="8b3e4-144">`ref` local variables may be reassigned</span></span>

<span data-ttu-id="8b3e4-145">Lokale `ref`-Variablen werden jetzt möglicherweise neu zugewiesen, um nach der Initialisierung auf verschiedene Instanzen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-145">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="8b3e4-146">Der folgende Code wird jetzt kompiliert:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-146">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="8b3e4-147">Weitere Informationen finden Sie im Artikel zu [`ref`-Rückgaben und lokalen `ref`-Variablen](../programming-guide/classes-and-structs/ref-returns.md) und im Artikel zu [`foreach`](../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-147">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="8b3e4-148">`stackalloc`-Arrays unterstützen Initialisierer</span><span class="sxs-lookup"><span data-stu-id="8b3e4-148">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="8b3e4-149">Sie konnten schon die Werte für Elemente in einem Array angeben, wenn Sie es initialisierten:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-149">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="8b3e4-150">Nun kann die gleiche Syntax auf Arrays angewendet werden, die mit `stackalloc` deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-150">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="8b3e4-151">Weitere Informationen finden Sie im Artikel zum [`stackalloc`-Operator](../language-reference/operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-151">For more information, see the [`stackalloc` operator](../language-reference/operators/stackalloc.md) article.</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="8b3e4-152">Weitere Typen unterstützen die `fixed`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8b3e4-152">More types support the `fixed` statement</span></span>

<span data-ttu-id="8b3e4-153">Die `fixed`-Anweisung unterstützte eine begrenzte Anzahl von Typen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-153">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="8b3e4-154">Ab C# 7.3 kann jeder Typ, der eine `GetPinnableReference()`-Methode enthält, die eine `ref T` oder `ref readonly T` zurückgibt, `fixed` sein.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-154">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="8b3e4-155">Dieses Feature hinzuzufügen, bedeutet, dass `fixed` mit <xref:System.Span%601?displayProperty=nameWithType> und verwandten Typen genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-155">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="8b3e4-156">Weitere Informationen finden Sie im Artikel zur [`fixed`-Anweisung](../language-reference/keywords/fixed-statement.md) in der Sprachreferenz.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-156">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="8b3e4-157">Verbesserte generische Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8b3e4-157">Enhanced generic constraints</span></span>

<span data-ttu-id="8b3e4-158">Sie können jetzt Typ <xref:System.Enum?displayProperty=nameWithType> oder <xref:System.Delegate?displayProperty=nameWithType> als Basisklasseneinschränkungen für einen Typparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-158">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="8b3e4-159">Sie können auch die neue `unmanaged`-Einschränkung nutzen, um anzugeben, dass der Typparameter ein **nicht verwalteter Typ** sein muss.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-159">You can also use the new `unmanaged` constraint, to specify that a type parameter must be an **unmanaged type**.</span></span> <span data-ttu-id="8b3e4-160">Ein **nicht verwalteter Typ** ist ein Typ, der kein Verweistyp ist und keinen Verweistyp auf Schachtelungsebenen aufweist.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-160">An **unmanaged type** is a type that isn't a reference type and doesn't contain any reference type at any level of nesting.</span></span>

<span data-ttu-id="8b3e4-161">Weitere Informationen finden Sie in den Artikeln zu generischen [`where`-Einschränkungen](../language-reference/keywords/where-generic-type-constraint.md) und [Einschränkungen für Typparameter](../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-161">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="8b3e4-162">Das Hinzufügen dieser Einschränkungen zu vorhandenen Typen ist eine [inkompatible Änderung](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-162">Adding these constraints to existing types is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="8b3e4-163">Geschlossene generische Typen erfüllen diese neuen Einschränkungen möglicherweise nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-163">Closed generic types may no longer meet these new constraints.</span></span>

## <a name="make-existing-features-better"></a><span data-ttu-id="8b3e4-164">Vorhandene Features besser machen</span><span class="sxs-lookup"><span data-stu-id="8b3e4-164">Make existing features better</span></span>

<span data-ttu-id="8b3e4-165">Das zweite Design enthält Verbesserungen der Features in der Sprache.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-165">The second theme provides improvements to features in the language.</span></span> <span data-ttu-id="8b3e4-166">Die Produktivität dieser Features wird verbessert, wenn sie in C# geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-166">These features improve productivity when writing C#.</span></span>

### <a name="tuples-support--and-"></a><span data-ttu-id="8b3e4-167">Tupel unterstützen `==` und `!=`</span><span class="sxs-lookup"><span data-stu-id="8b3e4-167">Tuples support `==` and `!=`</span></span>

<span data-ttu-id="8b3e4-168">Die C#-Tupeltypen unterstützen jetzt `==` und `!=`.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-168">The C# tuple types now support `==` and `!=`.</span></span> <span data-ttu-id="8b3e4-169">Weitere Informationen finden Sie unter dem [Gleichheit](../tuples.md#equality-and-tuples) behandelnden Abschnitt im Artikel zu [Tupeln](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-169">For more information, see the section covering [equality](../tuples.md#equality-and-tuples) in the article on [tuples](../tuples.md).</span></span>

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a><span data-ttu-id="8b3e4-170">Anfügen von Attributen zu den Unterstützungsfeldern für automatisch implementierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8b3e4-170">Attach attributes to the backing fields for auto-implemented properties</span></span>

<span data-ttu-id="8b3e4-171">Diese Syntax wird jetzt unterstützt:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-171">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="8b3e4-172">Das Attribut `SomeThingAboutFieldAttribute` wird auf das vom Compiler generierte Unterstützungsfeld für `SomeProperty` angewendet.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-172">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="8b3e4-173">Weitere Informationen finden Sie unter [attributes](../programming-guide/concepts/attributes/index.md) im C#-Programmierhandbuch.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-173">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

### <a name="in-method-overload-resolution-tiebreaker"></a><span data-ttu-id="8b3e4-174">Tiebreaker zur Auflösung der Überladung der `in`-Methode</span><span class="sxs-lookup"><span data-stu-id="8b3e4-174">`in` method overload resolution tiebreaker</span></span>

<span data-ttu-id="8b3e4-175">Wenn der `in`-Argumentmodifizierer hinzugefügt wurde, verursachten diese beiden Methoden eine Mehrdeutigkeit:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-175">When the `in` argument modifier was added, these two methods would cause an ambiguity:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="8b3e4-176">Jetzt ist die Überladung des Werts „by“ (im vorherigen Beispiel an erster Stelle) besser als die „by readonly“-Verweisversion.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-176">Now, the by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="8b3e4-177">Um die Version mit dem readonly-Verweisargument aufzurufen, müssen Sie auch den `in`-Modifizierer beim Aufrufen der Methode einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-177">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

> [!NOTE]
> <span data-ttu-id="8b3e4-178">Dies wurde als Fehlerkorrektur implementiert.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-178">This was implemented as a bug fix.</span></span> <span data-ttu-id="8b3e4-179">Dies ist selbst mit der Sprachversion „7.2“ nicht mehr mehrdeutig.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-179">This no longer is ambiguous even with the language version set to "7.2".</span></span>

<span data-ttu-id="8b3e4-180">Weitere Informationen finden Sie im Artikel zum [`in`-Parametermodifizierer](../language-reference/keywords/in-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-180">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="extend-expression-variables-in-initializers"></a><span data-ttu-id="8b3e4-181">Erweitern der Ausdrucksvariablen in Initialisierern</span><span class="sxs-lookup"><span data-stu-id="8b3e4-181">Extend expression variables in initializers</span></span>

<span data-ttu-id="8b3e4-182">Die in C# 7.0 zum Zulassen von `out`-Variablendeklarationen hinzugefügte Syntax wurde erweitert, sodass sie Feldinitialisierer, Eigenschafteninitialisierer, Konstruktorinitialisierer und Abfrageklauseln umfasst.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-182">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="8b3e4-183">Sie ermöglicht Code wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-183">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a><span data-ttu-id="8b3e4-184">Verbesserte Überladungskandidaten</span><span class="sxs-lookup"><span data-stu-id="8b3e4-184">Improved overload candidates</span></span>

<span data-ttu-id="8b3e4-185">In jedem Release werden die Überladungsauflösungsregeln für Situationen aktualisiert, in denen mehrdeutige Methodenaufrufe eine „naheliegende“ Auswahlmöglichkeit haben.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-185">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="8b3e4-186">In diesem Release werden drei neue Regeln hinzufügt, damit der Compiler die naheliegende Auswahlmöglichkeit nutzt:</span><span class="sxs-lookup"><span data-stu-id="8b3e4-186">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="8b3e4-187">Wenn eine Methodengruppe sowohl Instanz- als auch statische Member enthält, verwirft der Compiler die Instanzmember, wenn die Methode ohne Instanzempfänger oder -kontext aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-187">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="8b3e4-188">Der Compiler verwirft die statischen Member, wenn die Methode mit einem Instanzempfänger aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-188">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="8b3e4-189">Wenn kein Empfänger vorhanden ist, bezieht der Compiler nur statische Member in einen statischen Kontext ein – andernfalls sowohl statische als auch Instanzmember.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-189">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="8b3e4-190">Wenn unklar ist, ob der Empfänger eine Instanz oder ein Typ ist, bezieht der Compiler beides ein.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-190">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="8b3e4-191">Ein statischer Kontext, wo ein impliziter `this`-Instanzempfänger nicht verwendet werden kann, enthält den Text von Membern, wo kein `this` definiert ist, z.B. statische Member, sowie Orte, an denen `this` nicht verwendet werden kann, z.B. Feld- und Konstruktorinitialisierer.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-191">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="8b3e4-192">Wenn eine Methodengruppe einige generische Methoden enthält, deren Typargumente ihre Einschränkungen nicht erfüllen, werden diese Member aus dem Satz von Kandidaten entfernt.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-192">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="8b3e4-193">Für eine Methodengruppenkonvertierung werden Kandidatenmethoden, deren Rückgabetyp nicht mit dem des Delegaten übereinstimmt, aus dem Satz entfernt.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-193">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="8b3e4-194">Sie werden diese Änderung bemerken, da Sie weniger Compilerfehler für mehrdeutige Methodenüberladungen finden werden, wenn Sie sicher sind, welche Methode besser ist.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-194">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="8b3e4-195">Neue Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="8b3e4-195">New compiler options</span></span>

<span data-ttu-id="8b3e4-196">Neue Compileroptionen unterstützen neue Build- und DevOpsszenarien für C#-Programme.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-196">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="8b3e4-197">Öffentliche oder Open Source-Signierung</span><span class="sxs-lookup"><span data-stu-id="8b3e4-197">Public or Open Source signing</span></span>

<span data-ttu-id="8b3e4-198">Die `-publicsign`-Compileroption weist den Compiler an, die Assembly mit einem öffentlichen Schlüssel zu signieren.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-198">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="8b3e4-199">Die Assembly wird als signiert markiert, aber die Signatur wird dem öffentlichen Schlüssel entnommen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-199">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="8b3e4-200">Mit dieser Option können Sie signierte Assemblys aus Open Source-Projekten mit einem öffentlichen Schlüssel erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-200">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="8b3e4-201">Weitere Informationen finden Sie im Artikel zur [Compileroption „-publicsign“](../language-reference/compiler-options/publicsign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-201">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="8b3e4-202">pathmap</span><span class="sxs-lookup"><span data-stu-id="8b3e4-202">pathmap</span></span>

<span data-ttu-id="8b3e4-203">Die `-pathmap`-Compileroption weist den Compiler an, Quellpfade aus der Buildumgebung mit zugeordneten Quellpfaden zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-203">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="8b3e4-204">Die `-pathmap`-Option bestimmt den Quellpfad, der vom Compiler in PDB-Dateien oder für <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="8b3e4-204">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="8b3e4-205">Weitere Informationen finden Sie im Artikel zur [Compileroption „-pathmap“](../language-reference/compiler-options/pathmap-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="8b3e4-205">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>

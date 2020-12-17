---
ms.openlocfilehash: 97fab784acac4331894547eea27fc21b485597fb
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366881"
---
### <a name="passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation"></a><span data-ttu-id="fdd19-101">Das Übergeben von GroupCollection an IEnumerable\<T> akzeptierende Erweiterungsmethoden erfordert Vermeidung von Mehrdeutigkeit</span><span class="sxs-lookup"><span data-stu-id="fdd19-101">Passing GroupCollection to extension methods taking IEnumerable\<T> requires disambiguation</span></span>

<span data-ttu-id="fdd19-102">Wenn Sie eine Erweiterungsmethode aufrufen, die `IEnumerable<T>` für <xref:System.Text.RegularExpressions.GroupCollection> akzeptiert, müssen Sie den Typ mithilfe einer Umwandlung verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="fdd19-102">When calling an extension method that takes an `IEnumerable<T>` on a <xref:System.Text.RegularExpressions.GroupCollection>, you must disambiguate the type using a cast.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fdd19-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="fdd19-103">Change description</span></span>

<span data-ttu-id="fdd19-104">Ab .NET Core 3.0 implementiert <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> neben anderen Typen wie `IEnumerable<Group>` auch `IEnumerable<KeyValuePair<String,Group>>`.</span><span class="sxs-lookup"><span data-stu-id="fdd19-104">Starting in .NET Core 3.0, <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> implements `IEnumerable<KeyValuePair<String,Group>>` in addition to the other types it implements, including `IEnumerable<Group>`.</span></span> <span data-ttu-id="fdd19-105">Dies resultiert in einer Mehrdeutigkeit, wenn eine Erweiterungsmethode aufgerufen wird, die <xref:System.Collections.Generic.IEnumerable%601> akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="fdd19-105">This results in ambiguity when calling an extension method that takes an <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="fdd19-106">Wenn Sie eine solche Erweiterungsmethode für eine <xref:System.Text.RegularExpressions.GroupCollection>-Instanz aufrufen, z. B. <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, wird der folgende Compilerfehler angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fdd19-106">If you call such an extension method on a <xref:System.Text.RegularExpressions.GroupCollection> instance, for example, <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, you'll see the following compiler error:</span></span>

<span data-ttu-id="fdd19-107">**CS1061: „GroupCollection“ enthält keine Definition für „Count“, und es konnte keine Erweiterungsmethode „Count“ gefunden werden, die ein erstes Argument vom Typ „GroupCollection“ akzeptiert (möglicherweise fehlt eine using-Anweisung oder ein Assemblyverweis).**</span><span class="sxs-lookup"><span data-stu-id="fdd19-107">**CS1061: 'GroupCollection' does not contain a definition for 'Count' and no accessible extension method 'Count' accepting a first argument of type 'GroupCollection' could be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="fdd19-108">In vorherigen Versionen von .NET gab es keine Mehrdeutigkeit und keinen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="fdd19-108">In previous versions of .NET, there was no ambiguity and no compiler error.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fdd19-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="fdd19-109">Version introduced</span></span>

<span data-ttu-id="fdd19-110">3.0</span><span class="sxs-lookup"><span data-stu-id="fdd19-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="fdd19-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="fdd19-111">Reason for change</span></span>

<span data-ttu-id="fdd19-112">Hierbei handelt es sich um einen [unbeabsichtigten Breaking Change](https://github.com/dotnet/corefx/pull/30077).</span><span class="sxs-lookup"><span data-stu-id="fdd19-112">This was an [unintentional breaking change](https://github.com/dotnet/corefx/pull/30077).</span></span> <span data-ttu-id="fdd19-113">Da diese Funktionsweise seit einiger Zeit besteht, ist keine Änderung geplant.</span><span class="sxs-lookup"><span data-stu-id="fdd19-113">Because it has been like this for some time, we don't plan to revert it.</span></span> <span data-ttu-id="fdd19-114">Außerdem würde eine solche Änderung selbst zu einem Breaking Change führen.</span><span class="sxs-lookup"><span data-stu-id="fdd19-114">In addition, such a change would itself be breaking.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fdd19-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="fdd19-115">Recommended action</span></span>

<span data-ttu-id="fdd19-116">Heben Sie für <xref:System.Text.RegularExpressions.GroupCollection>-Instanzen die Mehrdeutigkeit von Aufrufen der Erweiterungsmethoden auf, die `IEnumerable<T>` mit einer Umwandlung akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="fdd19-116">For <xref:System.Text.RegularExpressions.GroupCollection> instances, disambiguate calls to extension methods that accept an `IEnumerable<T>` with a cast.</span></span>

```csharp
// Without a cast - causes CS1061.
match.Groups.Count(_ => true)

// With a disambiguating cast.
((IEnumerable<Group>)m.Groups).Count(_ => true);
```

#### <a name="category"></a><span data-ttu-id="fdd19-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="fdd19-117">Category</span></span>

<span data-ttu-id="fdd19-118">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="fdd19-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fdd19-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fdd19-119">Affected APIs</span></span>

<span data-ttu-id="fdd19-120">Dies betrifft alle Erweiterungsmethoden, die <xref:System.Collections.Generic.IEnumerable%601> akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="fdd19-120">Any extension method that accepts an <xref:System.Collections.Generic.IEnumerable%601> is affected.</span></span> <span data-ttu-id="fdd19-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fdd19-121">For example:</span></span>

- <xref:System.Collections.Immutable.ImmutableArray.ToImmutableArray%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableList.ToImmutableList%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet%2A?displayProperty=fullName>
- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A?displayProperty=fullName>
- <span data-ttu-id="fdd19-122">Die meisten `System.Linq.Enumerable`-Methoden, z. B. <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="fdd19-122">Most of the `System.Linq.Enumerable` methods, for example, <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></span></span>
- <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=fullName>
- <xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>

<!--

#### Affected APIs

- ``M:System.Collections.Immutable.ImmutableArray.ToImmutableArray``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary`
- `Overload:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet`
- ``M:System.Collections.Immutable.ImmutableList.ToImmutableList``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary`
- `Overload:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet`
- `Overload:System.Data.DataTableExtensions.CopyToDataTable`
- `Overload:System.Linq.Enumerable.Count`
- `Overload:System.Linq.ParallelEnumerable.AsParallel`
- `Overload:System.Linq.Queryable.AsQueryable`

-->

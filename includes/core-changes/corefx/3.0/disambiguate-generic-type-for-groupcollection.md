---
ms.openlocfilehash: 97fab784acac4331894547eea27fc21b485597fb
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366881"
---
### <a name="passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation"></a>Das Übergeben von GroupCollection an IEnumerable\<T> akzeptierende Erweiterungsmethoden erfordert Vermeidung von Mehrdeutigkeit

Wenn Sie eine Erweiterungsmethode aufrufen, die `IEnumerable<T>` für <xref:System.Text.RegularExpressions.GroupCollection> akzeptiert, müssen Sie den Typ mithilfe einer Umwandlung verdeutlichen.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Core 3.0 implementiert <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> neben anderen Typen wie `IEnumerable<Group>` auch `IEnumerable<KeyValuePair<String,Group>>`. Dies resultiert in einer Mehrdeutigkeit, wenn eine Erweiterungsmethode aufgerufen wird, die <xref:System.Collections.Generic.IEnumerable%601> akzeptiert. Wenn Sie eine solche Erweiterungsmethode für eine <xref:System.Text.RegularExpressions.GroupCollection>-Instanz aufrufen, z. B. <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, wird der folgende Compilerfehler angezeigt:

**CS1061: „GroupCollection“ enthält keine Definition für „Count“, und es konnte keine Erweiterungsmethode „Count“ gefunden werden, die ein erstes Argument vom Typ „GroupCollection“ akzeptiert (möglicherweise fehlt eine using-Anweisung oder ein Assemblyverweis).**

In vorherigen Versionen von .NET gab es keine Mehrdeutigkeit und keinen Compilerfehler.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="reason-for-change"></a>Grund für die Änderung

Hierbei handelt es sich um einen [unbeabsichtigten Breaking Change](https://github.com/dotnet/corefx/pull/30077). Da diese Funktionsweise seit einiger Zeit besteht, ist keine Änderung geplant. Außerdem würde eine solche Änderung selbst zu einem Breaking Change führen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Heben Sie für <xref:System.Text.RegularExpressions.GroupCollection>-Instanzen die Mehrdeutigkeit von Aufrufen der Erweiterungsmethoden auf, die `IEnumerable<T>` mit einer Umwandlung akzeptieren.

```csharp
// Without a cast - causes CS1061.
match.Groups.Count(_ => true)

// With a disambiguating cast.
((IEnumerable<Group>)m.Groups).Count(_ => true);
```

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

Dies betrifft alle Erweiterungsmethoden, die <xref:System.Collections.Generic.IEnumerable%601> akzeptieren. Beispiel:

- <xref:System.Collections.Immutable.ImmutableArray.ToImmutableArray%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableList.ToImmutableList%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet%2A?displayProperty=fullName>
- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A?displayProperty=fullName>
- Die meisten `System.Linq.Enumerable`-Methoden, z. B. <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName>.
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

---
title: Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5
description: Erfahren Sie mehr über Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5 unter Windows.
ms.date: 12/07/2020
ms.openlocfilehash: a53c36b31785fb43c0aa5f5040042abb6d40031a
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851750"
---
# <a name="behavior-changes-when-comparing-strings-on-net-5"></a><span data-ttu-id="c296e-103">Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5</span><span class="sxs-lookup"><span data-stu-id="c296e-103">Behavior changes when comparing strings on .NET 5+</span></span>

<span data-ttu-id="c296e-104">In NET 5.0 wird eine Änderung des Runtimeverhaltens eingeführt, aufgrund derer Globalisierungs-APIs auf allen unterstützten Plattformen [jetzt standardmäßig ICU verwenden](../../core/compatibility/globalization/5.0/icu-globalization-api.md).</span><span class="sxs-lookup"><span data-stu-id="c296e-104">.NET 5.0 introduces a runtime behavioral change where globalization APIs [now use ICU by default](../../core/compatibility/globalization/5.0/icu-globalization-api.md) across all supported platforms.</span></span> <span data-ttu-id="c296e-105">Dies ist eine Abkehr von früheren Versionen von .NET Core und .NET Framework, die bei Ausführung unter Windows die NLS-Funktionalität (National Language Support) des Betriebssystems nutzen.</span><span class="sxs-lookup"><span data-stu-id="c296e-105">This is a departure from earlier versions of .NET Core and from .NET Framework, which utilize the operating system's national language support (NLS) functionality when running on Windows.</span></span> <span data-ttu-id="c296e-106">Weitere Informationen zu diesen Änderungen, einschließlich Kompatibilitätsschalter, mit denen die Verhaltensänderung rückgängig gemacht werden kann, finden Sie unter [.NET-Globalisierung und ICU](../globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="c296e-106">For more information on these changes, including compatibility switches that can revert the behavior change, see [.NET globalization and ICU](../globalization-localization/globalization-icu.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c296e-107">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="c296e-107">Reason for change</span></span>

<span data-ttu-id="c296e-108">Diese Änderung wurde eingeführt, um das Globalisierungsverhalten von .NET in allen unterstützten Betriebssystemen zu vereinheitlichen.</span><span class="sxs-lookup"><span data-stu-id="c296e-108">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="c296e-109">Darüber hinaus können Anwendungen ihre eigenen Globalisierungsbibliotheken bündeln, anstatt von den in das Betriebssystem integrierten Bibliotheken abhängig zu sein.</span><span class="sxs-lookup"><span data-stu-id="c296e-109">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the OS's built-in libraries.</span></span> <span data-ttu-id="c296e-110">Weitere Informationen finden Sie in der [ Breaking Change-Benachrichtigung](../../core/compatibility/globalization/5.0/icu-globalization-api.md).</span><span class="sxs-lookup"><span data-stu-id="c296e-110">For more information, see [the breaking change notification](../../core/compatibility/globalization/5.0/icu-globalization-api.md).</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="c296e-111">Verhaltensunterschiede</span><span class="sxs-lookup"><span data-stu-id="c296e-111">Behavioral differences</span></span>

<span data-ttu-id="c296e-112">Wenn Sie Funktionen wie `string.IndexOf(string)` verwenden, ohne die Überladung aufzurufen, die das Argument <xref:System.StringComparison> verwendet, könnten Sie beabsichtigen, eine *ordinale Suche* durchzuführen. Doch stattdessen greifen Sie unbeabsichtigt auf eine Abhängigkeit von kulturspezifischem Verhalten zurück.</span><span class="sxs-lookup"><span data-stu-id="c296e-112">If you use functions like `string.IndexOf(string)` without calling the overload that takes a <xref:System.StringComparison> argument, you might intend to perform an *ordinal* search, but instead you inadvertently take a dependency on culture-specific behavior.</span></span> <span data-ttu-id="c296e-113">Da NLS und ICU unterschiedliche Logik in ihren linguistischen Vergleichsfunktionen implementieren, können die Ergebnisse von Methoden wie `string.IndexOf(string)` unerwartete Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c296e-113">Since NLS and ICU implement different logic in their linguistic comparers, the results of methods like `string.IndexOf(string)` can return unexpected values.</span></span>

<span data-ttu-id="c296e-114">Dies kann sich sogar dort manifestieren, wo Sie nicht unbedingt erwarten, dass Globalisierungsfunktionen aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="c296e-114">This can manifest itself even in places where you aren't always expecting globalization facilities to be active.</span></span> <span data-ttu-id="c296e-115">Beispielsweise kann der folgende Code abhängig von der aktuellen Runtime eine andere Antwort liefern.</span><span class="sxs-lookup"><span data-stu-id="c296e-115">For example, the following code can produce a different answer depending on the current runtime.</span></span>

```cs
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);

// The snippet prints:
//
// '6' when running on .NET Framework (Windows)
// '6' when running on .NET Core 2.x - 3.x (Windows)
// '-1' when running on .NET 5 (Windows)
// '-1' when running on .NET Core 2.x - 3.x or .NET 5 (non-Windows)
// '6' when running on .NET Core 2.x or .NET 5 (in invariant mode)
```

## <a name="guard-against-unexpected-behavior"></a><span data-ttu-id="c296e-116">Schutz vor unerwartetem Verhalten</span><span class="sxs-lookup"><span data-stu-id="c296e-116">Guard against unexpected behavior</span></span>

<span data-ttu-id="c296e-117">Dieser Abschnitt enthält zwei Optionen für den Umgang mit unerwarteten Verhaltensänderungen in .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="c296e-117">This section provides two options for dealing with unexpected behavior changes in .NET 5.0.</span></span>

### <a name="enable-code-analyzers"></a><span data-ttu-id="c296e-118">Aktivieren von Codeanalysetools</span><span class="sxs-lookup"><span data-stu-id="c296e-118">Enable code analyzers</span></span>

<span data-ttu-id="c296e-119">[Codeanalysetools](../../fundamentals/code-analysis/overview.md) können möglicherweise fehlerhafte Aufrufstellen erkennen.</span><span class="sxs-lookup"><span data-stu-id="c296e-119">[Code analyzers](../../fundamentals/code-analysis/overview.md) can detect possibly buggy call sites.</span></span> <span data-ttu-id="c296e-120">Es wird empfohlen, die Analysetools von .NET Compiler Platform (Roslyn) in Ihrem Projekt zu aktivieren, um unerwünschtem Verhalten vorzubeugen.</span><span class="sxs-lookup"><span data-stu-id="c296e-120">To help guard against any surprising behaviors, we recommend enabling .NET compiler platform (Roslyn) analyzers in your project.</span></span> <span data-ttu-id="c296e-121">Mithilfe dieser Analysetools kann Code gekennzeichnet werden, der versehentlich eine linguistische Vergleichsfunktion verwendet, obwohl wahrscheinlich eine ordinale Vergleichsfunktion beabsichtigt war.</span><span class="sxs-lookup"><span data-stu-id="c296e-121">The analyzers help flag code that might inadvertently be using a linguistic comparer when an ordinal comparer was likely intended.</span></span> <span data-ttu-id="c296e-122">Die folgenden Regeln sind bei der Kennzeichnung dieser Probleme nützlich:</span><span class="sxs-lookup"><span data-stu-id="c296e-122">The following rules should help flag these issues:</span></span>

- [<span data-ttu-id="c296e-123">CA1307: "StringComparison" zur Verdeutlichung angeben</span><span class="sxs-lookup"><span data-stu-id="c296e-123">CA1307: Specify StringComparison for clarity</span></span>](../../fundamentals/code-analysis/quality-rules/ca1307.md)
- [<span data-ttu-id="c296e-124">CA1309: Ordinal-StringComparison verwenden.</span><span class="sxs-lookup"><span data-stu-id="c296e-124">CA1309: Use ordinal StringComparison</span></span>](../../fundamentals/code-analysis/quality-rules/ca1309.md)
- [<span data-ttu-id="c296e-125">CA1310: "StringComparison" für Richtigkeit angeben</span><span class="sxs-lookup"><span data-stu-id="c296e-125">CA1310: Specify StringComparison for correctness</span></span>](../../fundamentals/code-analysis/quality-rules/ca1310.md)

<span data-ttu-id="c296e-126">Diese spezifischen Regeln sind standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c296e-126">These specific rules aren't enabled by default.</span></span> <span data-ttu-id="c296e-127">Legen Sie die folgenden Eigenschaften in Ihrer Projektdatei fest, um diese zu aktivieren und Verstöße wie Buildfehler anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="c296e-127">To enable them and show any violations as build errors, set the following properties in your project file:</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
  <WarningsAsErrors>$(WarningsAsErrors);CA1307;CA1309;CA1310</WarningsAsErrors>
</PropertyGroup>
```

<span data-ttu-id="c296e-128">Der folgende Ausschnitt ist ein Codebeispiel, das die relevanten Warnungen oder Fehlermeldungen des Codeanalysetools erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c296e-128">The following snippet shows examples of code that produces the relevant code analyzer warnings or errors.</span></span>

```cs
//
// Potentially incorrect code - answer might vary based on locale.
//
string s = GetString();
// Produces analyzer warning CA1310 for string; CA1307 matches on char ','
int idx = s.IndexOf(",");
Console.WriteLine(idx);

//
// Corrected code - matches the literal substring ",".
//
string s = GetString();
int idx = s.IndexOf(",", StringComparison.Ordinal);
Console.WriteLine(idx);

//
// Corrected code (alternative) - searches for the literal ',' character.
//
string s = GetString();
int idx = s.IndexOf(',');
Console.WriteLine(idx);
```

<span data-ttu-id="c296e-129">Wenn Sie eine sortierte Zeichenfolgensammlung instanziieren oder eine vorhandene auf Zeichenfolgen basierende Sammlung sortieren, geben Sie in ähnlicher Weise eine explizite Vergleichsfunktion an.</span><span class="sxs-lookup"><span data-stu-id="c296e-129">Similarly, when instantiating a sorted collection of strings or sorting an existing string-based collection, specify an explicit comparer.</span></span>

```cs
//
// Potentially incorrect code - behavior might vary based on locale.
//
SortedSet<string> mySet = new SortedSet<string>();
List<string> list = GetListOfStrings();
list.Sort();

//
// Corrected code - uses ordinal sorting; doesn't vary by locale.
//
SortedSet<string> mySet = new SortedSet<string>(StringComparer.Ordinal);
List<string> list = GetListOfStrings();
list.Sort(StringComparer.Ordinal);
```

### <a name="revert-back-to-nls-behaviors"></a><span data-ttu-id="c296e-130">Zurücksetzen auf NLS-Verhaltensweisen</span><span class="sxs-lookup"><span data-stu-id="c296e-130">Revert back to NLS behaviors</span></span>

<span data-ttu-id="c296e-131">Um .NET 5-Anwendungen bei Ausführung unter Windows auf ältere NLS-Verhaltensweisen zurückzusetzen, folgen Sie den Anweisungen unter [.NET-Globalisierung und ICU](../globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="c296e-131">To revert .NET 5 applications back to older NLS behaviors when running on Windows, follow the steps in [.NET Globalization and ICU](../globalization-localization/globalization-icu.md).</span></span> <span data-ttu-id="c296e-132">Dieser anwendungsweite Kompatibilitätsschalter muss auf Anwendungsebene festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c296e-132">This application-wide compatibility switch must be set at the application level.</span></span> <span data-ttu-id="c296e-133">Einzelne Bibliotheken können dieses Verhalten nicht aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c296e-133">Individual libraries cannot opt-in or opt-out of this behavior.</span></span>

> [!TIP]
> <span data-ttu-id="c296e-134">Es wird dringend empfohlen, die Codeanalyseregeln [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md) und [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) zu aktivieren, um die Codepflege zu verbessern und eventuell vorhandene latente Fehler aufzudecken.</span><span class="sxs-lookup"><span data-stu-id="c296e-134">We strongly recommend you enable the [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md), and [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) code analysis rules to help improve code hygiene and discover any existing latent bugs.</span></span> <span data-ttu-id="c296e-135">Weitere Informationen finden Sie unter [Aktivieren von Codeanalysetools](#enable-code-analyzers).</span><span class="sxs-lookup"><span data-stu-id="c296e-135">For more information, see [Enable code analyzers](#enable-code-analyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c296e-136">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c296e-136">Affected APIs</span></span>

<span data-ttu-id="c296e-137">Die meisten .NET-Anwendungen werden aufgrund der Änderungen in .NET 5.0 nicht auf unerwartete Verhaltensweisen stoßen.</span><span class="sxs-lookup"><span data-stu-id="c296e-137">Most .NET applications won't encounter any unexpected behaviors due to the changes in .NET 5.0.</span></span> <span data-ttu-id="c296e-138">Aufgrund der Anzahl der betroffenen APIs und ihrer Bedeutung für das gesamte .NET-Ökosystem sollten Sie sich jedoch bewusst sein, dass .NET 5.0 das Potenzial hat, unerwünschte Verhaltensweisen einzuführen oder latente Fehler offenzulegen, die bereits in Ihrer Anwendung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c296e-138">However, due to the number of affected APIs and how foundational these APIs are to the wider .NET ecosystem, you should be aware of the potential for .NET 5.0 to introduce unwanted behaviors or to expose latent bugs that already exist in your application.</span></span>

<span data-ttu-id="c296e-139">Zu den betroffenen APIs gehören u. a.:</span><span class="sxs-lookup"><span data-stu-id="c296e-139">The affected APIs include:</span></span>

- <xref:System.String.Compare%2A?displayProperty=fullName>
- <xref:System.String.EndsWith%2A?displayProperty=fullName>
- <xref:System.String.IndexOf%2A?displayProperty=fullName>
- <xref:System.String.StartsWith%2A?displayProperty=fullName>
- <xref:System.String.ToLower%2A?displayProperty=fullName>
- <xref:System.String.ToLowerInvariant%2A?displayProperty=fullName>
- <xref:System.String.ToUpper%2A?displayProperty=fullName>
- <xref:System.String.ToUpperInvariant%2A?displayProperty=fullName>
- <span data-ttu-id="c296e-140"><xref:System.Globalization.TextInfo?displayProperty=fullName> (die meisten Member)</span><span class="sxs-lookup"><span data-stu-id="c296e-140"><xref:System.Globalization.TextInfo?displayProperty=fullName> (most members)</span></span>
- <span data-ttu-id="c296e-141"><xref:System.Globalization.CompareInfo?displayProperty=fullName> (die meisten Member)</span><span class="sxs-lookup"><span data-stu-id="c296e-141"><xref:System.Globalization.CompareInfo?displayProperty=fullName> (most members)</span></span>
- <span data-ttu-id="c296e-142"><xref:System.Array.Sort%2A?displayProperty=fullName> (beim Sortieren von Zeichenfolgenarrays)</span><span class="sxs-lookup"><span data-stu-id="c296e-142"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting arrays of strings)</span></span>
- <span data-ttu-id="c296e-143"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (wenn die Listenelemente Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="c296e-143"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="c296e-144"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="c296e-144"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="c296e-145"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="c296e-145"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="c296e-146"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (wenn die Gruppe Zeichenfolgen enthält)</span><span class="sxs-lookup"><span data-stu-id="c296e-146"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

> [!NOTE]
> <span data-ttu-id="c296e-147">Dies ist keine vollständige Liste der betroffenen APIs.</span><span class="sxs-lookup"><span data-stu-id="c296e-147">This is not an exhaustive list of affected APIs.</span></span>

<span data-ttu-id="c296e-148">Alle der oben genannten APIs verwenden standardmäßig *linguistische* Zeichenfolgensuchen und -vergleiche unter Verwendung der [aktuellen Kultur](xref:System.Threading.Thread.CurrentCulture) des Threads.</span><span class="sxs-lookup"><span data-stu-id="c296e-148">All of the above APIs use *linguistic* string searching and comparison using the thread's [current culture](xref:System.Threading.Thread.CurrentCulture), by default.</span></span> <span data-ttu-id="c296e-149">Die Unterschiede zwischen  *linguistischen* und *ordinalen* Suchen und Vergleichen werden im Abschnitt [Vergleich ordinaler und linguistischer Suchen und Vergleiche](#ordinal-vs-linguistic-search-and-comparison) vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="c296e-149">The differences between *linguistic* and *ordinal* search and comparison are called out in the [Ordinal vs. linguistic search and comparison](#ordinal-vs-linguistic-search-and-comparison).</span></span>

<span data-ttu-id="c296e-150">Da ICU linguistische Zeichenfolgevergleiche anders als NLS implementiert, können Windows-basierte Anwendungen, bei denen ein Upgrade von einer früheren Version von .NET Core oder .NET Framework auf .NET 5.0 erfolgt und die eine der betroffenen APIs aufrufen, feststellen, dass die APIs beginnen, ein anderes Verhalten zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="c296e-150">Because ICU implements linguistic string comparisons differently from NLS, Windows-based applications that upgrade to .NET 5.0 from an earlier version of .NET Core or .NET Framework and that call one of the affected APIs may notice that the APIs begin exhibiting different behaviors.</span></span>

### <a name="exceptions"></a><span data-ttu-id="c296e-151">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="c296e-151">Exceptions</span></span>

* <span data-ttu-id="c296e-152">Wenn eine API einen expliziten Parameter des Typs `StringComparison` oder `CultureInfo` akzeptiert, setzt dieser Parameter das Standardverhalten der API außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="c296e-152">If an API accepts an explicit `StringComparison` or `CultureInfo` parameter, that parameter overrides the API's default behavior.</span></span>
* <span data-ttu-id="c296e-153">`System.String`-Member, bei denen der erste Parameter den Typ `char` hat (z. B. <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>), verwenden die ordinale Suche, es sei denn, der Aufrufer übergibt ein explizites `StringComparison`-Argument, das `CurrentCulture[IgnoreCase]` oder `InvariantCulture[IgnoreCase]` angibt.</span><span class="sxs-lookup"><span data-stu-id="c296e-153">`System.String` members where the first parameter is of type `char` (for example, <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>) use ordinal searching, unless the caller passes an explicit `StringComparison` argument that specifies `CurrentCulture[IgnoreCase]` or `InvariantCulture[IgnoreCase]`.</span></span>

<span data-ttu-id="c296e-154">Eine detailliertere Analyse des Standardverhaltens der einzelnen <xref:System.String>-APIs finden Sie im Abschnitt [Standardsuch- und -Vergleichstypen](#default-search-and-comparison-types).</span><span class="sxs-lookup"><span data-stu-id="c296e-154">For a more detailed analysis of the default behavior of each <xref:System.String> API, see the [Default search and comparison types](#default-search-and-comparison-types) section.</span></span>

## <a name="ordinal-vs-linguistic-search-and-comparison"></a><span data-ttu-id="c296e-155">Vergleich ordinaler und linguistischer Suchen und Vergleiche</span><span class="sxs-lookup"><span data-stu-id="c296e-155">Ordinal vs. linguistic search and comparison</span></span>

<span data-ttu-id="c296e-156">Bei *ordinalen* Suchen und Vergleichen (die auch als *nicht linguistisch* bezeichnet werden) wird eine Zeichenfolge in ihre einzelnen `char`-Elemente zerlegt und eine zeichenweise Suche bzw. ein zeichenweiser Vergleich durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c296e-156">*Ordinal* (also known as *non-linguistic*) search and comparison decomposes a string into its individual `char` elements and performs a char-by-char search or comparison.</span></span> <span data-ttu-id="c296e-157">Beispielsweise werden die Zeichenfolgen `"dog"` und `"dog"` von der Vergleichsfunktion `Ordinal` als *gleich* bewertet, da die beiden Zeichenfolgen aus exakt der gleichen Folge von Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="c296e-157">For example, the strings `"dog"` and `"dog"` compare as *equal* under an `Ordinal` comparer, since the two strings consist of the exact same sequence of chars.</span></span> <span data-ttu-id="c296e-158">Allerdings werden `"dog"` und `"Dog"` von der Vergleichsfunktion `Ordinal` als *ungleich* bewertet, da sie nicht aus der exakt gleichen Folge von Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="c296e-158">However, `"dog"` and `"Dog"` compare as *not equal* under an `Ordinal` comparer, because they don't consist of the exact same sequence of chars.</span></span> <span data-ttu-id="c296e-159">Das heißt, dass der Codepunkt von `'D'` in Großschreibung `U+0044` vor dem Codepunkt von `'d'` in Kleinschreibung `U+0064` vorkommt, was bedeutet dass `"dog"` vor `"Dog"` sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="c296e-159">That is, uppercase `'D'`'s code point `U+0044` occurs before lowercase `'d'`'s code point `U+0064`, resulting in `"dog"` sorting before `"Dog"`.</span></span>

<span data-ttu-id="c296e-160">Die Vergleichsfunktion `OrdinalIgnoreCase` arbeitet weiterhin zeichenweise, berücksichtigt aber beim Durchführen des Vorgangs keine Unterschiede zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="c296e-160">An `OrdinalIgnoreCase` comparer still operates on a char-by-char basis, but it eliminates case differences while performing the operation.</span></span> <span data-ttu-id="c296e-161">Bei der Vergleichsfunktion `OrdinalIgnoreCase` werden die Zeichenpaare `'d'` und `'D'` als *gleich* bewertet. Gleiches gilt für die Zeichenpaare `'á'` und `'Á'`.</span><span class="sxs-lookup"><span data-stu-id="c296e-161">Under an `OrdinalIgnoreCase` comparer, the char pairs `'d'` and `'D'` compare as *equal*, as do the char pairs `'á'` and `'Á'`.</span></span> <span data-ttu-id="c296e-162">Aber das Zeichen ohne Akzent `'a'` wird als *ungleich* dem Zeichen mit Akzent `'á'` bewertet.</span><span class="sxs-lookup"><span data-stu-id="c296e-162">But the unaccented char `'a'` compares as *not equal* to the accented char `'á'`.</span></span>

<span data-ttu-id="c296e-163">Einige Beispiele hierfür finden Sie in der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="c296e-163">Some examples of this are provided in the following table:</span></span>

| <span data-ttu-id="c296e-164">Zeichenfolge 1</span><span class="sxs-lookup"><span data-stu-id="c296e-164">String 1</span></span> | <span data-ttu-id="c296e-165">Zeichenfolge 2</span><span class="sxs-lookup"><span data-stu-id="c296e-165">String 2</span></span> | <span data-ttu-id="c296e-166">Vergleich mit `Ordinal`</span><span class="sxs-lookup"><span data-stu-id="c296e-166">`Ordinal` comparison</span></span> | <span data-ttu-id="c296e-167">Vergleich mit `OrdinalIgnoreCase`</span><span class="sxs-lookup"><span data-stu-id="c296e-167">`OrdinalIgnoreCase` comparison</span></span> |
|---|---|---|---|
| `"dog"` | `"dog"` | <span data-ttu-id="c296e-168">equal</span><span class="sxs-lookup"><span data-stu-id="c296e-168">equal</span></span> | <span data-ttu-id="c296e-169">equal</span><span class="sxs-lookup"><span data-stu-id="c296e-169">equal</span></span> |
| `"dog"` | `"Dog"` | <span data-ttu-id="c296e-170">Ungleich</span><span class="sxs-lookup"><span data-stu-id="c296e-170">not equal</span></span> | <span data-ttu-id="c296e-171">equal</span><span class="sxs-lookup"><span data-stu-id="c296e-171">equal</span></span> |
| `"resume"` | `"Resume"` | <span data-ttu-id="c296e-172">Ungleich</span><span class="sxs-lookup"><span data-stu-id="c296e-172">not equal</span></span> | <span data-ttu-id="c296e-173">equal</span><span class="sxs-lookup"><span data-stu-id="c296e-173">equal</span></span> |
| `"resume"` | `"résumé"` | <span data-ttu-id="c296e-174">Ungleich</span><span class="sxs-lookup"><span data-stu-id="c296e-174">not equal</span></span> | <span data-ttu-id="c296e-175">Ungleich</span><span class="sxs-lookup"><span data-stu-id="c296e-175">not equal</span></span> |

<span data-ttu-id="c296e-176">Unicode erlaubt auch Zeichenfolgen mit mehreren verschiedenen InMemory-Darstellungen.</span><span class="sxs-lookup"><span data-stu-id="c296e-176">Unicode also allows strings to have several different in-memory representations.</span></span> <span data-ttu-id="c296e-177">Zum Beispiel kann ein e mit Accent aigu (é) auf zwei mögliche Arten dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="c296e-177">For example, an e-acute (é) can be represented in two possible ways:</span></span>

* <span data-ttu-id="c296e-178">Als einzelnes Literalzeichen `'é'` (auch als `'\u00E9'` geschrieben).</span><span class="sxs-lookup"><span data-stu-id="c296e-178">A single literal `'é'` character (also written as `'\u00E9'`).</span></span>
* <span data-ttu-id="c296e-179">Als Literalzeichen ohne Akzent `'e'`, gefolgt von einer Kombination von Akzentmodifiziererzeichen `'\u0301'`.</span><span class="sxs-lookup"><span data-stu-id="c296e-179">A literal unaccented `'e'` character, followed by a combining accent modifier character `'\u0301'`.</span></span>

<span data-ttu-id="c296e-180">Dies bedeutet, dass die folgenden _vier_ Zeichenfolgen bei der Anzeige alle in `"résumé"` resultieren, auch wenn ihre Bestandteile unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="c296e-180">This means that the following _four_ strings all result in `"résumé"` when displayed, even though their constituent pieces are different.</span></span> <span data-ttu-id="c296e-181">Die Zeichenfolgen verwenden eine Kombination aus Literalzeichen (`'é'`) oder Literalzeichen ohne Akzent (`'e'`) sowie den kombinierenden Akzentmodifizierer (`'\u0301'`).</span><span class="sxs-lookup"><span data-stu-id="c296e-181">The strings use a combination of literal `'é'` characters or literal unaccented `'e'` characters plus the combining accent modifier `'\u0301'`.</span></span>

* `"r\u00E9sum\u00E9"`
* `"r\u00E9sume\u0301"`
* `"re\u0301sum\u00E9"`
* `"re\u0301sume\u0301"`

<span data-ttu-id="c296e-182">Bei einer ordinalen Vergleichsfunktion wird keine dieser Zeichenfolgen als gleich zueinander bewertet.</span><span class="sxs-lookup"><span data-stu-id="c296e-182">Under an ordinal comparer, none of these strings compare as equal to each other.</span></span> <span data-ttu-id="c296e-183">Das liegt daran, dass sie alle unterschiedliche zugrunde liegende Zeichenfolgen enthalten, auch wenn sie beim Rendern auf dem Bildschirm alle identisch aussehen.</span><span class="sxs-lookup"><span data-stu-id="c296e-183">This is because they all contain different underlying char sequences, even though when they're rendered to the screen, they all look the same.</span></span>

<span data-ttu-id="c296e-184">Bei der Ausführung des Vorgangs `string.IndexOf(..., StringComparison.Ordinal)` sucht die Runtime nach einer exakten Teilzeichenfolgenübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="c296e-184">When performing a `string.IndexOf(..., StringComparison.Ordinal)` operation, the runtime looks for an exact substring match.</span></span> <span data-ttu-id="c296e-185">Die Ergebnisse sind wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c296e-185">The results are as follows.</span></span>

```cs
Console.WriteLine("resume".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("resume".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
```

<span data-ttu-id="c296e-186">Ordinale Such- und Vergleichsroutinen werden grundsätzlich nicht durch die Einstellung der Kultur des aktuellen Threads beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="c296e-186">Ordinal search and comparison routines are never affected by the current thread's culture setting.</span></span>

<span data-ttu-id="c296e-187">*Linguistische* Such- und Vergleichsroutinen zerlegen eine Zeichenfolge in *Sortierungselemente* und wenden Suchen oder Vergleiche auf diese Elemente an.</span><span class="sxs-lookup"><span data-stu-id="c296e-187">*Linguistic* search and comparison routines decompose a string into *collation elements* and perform searches or comparisons on these elements.</span></span> <span data-ttu-id="c296e-188">Es gibt nicht notwendigerweise eine 1:1-Zuordnung zwischen den Zeichen einer Zeichenfolge und den zugehörigen Sortierungselementen.</span><span class="sxs-lookup"><span data-stu-id="c296e-188">There's not necessarily a 1:1 mapping between a string's characters and its constituent collation elements.</span></span> <span data-ttu-id="c296e-189">Beispielsweise kann eine Zeichenfolge der Länge 2 nur aus einem einzigen Sortierungselement bestehen.</span><span class="sxs-lookup"><span data-stu-id="c296e-189">For example, a string of length 2 may consist of only a single collation element.</span></span> <span data-ttu-id="c296e-190">Wenn zwei Zeichenfolgen linguistisch sinnvoll verglichen werden, prüft die Vergleichsfunktion, ob die Sortierungselemente der beiden Zeichenfolgen die gleiche semantische Bedeutung haben, auch wenn die Literalzeichen der Zeichenfolge unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="c296e-190">When two strings are compared in a linguistic-aware fashion, the comparer checks whether the two strings' collation elements have the same semantic meaning, even if the string's literal characters are different.</span></span>

<span data-ttu-id="c296e-191">Betrachten Sie nochmals die Zeichenfolge `"résumé"` und ihre vier Darstellungen.</span><span class="sxs-lookup"><span data-stu-id="c296e-191">Consider again the string `"résumé"` and its four different representations.</span></span> <span data-ttu-id="c296e-192">In der folgenden Tabelle ist jede Darstellung in ihre Sortierungselemente unterteilt.</span><span class="sxs-lookup"><span data-stu-id="c296e-192">The following table shows each representation broken down into its collation elements.</span></span>

| <span data-ttu-id="c296e-193">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c296e-193">String</span></span> | <span data-ttu-id="c296e-194">Als Sortierungselemente</span><span class="sxs-lookup"><span data-stu-id="c296e-194">As collation elements</span></span> |
|---|---|
| `"r\u00E9sum\u00E9"` | `"r" + "\u00E9" + "s" + "u" + "m" + "\u00E9"` |
| `"r\u00E9sume\u0301"` | `"r" + "\u00E9" + "s" + "u" + "m" + "e\u0301"` |
| `"re\u0301sum\u00E9"` | `"r" + "e\u0301" + "s" + "u" + "m" + "\u00E9"` |
| `"re\u0301sume\u0301"` | `"r" + "e\u00E9" + "s" + "u" + "m" + "e\u0301"` |

<span data-ttu-id="c296e-195">Ein Sortierungselement entspricht im Großen und Ganzen dem, was Leser als ein einzelnes oder eine Gruppe von Zeichen ansehen würden.</span><span class="sxs-lookup"><span data-stu-id="c296e-195">A collation element corresponds loosely to what readers would think of as a single character or cluster of characters.</span></span> <span data-ttu-id="c296e-196">Es ist konzeptionell einem [Graphemhaufen](character-encoding-introduction.md#grapheme-clusters) ähnlich, umfasst aber einen etwas größeren Schirm.</span><span class="sxs-lookup"><span data-stu-id="c296e-196">It's conceptually similar to a [grapheme cluster](character-encoding-introduction.md#grapheme-clusters) but encompasses a somewhat larger umbrella.</span></span>

<span data-ttu-id="c296e-197">Bei einer linguistischen Vergleichsfunktion sind exakte Übereinstimmungen nicht notwendig.</span><span class="sxs-lookup"><span data-stu-id="c296e-197">Under a linguistic comparer, exact matches aren't necessary.</span></span> <span data-ttu-id="c296e-198">Stattdessen werden Sortierungselemente auf Grundlage ihrer semantischen Bedeutung verglichen.</span><span class="sxs-lookup"><span data-stu-id="c296e-198">Collation elements are instead compared based on their semantic meaning.</span></span> <span data-ttu-id="c296e-199">Beispielsweise bewertet eine linguistische Vergleichsfunktion die Teilzeichenketten `"\u00E9"` und `"e\u0301"` als gleich, da beide semantisch „ein kleingeschriebenes e mit einem Akut“ bedeuten.</span><span class="sxs-lookup"><span data-stu-id="c296e-199">For example, a linguistic comparer treats the substrings `"\u00E9"` and `"e\u0301"` as equal since they both semantically mean "a lowercase e with an acute accent modifier."</span></span> <span data-ttu-id="c296e-200">Dies ermöglicht es der `IndexOf`-Methode, die Teilzeichenfolge `"e\u0301"` innerhalb einer größeren Zeichenfolge zu finden, die die semantisch äquivalente Teilzeichenfolge `"\u00E9"` enthält (siehe das folgende Codebeispiel).</span><span class="sxs-lookup"><span data-stu-id="c296e-200">This allows the `IndexOf` method to match the substring `"e\u0301"` within a larger string that contains the semantically equivalent substring `"\u00E9"`, as shown in the following code sample.</span></span>

```cs
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e")); // prints '-1' (not found)
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e\u00E9")); // prints '1'
Console.WriteLine("\u00E9".IndexOf("e\u00E9")); // prints '0'
```

<span data-ttu-id="c296e-201">Dies hat zur Folge, dass zwei Zeichenfolgen unterschiedlicher Länge bei einem linguistischen Vergleich als gleich bewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="c296e-201">As a consequence of this, two strings of different lengths may compare as equal if a linguistic comparison is used.</span></span> <span data-ttu-id="c296e-202">Aufrufer sollten darauf achten, keine von Groß-/Kleinschreibung geprägte Logik zu verwenden, die die Zeichenfolgenlänge in solchen Szenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="c296e-202">Callers should take care not to special-case logic that deals with string length in such scenarios.</span></span>

<span data-ttu-id="c296e-203">*Kulturabhängige* Such- und Vergleichsroutinen sind eine spezielle Form linguistischer Such- und Vergleichsroutinen.</span><span class="sxs-lookup"><span data-stu-id="c296e-203">*Culture-aware* search and comparison routines are a special form of linguistic search and comparison routines.</span></span> <span data-ttu-id="c296e-204">Bei einer kulturabhängigen Vergleichsfunktion wird das Konzept eines Sortierungselements um Informationen erweitert, die für die jeweilige Kultur spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="c296e-204">Under a culture-aware comparer, the concept of a collation element is extended to include information specific to the specified culture.</span></span>

<span data-ttu-id="c296e-205">Wenn z. B. [ im ungarischen Alphabet](https://en.wikipedia.org/wiki/Hungarian_alphabet) die beiden Zeichen \<dz\> hintereinander stehen, werden sie als eigener Buchstabe betrachtet, der sich sowohl von \<d\> als auch von \<z\> unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="c296e-205">For example, [in the Hungarian alphabet](https://en.wikipedia.org/wiki/Hungarian_alphabet), when the two characters \<dz\> appear back-to-back, they are considered their own unique letter distinct from either \<d\> or \<z\>.</span></span> <span data-ttu-id="c296e-206">Das bedeutet, dass wenn \<dz\> in einer Zeichenfolge vorkommt, eine kulturabhängige ungarische Vergleichsfunktion diese als einzelnes Sortierungselement behandelt.</span><span class="sxs-lookup"><span data-stu-id="c296e-206">This means that when \<dz\> is seen in a string, a Hungarian culture-aware comparer treats it as a single collation element.</span></span>

| <span data-ttu-id="c296e-207">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c296e-207">String</span></span> | <span data-ttu-id="c296e-208">Als Sortierungselemente</span><span class="sxs-lookup"><span data-stu-id="c296e-208">As collation elements</span></span> | <span data-ttu-id="c296e-209">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c296e-209">Remarks</span></span> |
|---|---|---|
| `"endz"` | `"e" + "n" + "d" + "z"` | <span data-ttu-id="c296e-210">(bei einer standardmäßigen linguistischen Vergleichsfunktion)</span><span class="sxs-lookup"><span data-stu-id="c296e-210">(using a standard linguistic comparer)</span></span> |
| `"endz"` | `"e" + "n" + "dz"` | <span data-ttu-id="c296e-211">(bei einer von der ungarischen Kultur abhängigen Vergleichsfunktion)</span><span class="sxs-lookup"><span data-stu-id="c296e-211">(using a Hungarian culture-aware comparer)</span></span> |

<span data-ttu-id="c296e-212">Bei Verwendung einer von der ungarischen Kultur abhängigen Vergleichsfunktion bedeutet dies, dass die Zeichenfolge `"endz"` *nicht* mit der Teilzeichenfolge `"z"` endet, da <\dz\> und <\z\> als Sortierungselemente mit unterschiedlicher semantischer Bedeutung anzusehen sind.</span><span class="sxs-lookup"><span data-stu-id="c296e-212">When using a Hungarian culture-aware comparer, this means that the string `"endz"` *does not* end with the substring `"z"`, as <\dz\> and <\z\> are considered collation elements with different semantic meaning.</span></span>

```cs
// Set thread culture to Hungarian
CultureInfo.CurrentCulture = CultureInfo.GetCultureInfo("hu-HU");
Console.WriteLine("endz".EndsWith("z")); // Prints 'False'

// Set thread culture to invariant culture
CultureInfo.CurrentCulture = CultureInfo.InvariantCulture;
Console.WriteLine("endz".EndsWith("z")); // Prints 'True'
```

> [!NOTE]
>
> - <span data-ttu-id="c296e-213">Verhalten: Sprach- und kulturabhängige Vergleichsfunktionen können von Zeit zu Zeit Verhaltensanpassungen erfahren.</span><span class="sxs-lookup"><span data-stu-id="c296e-213">Behavior: Linguistic and culture-aware comparers can undergo behavioral adjustments from time to time.</span></span> <span data-ttu-id="c296e-214">Sowohl ICU als auch die ältere Windows-Funktion NLS werden aktualisiert, um dem Wandel der Sprachen in der Welt Rechnung zu tragen.</span><span class="sxs-lookup"><span data-stu-id="c296e-214">Both ICU and the older Windows NLS facility are updated to account for how world languages change.</span></span> <span data-ttu-id="c296e-215">Weitere Informationen finden Sie im Blogbeitrag [Locale (Culture) Data Churn](/archive/blogs/shawnste/locale-culture-data-churn).</span><span class="sxs-lookup"><span data-stu-id="c296e-215">For more information, see the blog post [Locale (culture) data churn](/archive/blogs/shawnste/locale-culture-data-churn).</span></span> <span data-ttu-id="c296e-216">Das Verhalten der *ordinalen* Vergleichsfunktion ändert sich nicht, da sie exakte bitweise Such- und Vergleichsvorgänge durchführt.</span><span class="sxs-lookup"><span data-stu-id="c296e-216">The *Ordinal* comparer's behavior will never change since it performs exact bitwise searching and comparison.</span></span> <span data-ttu-id="c296e-217">Das Verhalten der Vergleichsfunktion *OrdinalIgnoreCase* kann sich jedoch ändern, wenn Unicode immer mehr Zeichensätze umfasst und Lücken in vorhandenen Daten zu Groß- und Kleinschreibung schließt.</span><span class="sxs-lookup"><span data-stu-id="c296e-217">However, the *OrdinalIgnoreCase* comparer's behavior may change as Unicode grows to encompass more character sets and corrects omissions in existing casing data.</span></span>
> - <span data-ttu-id="c296e-218">Verwendung: Die Vergleichsfunktionen `StringComparison.InvariantCulture` und `StringComparison.InvariantCultureIgnoreCase` sind linguistische Vergleichsfunktionen, die nicht kulturabhängig sind.</span><span class="sxs-lookup"><span data-stu-id="c296e-218">Usage: The comparers `StringComparison.InvariantCulture` and `StringComparison.InvariantCultureIgnoreCase` are linguistic comparers that are not culture-aware.</span></span> <span data-ttu-id="c296e-219">Das heißt, dass diese Vergleichsfunktionen Konzepte wie den Akzentbuchstaben é mit mehreren möglichen zugrunde liegenden Darstellungen verstehen und dass alle diese Darstellungen gleich behandelt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="c296e-219">That is, these comparers understand concepts such as the accented character é having multiple possible underlying representations, and that all such representations should be treated equal.</span></span> <span data-ttu-id="c296e-220">Nicht kulturabhängige linguistische Vergleichsfunktionen sehen jedoch im Unterschied zu \<d\> oder \<z\> keine besondere Behandlung von \<dz\> vor, wie oben gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c296e-220">But non-culture-aware linguistic comparers won't contain special handling for \<dz\> as distinct from \<d\> or \<z\>, as shown above.</span></span> <span data-ttu-id="c296e-221">Sie enthalten auch keine Behandlung für Sonderfälle wie das deutsche Eszett (ß).</span><span class="sxs-lookup"><span data-stu-id="c296e-221">They also won't special-case characters like the German Eszett (ß).</span></span>

<span data-ttu-id="c296e-222">.NET bietet auch den *invarianten Globalisierungsmodus*.</span><span class="sxs-lookup"><span data-stu-id="c296e-222">.NET also offers the *invariant globalization mode*.</span></span> <span data-ttu-id="c296e-223">Dieser wählbare Modus deaktiviert Codepfade, die sich mit linguistischen Such- und Vergleichsroutinen befassen.</span><span class="sxs-lookup"><span data-stu-id="c296e-223">This opt-in mode disables code paths that deal with linguistic search and comparison routines.</span></span> <span data-ttu-id="c296e-224">In diesem Modus wird bei allen Vorgängen das Verhalten von *Ordinal* oder *OrdinalIgnoreCase* verwendet, und zwar unabhängig davon, welches `CultureInfo`- oder `StringComparison`-Argument der Aufrufer angibt.</span><span class="sxs-lookup"><span data-stu-id="c296e-224">In this mode, all operations use *Ordinal* or *OrdinalIgnoreCase* behaviors, regardless of what `CultureInfo` or `StringComparison` argument the caller provides.</span></span> <span data-ttu-id="c296e-225">Weitere Informationen finden Sie unter [Runtimekonfigurationsoptionen für die Globalisierung](../../core/run-time-config/globalization.md) und [Invarianter Modus für .NET Core-Globalisierung](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c296e-225">For more information, see [Run-time configuration options for globalization](../../core/run-time-config/globalization.md) and [.NET Core Globalization Invariant Mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

<span data-ttu-id="c296e-226">Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET](best-practices-strings.md).</span><span class="sxs-lookup"><span data-stu-id="c296e-226">For more information, see [Best practices for comparing strings in .NET](best-practices-strings.md).</span></span>

## <a name="security-implications"></a><span data-ttu-id="c296e-227">Folgen für die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c296e-227">Security implications</span></span>

<span data-ttu-id="c296e-228">Wenn Ihre Anwendung eine betroffene API zum Filtern verwendet, empfehlen wir, die Codeanalyseregeln CA1307 und CA1309 zu aktivieren, um Stellen ausfindig zu machen, an denen statt einer gewöhnlichen Suche versehentlich eine linguistische Suche verwendet worden sein könnte.</span><span class="sxs-lookup"><span data-stu-id="c296e-228">If your app uses an affected API for filtering, we recommend enabling the CA1307 and CA1309 code analysis rules to help locate places where a linguistic search may have inadvertently been used instead of an ordinal search.</span></span> <span data-ttu-id="c296e-229">Codemuster wie die folgenden können anfällig für Sicherheitslücken sein.</span><span class="sxs-lookup"><span data-stu-id="c296e-229">Code patterns like the following may be susceptible to security exploits.</span></span>

```cs
//
// THIS SAMPLE CODE IS INCORRECT.
// DO NOT USE IT IN PRODUCTION.
//
public bool ContainsHtmlSensitiveCharacters(string input)
{
    if (input.IndexOf("<") >= 0) { return true; }
    if (input.IndexOf("&") >= 0) { return true; }
    return false;
}
```

<span data-ttu-id="c296e-230">Da die `string.IndexOf(string)`-Methode standardmäßig eine linguistische Suche verwendet, ist es möglich, dass eine Zeichenfolge das Literal `'<'` oder Zeichen `'&'` enthält und dass die `string.IndexOf(string)`-Routine `-1` zurückgibt, was darauf hinweist, dass die gesuchte Teilzeichenfolge nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="c296e-230">Because the `string.IndexOf(string)` method uses a linguistic search by default, it's possible for a string to contain a literal `'<'` or `'&'` character and for the `string.IndexOf(string)` routine to return `-1`, indicating that the search substring was not found.</span></span> <span data-ttu-id="c296e-231">Die Codeanalyseregeln CA1307 und CA1309 kennzeichnen solche Aufrufstellen und warnen den Entwickler, dass ein potenzielles Problem vorliegt.</span><span class="sxs-lookup"><span data-stu-id="c296e-231">Code analysis rules CA1307 and CA1309 flag such call sites and alert the developer that there's a potential problem.</span></span>

## <a name="default-search-and-comparison-types"></a><span data-ttu-id="c296e-232">Typen von Standardsuchen und -vergleichen</span><span class="sxs-lookup"><span data-stu-id="c296e-232">Default search and comparison types</span></span>

<span data-ttu-id="c296e-233">Die folgende Tabelle enthält die standardmäßigen Such- und Vergleichstypen für verschiedene Zeichenfolgen und zeichenfolgenähnliche APIs.</span><span class="sxs-lookup"><span data-stu-id="c296e-233">The following table lists the default search and comparison types for various string and string-like APIs.</span></span> <span data-ttu-id="c296e-234">Wenn der Aufrufer einen expliziten `CultureInfo`- oder `StringComparison`-Parameter angibt, wird dieser Parameter gegenüber jeder Standardeinstellung bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="c296e-234">If the caller provides an explicit `CultureInfo` or `StringComparison` parameter, that parameter will be honored over any default.</span></span>

| <span data-ttu-id="c296e-235">API</span><span class="sxs-lookup"><span data-stu-id="c296e-235">API</span></span> | <span data-ttu-id="c296e-236">Standardverhalten</span><span class="sxs-lookup"><span data-stu-id="c296e-236">Default behavior</span></span> | <span data-ttu-id="c296e-237">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c296e-237">Remarks</span></span> |
|---|---|---|
| `string.Compare` | <span data-ttu-id="c296e-238">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-238">CurrentCulture</span></span> | |
| `string.CompareTo` | <span data-ttu-id="c296e-239">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-239">CurrentCulture</span></span> | |
| `string.Contains` | <span data-ttu-id="c296e-240">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-240">Ordinal</span></span> | |
| `string.EndsWith` | <span data-ttu-id="c296e-241">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-241">Ordinal</span></span> | <span data-ttu-id="c296e-242">(wenn der erste Parameter ein `char` ist)</span><span class="sxs-lookup"><span data-stu-id="c296e-242">(when the first parameter is a `char`)</span></span> |
| `string.EndsWith` | <span data-ttu-id="c296e-243">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-243">CurrentCulture</span></span> | <span data-ttu-id="c296e-244">(wenn der erste Parameter ein `string` ist)</span><span class="sxs-lookup"><span data-stu-id="c296e-244">(when the first parameter is a `string`)</span></span> |
| `string.Equals` | <span data-ttu-id="c296e-245">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-245">Ordinal</span></span> | |
| `string.GetHashCode` | <span data-ttu-id="c296e-246">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-246">Ordinal</span></span> | |
| `string.IndexOf` | <span data-ttu-id="c296e-247">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-247">Ordinal</span></span> | <span data-ttu-id="c296e-248">(wenn der erste Parameter ein `char` ist)</span><span class="sxs-lookup"><span data-stu-id="c296e-248">(when the first parameter is a `char`)</span></span> |
| `string.IndexOf` | <span data-ttu-id="c296e-249">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-249">CurrentCulture</span></span> | <span data-ttu-id="c296e-250">(wenn der erste Parameter ein `string` ist)</span><span class="sxs-lookup"><span data-stu-id="c296e-250">(when the first parameter is a `string`)</span></span> |
| `string.IndexOfAny` | <span data-ttu-id="c296e-251">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-251">Ordinal</span></span> | |
| `string.LastIndexOf` | <span data-ttu-id="c296e-252">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-252">Ordinal</span></span> | <span data-ttu-id="c296e-253">(wenn der erste Parameter ein `char` ist)</span><span class="sxs-lookup"><span data-stu-id="c296e-253">(when the first parameter is a `char`)</span></span> |
| `string.LastIndexOf` | <span data-ttu-id="c296e-254">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-254">CurrentCulture</span></span> | <span data-ttu-id="c296e-255">(wenn der erste Parameter ein `string` ist)</span><span class="sxs-lookup"><span data-stu-id="c296e-255">(when the first parameter is a `string`)</span></span> |
| `string.LastIndexOfAny` | <span data-ttu-id="c296e-256">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-256">Ordinal</span></span> | |
| `string.Replace` | <span data-ttu-id="c296e-257">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-257">Ordinal</span></span> | |
| `string.Split` | <span data-ttu-id="c296e-258">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-258">Ordinal</span></span> | |
| `string.StartsWith` | <span data-ttu-id="c296e-259">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-259">Ordinal</span></span> | <span data-ttu-id="c296e-260">(wenn der erste Parameter ein `char` ist)</span><span class="sxs-lookup"><span data-stu-id="c296e-260">(when the first parameter is a `char`)</span></span> |
| `string.StartsWith` | <span data-ttu-id="c296e-261">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-261">CurrentCulture</span></span> | <span data-ttu-id="c296e-262">(wenn der erste Parameter ein `string` ist)</span><span class="sxs-lookup"><span data-stu-id="c296e-262">(when the first parameter is a `string`)</span></span> |
| `string.ToLower` | <span data-ttu-id="c296e-263">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-263">CurrentCulture</span></span> | |
| `string.ToLowerInvariant` | <span data-ttu-id="c296e-264">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-264">InvariantCulture</span></span> | |
| `string.ToUpper` | <span data-ttu-id="c296e-265">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-265">CurrentCulture</span></span> | |
| `string.ToUpperInvariant` | <span data-ttu-id="c296e-266">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-266">InvariantCulture</span></span> | |
| `string.Trim` | <span data-ttu-id="c296e-267">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-267">Ordinal</span></span> | |
| `string.TrimEnd` | <span data-ttu-id="c296e-268">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-268">Ordinal</span></span> | |
| `string.TrimStart` | <span data-ttu-id="c296e-269">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-269">Ordinal</span></span> | |
| `string == string` | <span data-ttu-id="c296e-270">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-270">Ordinal</span></span> | |
| `string != string` | <span data-ttu-id="c296e-271">Ordinal</span><span class="sxs-lookup"><span data-stu-id="c296e-271">Ordinal</span></span> | |

<span data-ttu-id="c296e-272">Anders als `string`-APIs führen alle `MemoryExtensions`-APIs standardmäßig *ordinale* Suchen und Vergleiche durch, bei folgenden Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="c296e-272">Unlike `string` APIs, all `MemoryExtensions` APIs perform *Ordinal* searches and comparisons by default, with the following exceptions.</span></span>

| <span data-ttu-id="c296e-273">API</span><span class="sxs-lookup"><span data-stu-id="c296e-273">API</span></span> | <span data-ttu-id="c296e-274">Standardverhalten</span><span class="sxs-lookup"><span data-stu-id="c296e-274">Default behavior</span></span> | <span data-ttu-id="c296e-275">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c296e-275">Remarks</span></span> |
|---|---|---|
| `MemoryExtensions.ToLower` | <span data-ttu-id="c296e-276">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-276">CurrentCulture</span></span> | <span data-ttu-id="c296e-277">(bei Übergeben von NULL für ein `CultureInfo`-Argument)</span><span class="sxs-lookup"><span data-stu-id="c296e-277">(when passed a null `CultureInfo` argument)</span></span> |
| `MemoryExtensions.ToLowerInvariant` | <span data-ttu-id="c296e-278">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-278">InvariantCulture</span></span> | |
| `MemoryExtensions.ToUpper` | <span data-ttu-id="c296e-279">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-279">CurrentCulture</span></span> | <span data-ttu-id="c296e-280">(bei Übergeben von NULL für ein `CultureInfo`-Argument)</span><span class="sxs-lookup"><span data-stu-id="c296e-280">(when passed a null `CultureInfo` argument)</span></span> |
| `MemoryExtensions.ToUpperInvariant` | <span data-ttu-id="c296e-281">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="c296e-281">InvariantCulture</span></span> | |

<span data-ttu-id="c296e-282">Eine Folge davon ist, dass bei der Konvertierung von Code von der Nutzung von `string` in die Nutzung von `ReadOnlySpan<char>` unbeabsichtigt Verhaltensänderungen herbeigeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="c296e-282">A consequence is that when converting code from consuming `string` to consuming `ReadOnlySpan<char>`, behavioral changes may be introduced inadvertently.</span></span> <span data-ttu-id="c296e-283">Es folgt ein Beispiel dafür.</span><span class="sxs-lookup"><span data-stu-id="c296e-283">An example of this follows.</span></span>

```cs
string str = GetString();
if (str.StartsWith("Hello")) { /* do something */ } // this is a CULTURE-AWARE (linguistic) comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello")) { /* do something */ } // this is an ORDINAL (non-linguistic) comparison
```

<span data-ttu-id="c296e-284">Um dem zu begegnen, wird empfohlen, einen expliziten `StringComparison`-Parameter an diese APIs zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c296e-284">The recommended way to address this is to pass an explicit `StringComparison` parameter to these APIs.</span></span> <span data-ttu-id="c296e-285">Die Codeanalyseregeln CA1307 und CA1309 können dabei helfen.</span><span class="sxs-lookup"><span data-stu-id="c296e-285">The code analysis rules CA1307 and CA1309 can assist with this.</span></span>

```cs
string str = GetString();
if (str.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison
```

## <a name="see-also"></a><span data-ttu-id="c296e-286">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c296e-286">See also</span></span>

- [<span data-ttu-id="c296e-287">Breaking Changes bei der Globalisierung</span><span class="sxs-lookup"><span data-stu-id="c296e-287">Globalization breaking changes</span></span>](../../core/compatibility/globalization.md)
- [<span data-ttu-id="c296e-288">Bewährte Methoden zum Vergleichen von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="c296e-288">Best practices for comparing strings in .NET</span></span>](best-practices-strings.md)
- [<span data-ttu-id="c296e-289">Vergleichen von Zeichenfolgen in C#</span><span class="sxs-lookup"><span data-stu-id="c296e-289">How to compare strings in C#</span></span>](../../csharp/how-to/compare-strings.md)
- [<span data-ttu-id="c296e-290">.NET-Globalisierung und ICU</span><span class="sxs-lookup"><span data-stu-id="c296e-290">.NET globalization and ICU</span></span>](../globalization-localization/globalization-icu.md)
- [<span data-ttu-id="c296e-291">Vergleich von ordinalen und kulturabhängigen Zeichenfolgenvorgängen</span><span class="sxs-lookup"><span data-stu-id="c296e-291">Ordinal vs. culture-sensitive string operations</span></span>](/dotnet/api/system.string#ordinal-vs-culture-sensitive-operations)
- [<span data-ttu-id="c296e-292">Übersicht über die Analyse von .NET-Quellcode</span><span class="sxs-lookup"><span data-stu-id="c296e-292">Overview of .NET source code analysis</span></span>](../../fundamentals/code-analysis/overview.md)

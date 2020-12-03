---
title: 'Breaking Change: Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows'
description: Hier erfahren Sie mehr über den Globalisierungs-Breaking-Change in .NET 5.0, bei dem anstelle von NLS ICU-Bibliotheken für Globalisierungsfunktionen verwendet werden.
ms.date: 05/19/2020
ms.openlocfilehash: efc20e21969ea4a83c9122e40b262e1dc38e6770
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759559"
---
# <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="85193-103">Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows</span><span class="sxs-lookup"><span data-stu-id="85193-103">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="85193-104">.NET 5.0 und höhere Versionen verwenden bei der Ausführung unter dem Windows 10-Update vom Mai 2019 oder später [ICU](http://site.icu-project.org/home)-Bibliotheken (International Components for Unicode, internationale Komponenten für Unicode) für die Globalisierungsfunktionalität.</span><span class="sxs-lookup"><span data-stu-id="85193-104">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

## <a name="change-description"></a><span data-ttu-id="85193-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="85193-105">Change description</span></span>

<span data-ttu-id="85193-106">In .NET Core 1.0-3.1 und .NET Framework 4 und höher verwenden .NET-Bibliotheken [NLS](/windows/win32/intl/national-language-support)-APIs (National Language Support) für Globalisierungsfunktionalität unter Windows.</span><span class="sxs-lookup"><span data-stu-id="85193-106">In .NET Core 1.0 - 3.1 and .NET Framework 4 and later, .NET libraries use [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality on Windows.</span></span> <span data-ttu-id="85193-107">Beispielsweise wurden NLS-Funktionen verwendet, um Zeichenfolgen zu vergleichen, Informationen zur Kultur abzurufen und Groß-/Kleinschreibung von Zeichenfolgen gemäß der entsprechenden Kultur umzusetzen.</span><span class="sxs-lookup"><span data-stu-id="85193-107">For example, NLS functions were used to compare strings, get culture information, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="85193-108">Ab .NET 5.0 verwenden .NET-Bibliotheken standardmäßig Globalisierungs-APIs von [ICU](http://site.icu-project.org/home), wenn eine Anwendung unter Windows 10 mit Update vom Mai 2019 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="85193-108">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs, by default.</span></span>

> [!NOTE]
> <span data-ttu-id="85193-109">Das Windows 10-Update von Mai 2019 und spätere Versionen werden mit der nativen ICU-Bibliothek ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="85193-109">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="85193-110">Wenn die .NET-Runtime ICU nicht laden kann, verwendet sie stattdessen NLS.</span><span class="sxs-lookup"><span data-stu-id="85193-110">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="85193-111">Verhaltensunterschiede</span><span class="sxs-lookup"><span data-stu-id="85193-111">Behavioral differences</span></span>

<span data-ttu-id="85193-112">Möglicherweise bemerken Sie Änderungen in Ihrer Anwendung, auch wenn Sie sich nicht bewusst sind, dass Sie Globalisierungsfunktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="85193-112">You might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="85193-113">In diesem Abschnitt finden einige der Verhaltensänderungen, die Sie möglicherweise beobachten, aber es gibt noch weitere.</span><span class="sxs-lookup"><span data-stu-id="85193-113">This section lists a couple of the behavioral changes you might see, but there are others too.</span></span>

### <a name="stringindexof"></a><span data-ttu-id="85193-114">String.IndexOf</span><span class="sxs-lookup"><span data-stu-id="85193-114">String.IndexOf</span></span>

<span data-ttu-id="85193-115">Betrachten Sie den folgenden Code, der <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> aufruft, um den Index des Zeilenvorschubzeichens in einer Zeichenfolge zu finden.</span><span class="sxs-lookup"><span data-stu-id="85193-115">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="85193-116">In früheren Versionen von .NET unter Windows gibt der Ausschnitt `6` aus.</span><span class="sxs-lookup"><span data-stu-id="85193-116">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="85193-117">Ab .NET 5.0 unter Windows 19H1 und höheren Versionen gibt der Ausschnitt `-1` aus.</span><span class="sxs-lookup"><span data-stu-id="85193-117">In .NET 5.0 and later versions on Windows 19H1 and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="85193-118">Um diesen Code durch eine ordinale Suche anstelle einer kulturabhängigen Suche zu korrigieren, rufen Sie die Überladung <xref:System.String.IndexOf(System.String,System.StringComparison)> auf, an die Sie <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="85193-118">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="85193-119">Sie können Codeanalyseregeln entsprechend [CA1307: Angeben von StringComparison für mehr Klarheit](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) und [CA1309: Verwenden eines ordinalen StringComparison](../../../../fundamentals/code-analysis/quality-rules/ca1309.md) ausführen, um diese Aufrufstellen in Ihrem Code zu finden.</span><span class="sxs-lookup"><span data-stu-id="85193-119">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../../fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="85193-120">Weitere Informationen finden Sie unter [Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5](../../../../standard/base-types/string-comparison-net-5-plus.md).</span><span class="sxs-lookup"><span data-stu-id="85193-120">For more information, see [Behavior changes when comparing strings on .NET 5+](../../../../standard/base-types/string-comparison-net-5-plus.md).</span></span>

### <a name="currency-symbol"></a><span data-ttu-id="85193-121">Währungssymbol</span><span class="sxs-lookup"><span data-stu-id="85193-121">Currency symbol</span></span>

<span data-ttu-id="85193-122">Betrachten Sie den folgenden Code, der eine Zeichenfolge mit `C` als Spezifizierer des Währungsformats formatiert.</span><span class="sxs-lookup"><span data-stu-id="85193-122">Consider the following code that formats a string using the currency format specifier `C`.</span></span> <span data-ttu-id="85193-123">Die Kultur des aktuellen Threads ist auf eine Kultur festgelegt, die nur die Sprache und nicht das Land umfasst.</span><span class="sxs-lookup"><span data-stu-id="85193-123">The current thread's culture is set to a culture that includes only the language and not the country.</span></span>

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- <span data-ttu-id="85193-124">In früheren Versionen von .NET unter Windows ist der Wert des Texts `"100,00 €"`.</span><span class="sxs-lookup"><span data-stu-id="85193-124">In previous versions of .NET on Windows, the value of text is `"100,00 €"`.</span></span>
- <span data-ttu-id="85193-125">Ab .NET 5.0 unter Windows 19H1 und späteren Versionen ist der Wert des Texts `"100,00 ¤"`, der das internationale Währungssymbol anstelle von Euro verwendet.</span><span class="sxs-lookup"><span data-stu-id="85193-125">In .NET 5.0 and later versions on Windows 19H1 and later versions, the value of text is `"100,00 ¤"`, which uses the international currency symbol instead of the euro.</span></span> <span data-ttu-id="85193-126">In ICU ist eine Währung eine Eigenschaft eines Landes oder einer Region und nicht einer Sprache.</span><span class="sxs-lookup"><span data-stu-id="85193-126">In ICU, the design is that a currency is a property of a country or region, not a language.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="85193-127">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="85193-127">Reason for change</span></span>

<span data-ttu-id="85193-128">Diese Änderung wurde eingeführt, um das Globalisierungsverhalten von .NET in allen unterstützten Betriebssystemen zu vereinheitlichen.</span><span class="sxs-lookup"><span data-stu-id="85193-128">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="85193-129">Darüber hinaus können Anwendungen ihre eigenen Globalisierungsbibliotheken bündeln, anstatt von den in das Betriebssystem integrierten Bibliotheken abhängig zu sein.</span><span class="sxs-lookup"><span data-stu-id="85193-129">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the operating system's built-in libraries.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="85193-130">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="85193-130">Version introduced</span></span>

<span data-ttu-id="85193-131">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="85193-131">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="85193-132">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="85193-132">Recommended action</span></span>

<span data-ttu-id="85193-133">Auf der Seite des Entwicklers ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85193-133">No action is required on the part of the developer.</span></span> <span data-ttu-id="85193-134">Wenn Sie jedoch weiterhin NLS-Globalisierungs-APIs verwenden möchten, können Sie einen [Runtimeschalter festlegen](../../../run-time-config/globalization.md#nls), um zu diesem Verhalten zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="85193-134">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="85193-135">Weitere Informationen zu den verfügbaren Schaltern finden Sie im Artikel [.NET-Globalisierung und ICU](../../../../standard/globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="85193-135">For more information about the available switches, see the [.NET globalization and ICU](../../../../standard/globalization-localization/globalization-icu.md) article.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="85193-136">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="85193-136">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="85193-137">Die meisten Typen im <xref:System.Globalization?displayProperty=fullName>-Namespace</span><span class="sxs-lookup"><span data-stu-id="85193-137">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>
- <span data-ttu-id="85193-138"><xref:System.Array.Sort%2A?displayProperty=fullName> (beim Sortieren eines Zeichenfolgenarrays)</span><span class="sxs-lookup"><span data-stu-id="85193-138"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting an array of strings)</span></span>
- <span data-ttu-id="85193-139"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (wenn die Listenelemente Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="85193-139"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="85193-140"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="85193-140"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="85193-141"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="85193-141"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="85193-142"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (wenn die Gruppe Zeichenfolgen enthält)</span><span class="sxs-lookup"><span data-stu-id="85193-142"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

<!--

### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

### Category

- Core .NET libraries
- Globalization

-->

---
ms.openlocfilehash: 02b5dc181abe384c1a5f47c042e475f67a0afe1c
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400804"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="58148-101">Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows</span><span class="sxs-lookup"><span data-stu-id="58148-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="58148-102">.NET 5.0 und höhere Versionen verwenden bei der Ausführung unter dem Windows 10-Update vom Mai 2019 oder später [ICU](http://site.icu-project.org/home)-Bibliotheken (International Components for Unicode, internationale Komponenten für Unicode) für die Globalisierungsfunktionalität.</span><span class="sxs-lookup"><span data-stu-id="58148-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="58148-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="58148-103">Change description</span></span>

<span data-ttu-id="58148-104">In .NET Core 1.0-3.1 und .NET Framework 4 und höher verwenden .NET-Bibliotheken [NLS](/windows/win32/intl/national-language-support)-APIs (National Language Support) für Globalisierungsfunktionalität unter Windows.</span><span class="sxs-lookup"><span data-stu-id="58148-104">In .NET Core 1.0 - 3.1 and .NET Framework 4 and later, .NET libraries use [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality on Windows.</span></span> <span data-ttu-id="58148-105">Beispielsweise wurden NLS-Funktionen verwendet, um Zeichenfolgen zu vergleichen, Informationen zur Kultur abzurufen und Groß-/Kleinschreibung von Zeichenfolgen gemäß der entsprechenden Kultur umzusetzen.</span><span class="sxs-lookup"><span data-stu-id="58148-105">For example, NLS functions were used to compare strings, get culture information, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="58148-106">Ab .NET 5.0 verwenden .NET-Bibliotheken standardmäßig Globalisierungs-APIs von [ICU](http://site.icu-project.org/home), wenn eine Anwendung unter Windows 10 mit Update vom Mai 2019 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="58148-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs, by default.</span></span>

> [!NOTE]
> <span data-ttu-id="58148-107">Das Windows 10-Update von Mai 2019 und spätere Versionen werden mit der nativen ICU-Bibliothek ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="58148-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="58148-108">Wenn die .NET-Runtime ICU nicht laden kann, verwendet sie stattdessen NLS.</span><span class="sxs-lookup"><span data-stu-id="58148-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

#### <a name="behavioral-differences"></a><span data-ttu-id="58148-109">Verhaltensunterschiede</span><span class="sxs-lookup"><span data-stu-id="58148-109">Behavioral differences</span></span>

<span data-ttu-id="58148-110">Möglicherweise bemerken Sie Änderungen in Ihrer Anwendung, auch wenn Sie sich nicht bewusst sind, dass Sie Globalisierungsfunktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="58148-110">You might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="58148-111">In diesem Abschnitt finden einige der Verhaltensänderungen, die Sie möglicherweise beobachten, aber es gibt noch weitere.</span><span class="sxs-lookup"><span data-stu-id="58148-111">This section lists a couple of the behavioral changes you might see, but there are others too.</span></span>

##### <a name="stringindexof"></a><span data-ttu-id="58148-112">String.IndexOf</span><span class="sxs-lookup"><span data-stu-id="58148-112">String.IndexOf</span></span>

<span data-ttu-id="58148-113">Betrachten Sie den folgenden Code, der <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> aufruft, um den Index des Zeilenvorschubzeichens in einer Zeichenfolge zu finden.</span><span class="sxs-lookup"><span data-stu-id="58148-113">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="58148-114">In früheren Versionen von .NET unter Windows gibt der Ausschnitt `6` aus.</span><span class="sxs-lookup"><span data-stu-id="58148-114">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="58148-115">Ab .NET 5.0 unter Windows 19H1 und höheren Versionen gibt der Ausschnitt `-1` aus.</span><span class="sxs-lookup"><span data-stu-id="58148-115">In .NET 5.0 and later versions on Windows 19H1 and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="58148-116">Um diesen Code durch eine ordinale Suche anstelle einer kulturabhängigen Suche zu korrigieren, rufen Sie die Überladung <xref:System.String.IndexOf(System.String,System.StringComparison)> auf, an die Sie <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> als Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="58148-116">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="58148-117">Sie können Codeanalyseregeln entsprechend [CA1307: Angeben von StringComparison für mehr Klarheit](../../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) und [CA1309: Verwenden eines ordinalen StringComparison](../../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) ausführen, um diese Aufrufstellen in Ihrem Code zu finden.</span><span class="sxs-lookup"><span data-stu-id="58148-117">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="58148-118">Weitere Informationen finden Sie unter [Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5](../../../../docs/standard/base-types/string-comparison-net-5-plus.md).</span><span class="sxs-lookup"><span data-stu-id="58148-118">For more information, see [Behavior changes when comparing strings on .NET 5+](../../../../docs/standard/base-types/string-comparison-net-5-plus.md).</span></span>

##### <a name="currency-symbol"></a><span data-ttu-id="58148-119">Währungssymbol</span><span class="sxs-lookup"><span data-stu-id="58148-119">Currency symbol</span></span>

<span data-ttu-id="58148-120">Betrachten Sie den folgenden Code, der eine Zeichenfolge mit `C` als Spezifizierer des Währungsformats formatiert.</span><span class="sxs-lookup"><span data-stu-id="58148-120">Consider the following code that formats a string using the currency format specifier `C`.</span></span> <span data-ttu-id="58148-121">Die Kultur des aktuellen Threads ist auf eine Kultur festgelegt, die nur die Sprache und nicht das Land umfasst.</span><span class="sxs-lookup"><span data-stu-id="58148-121">The current thread's culture is set to a culture that includes only the language and not the country.</span></span>

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- <span data-ttu-id="58148-122">In früheren Versionen von .NET unter Windows ist der Wert des Texts `"100,00 €"`.</span><span class="sxs-lookup"><span data-stu-id="58148-122">In previous versions of .NET on Windows, the value of text is `"100,00 €"`.</span></span>
- <span data-ttu-id="58148-123">Ab .NET 5.0 unter Windows 19H1 und späteren Versionen ist der Wert des Texts `"100,00 ¤"`, der das internationale Währungssymbol anstelle von Euro verwendet.</span><span class="sxs-lookup"><span data-stu-id="58148-123">In .NET 5.0 and later versions on Windows 19H1 and later versions, the value of text is `"100,00 ¤"`, which uses the international currency symbol instead of the euro.</span></span> <span data-ttu-id="58148-124">In ICU ist eine Währung eine Eigenschaft eines Landes oder einer Region und nicht einer Sprache.</span><span class="sxs-lookup"><span data-stu-id="58148-124">In ICU, the design is that a currency is a property of a country or region, not a language.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="58148-125">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="58148-125">Reason for change</span></span>

<span data-ttu-id="58148-126">Diese Änderung wurde eingeführt, um das Globalisierungsverhalten von .NET in allen unterstützten Betriebssystemen zu vereinheitlichen.</span><span class="sxs-lookup"><span data-stu-id="58148-126">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="58148-127">Darüber hinaus können Anwendungen ihre eigenen Globalisierungsbibliotheken bündeln, anstatt von den in das Betriebssystem integrierten Bibliotheken abhängig zu sein.</span><span class="sxs-lookup"><span data-stu-id="58148-127">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the operating system's built-in libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="58148-128">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="58148-128">Version introduced</span></span>

<span data-ttu-id="58148-129">.NET 5.0 Preview 4</span><span class="sxs-lookup"><span data-stu-id="58148-129">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="58148-130">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="58148-130">Recommended action</span></span>

<span data-ttu-id="58148-131">Auf der Seite des Entwicklers ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58148-131">No action is required on the part of the developer.</span></span> <span data-ttu-id="58148-132">Wenn Sie jedoch weiterhin NLS-Globalisierungs-APIs verwenden möchten, können Sie einen [Runtimeschalter festlegen](../../../../docs/core/run-time-config/globalization.md#nls), um zu diesem Verhalten zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="58148-132">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="58148-133">Weitere Informationen zu den verfügbaren Schaltern finden Sie im Artikel [.NET-Globalisierung und ICU](../../../../docs/standard/globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="58148-133">For more information about the available switches, see the [.NET globalization and ICU](../../../../docs/standard/globalization-localization/globalization-icu.md) article.</span></span>

#### <a name="category"></a><span data-ttu-id="58148-134">Kategorie</span><span class="sxs-lookup"><span data-stu-id="58148-134">Category</span></span>

- <span data-ttu-id="58148-135">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="58148-135">Core .NET libraries</span></span>
- <span data-ttu-id="58148-136">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="58148-136">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="58148-137">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="58148-137">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="58148-138">Die meisten Typen im <xref:System.Globalization?displayProperty=fullName>-Namespace</span><span class="sxs-lookup"><span data-stu-id="58148-138">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>
- <span data-ttu-id="58148-139"><xref:System.Array.Sort%2A?displayProperty=fullName> (beim Sortieren eines Zeichenfolgenarrays)</span><span class="sxs-lookup"><span data-stu-id="58148-139"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting an array of strings)</span></span>
- <span data-ttu-id="58148-140"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (wenn die Listenelemente Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="58148-140"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="58148-141"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="58148-141"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="58148-142"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)</span><span class="sxs-lookup"><span data-stu-id="58148-142"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="58148-143"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (wenn die Gruppe Zeichenfolgen enthält)</span><span class="sxs-lookup"><span data-stu-id="58148-143"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

-->

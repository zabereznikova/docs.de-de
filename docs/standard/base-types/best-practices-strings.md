---
title: "Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen"
description: "Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: b3cefaa4-0a3f-4a96-aba9-1de30fb07c29
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 057faa0ad78dfb0a600dad2a1f0aeea240f33282
ms.contentlocale: de-de
ms.lasthandoff: 01/18/2017

---

# <a name="best-practices-for-using-strings"></a><span data-ttu-id="14a37-104">Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="14a37-104">Best practices for using strings</span></span>

<span data-ttu-id="14a37-105">.NET bietet umfangreiche Unterstützung für das Entwickeln von lokalisierten und globalisierten Anwendungen und erleichtert bei der Ausführung allgemeiner Operationen das Übernehmen von Konventionen der aktuellen oder einer anderen Kultur, beispielsweise bei der Sortierung und Anzeige von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="14a37-105">.NET provides extensive support for developing localized and globalized applications, and makes it easy to apply the conventions of either the current culture or a specific culture when performing common operations such as sorting and displaying strings.</span></span> <span data-ttu-id="14a37-106">Das Sortieren oder Vergleichen von Zeichenfolgen stellt jedoch nicht immer eine kulturabhängige Operation dar.</span><span class="sxs-lookup"><span data-stu-id="14a37-106">But sorting or comparing strings is not always a culture-sensitive operation.</span></span> <span data-ttu-id="14a37-107">Beispielsweise sollten interne Zeichenfolgen von Anwendungen i. d. R. in allen Kulturen gleich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-107">For example, strings that are used internally by an application typically should be handled identically across all cultures.</span></span> <span data-ttu-id="14a37-108">Wenn kulturabhängige Zeichenfolgendaten, z. B. XML-Tags, HTML-Tags, Benutzernamen, Dateipfade und Systemobjektnamen, kulturabhängig interpretiert werden, können Fehler im Anwendungscode auftreten, die Leistung kann sich verschlechtern, und in einigen Fällen kann es zu Sicherheitsproblemen kommen.</span><span class="sxs-lookup"><span data-stu-id="14a37-108">When culturally independent string data, such as XML tags, HTML tags, user names, file paths, and the names of system objects, are interpreted as if they were culture-sensitive, application code can be subject to subtle bugs, poor performance, and, in some cases, security issues.</span></span>

<span data-ttu-id="14a37-109">In diesem Artikel werden die Methoden für die Sortierung, den Vergleich und die Schreibweise von Zeichenfolgen in .NET untersucht. Darüber hinaus werden Empfehlungen zum Auswählen einer entsprechenden Zeichenfolgen-Behandlungsmethode gegeben und weitere Informationen dazu bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="14a37-109">This article examines the string sorting, comparison, and casing methods in .NET, presents recommendations for selecting an appropriate string-handling method, and provides additional information about string-handling methods.</span></span> <span data-ttu-id="14a37-110">Er wird außerdem untersucht, wie formatierte Daten, z. B. numerische Daten und Datums-/Uhrzeitdaten, für die Anzeige und Speicherung behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-110">It also examines how formatted data, such as numeric data and date and time data, is handled for display and for storage.</span></span> 

<span data-ttu-id="14a37-111">Dieser Artikel enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="14a37-111">This article contains the following sections:</span></span>

* [<span data-ttu-id="14a37-112">Empfehlungen zur Zeichenfolgenverwendung</span><span class="sxs-lookup"><span data-stu-id="14a37-112">Recommendations for string usage</span></span>](#recommendations-for-string-usage)

* [<span data-ttu-id="14a37-113">Explizites Angeben von Zeichenfolgenvergleichen</span><span class="sxs-lookup"><span data-stu-id="14a37-113">Specifying string comparisons explicitly</span></span>](#specifying-string-comparisons-explicitly)

* [<span data-ttu-id="14a37-114">Details zum Zeichenfolgenvergleich</span><span class="sxs-lookup"><span data-stu-id="14a37-114">The details of string comparison</span></span>](#the-details-of-string-comparison)

* [<span data-ttu-id="14a37-115">Auswählen eines StringComparison-Members für den Methodenaufruf</span><span class="sxs-lookup"><span data-stu-id="14a37-115">Choosing a StringComparison member for your method call</span></span>](#choosing-a-stringcomparison-member-for-your-method-call)

* [<span data-ttu-id="14a37-116">Allgemeine Methoden für den Zeichenfolgenvergleich</span><span class="sxs-lookup"><span data-stu-id="14a37-116">Common string comparison methods</span></span>](#common-string-comparison-methods)

* [<span data-ttu-id="14a37-117">Methoden für den indirekten Zeichenfolgenvergleich</span><span class="sxs-lookup"><span data-stu-id="14a37-117">Methods that perform string comparison indirectly</span></span>](#methods-that-perform-string-comparison-indirectly)

* [<span data-ttu-id="14a37-118">Anzeigen und Beibehalten von formatierten Daten</span><span class="sxs-lookup"><span data-stu-id="14a37-118">Displaying and persisting formatted data</span></span>](#displaying-and-persisting-formatted-data)

## <a name="recommendations-for-string-usage"></a><span data-ttu-id="14a37-119">Empfehlungen zur Zeichenfolgenverwendung</span><span class="sxs-lookup"><span data-stu-id="14a37-119">Recommendations for string usage</span></span>

<span data-ttu-id="14a37-120">Beachten Sie folgende grundlegende Empfehlungen zur Verwendung von Zeichenfolgen bei der Entwicklung mit .NET:</span><span class="sxs-lookup"><span data-stu-id="14a37-120">When you develop with .NET, follow these simple recommendations when you use strings:</span></span> 

* <span data-ttu-id="14a37-121">Verwenden Sie Überladungen, die die Regeln für Zeichenfolgenvergleiche in Zeichenfolgenoperationen explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-121">Use overloads that explicitly specify the string comparison rules for string operations.</span></span> <span data-ttu-id="14a37-122">Normalerweise müssen Sie dazu eine Methodenüberladung mit einem Parameter vom Typ [StringComparison](xref:System.StringComparison) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="14a37-122">Typically, this involves calling a method overload that has a parameter of type [StringComparison](xref:System.StringComparison).</span></span>

* <span data-ttu-id="14a37-123">Verwenden Sie [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) als Ihre sichere Standardeinstellung für kulturunabhängige Zeichenfolgenvergleiche.</span><span class="sxs-lookup"><span data-stu-id="14a37-123">Use [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for comparisons as your safe default for culture-agnostic string matching.</span></span>

* <span data-ttu-id="14a37-124">Verwenden Sie Vergleiche mit [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) für eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="14a37-124">Use comparisons with [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for better performance.</span></span>

* <span data-ttu-id="14a37-125">Verwenden Sie Zeichenfolgenoperationen, die auf [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) basieren, um die Ausgabe für Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14a37-125">Use string operations that are based on [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) when you display output to the user.</span></span>

* <span data-ttu-id="14a37-126">Verwenden Sie die nicht linguistischen Werte [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) anstelle von Zeichenfolgenoperationen, die auf [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) basieren, wenn der Vergleich linguistisch nicht relevant ist (z.B. symbolisch).</span><span class="sxs-lookup"><span data-stu-id="14a37-126">Use the non-linguistic [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) values instead of string operations based on [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) when the comparison is linguistically irrelevant (symbolic, for example).</span></span>

* <span data-ttu-id="14a37-127">Verwenden Sie die [String.ToUpperInvariant](xref:System.String.ToUpperInvariant)-Methode anstelle der [String.ToLowerInvariant](xref:System.String.ToLowerInvariant)-Methode, wenn Sie Zeichenfolgen für einen Vergleich normalisieren.</span><span class="sxs-lookup"><span data-stu-id="14a37-127">Use the [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) method instead of the [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) method when you normalize strings for comparison.</span></span>

* <span data-ttu-id="14a37-128">Verwenden Sie eine Überladung der [String](xref:System.String)`Equals`-Methode, um zu überprüfen, ob zwei Zeichenfolgen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="14a37-128">Use an overload of the [String](xref:System.String) `Equals` method to test whether two strings are equal.</span></span>

* <span data-ttu-id="14a37-129">Verwenden Sie eine Überladung von der [String](xref:System.String)`Compare`- und [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode zum Sortieren von Zeichenfolgen, nicht zur Überprüfung auf Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="14a37-129">Use an overload of the [String](xref:System.String) `Compare` and [String.CompareTo](xref:System.String.CompareTo(System.String)) methods to sort strings, not to check for equality.</span></span>

* <span data-ttu-id="14a37-130">Verwenden Sie kulturabhängige Formatierung, um Daten, die keine Zeichenfolge sind, z. B. Zahlen und Datumsangaben, auf einer Benutzeroberfläche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14a37-130">Use culture-sensitive formatting to display non-string data, such as numbers and dates, in a user interface.</span></span> <span data-ttu-id="14a37-131">Verwenden Sie Formatierung mit der invarianten Kultur, um Daten, die keine Zeichenfolge sind, im Zeichenfolgenformat beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="14a37-131">Use formatting with the invariant culture to persist non-string data in string form.</span></span>

<span data-ttu-id="14a37-132">Vermeiden Sie folgende Vorgehensweisen bei der Verwendung von Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="14a37-132">Avoid the following practices when you use strings:</span></span>

* <span data-ttu-id="14a37-133">Verwenden Sie keine Überladungen, die die Regeln für Zeichenfolgenvergleiche in Zeichenfolgenoperationen nicht explizit oder implizit angeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-133">Do not use overloads that do not explicitly or implicitly specify the string comparison rules for string operations.</span></span> 

* <span data-ttu-id="14a37-134">Verwenden Sie keine Überladung der [String](xref:System.String)`Compare`-Methode oder der [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode, und führen Sie eine Überprüfung mit einem Rückgabewert von 0 (null) durch, um zu bestimmen, ob zwei Zeichenfolgen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="14a37-134">Do not use an overload of the [String](xref:System.String) `Compare` or [String.CompareTo](xref:System.String.CompareTo(System.String)) methods and test for a return value of zero to determine whether two strings are equal.</span></span>

* <span data-ttu-id="14a37-135">Verwenden Sie nicht kulturabhängige Formatierung, um numerische Daten oder Datums-/Uhrzeitdaten im Zeichenfolgenformat beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="14a37-135">Do not use culture-sensitive formatting to persist numeric data or date and time data in string form.</span></span>

## <a name="specifying-string-comparisons-explicitly"></a><span data-ttu-id="14a37-136">Explizites Angeben von Zeichenfolgenvergleichen</span><span class="sxs-lookup"><span data-stu-id="14a37-136">Specifying string comparisons explicitly</span></span>

<span data-ttu-id="14a37-137">Die Methoden zum Bearbeiten von Zeichenfolgen in .NET werden i.d.R. überladen.</span><span class="sxs-lookup"><span data-stu-id="14a37-137">Most of the string manipulation methods in .NET are overloaded.</span></span> <span data-ttu-id="14a37-138">Während einige Überladungen normalerweise Standardwerte akzeptieren, geben andere Überladungen exakt an, wie Zeichenfolgen verglichen oder bearbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="14a37-138">Typically, one or more overloads accept default settings, whereas others accept no defaults and instead define the precise way in which strings are to be compared or manipulated.</span></span> <span data-ttu-id="14a37-139">Methoden, die keine Standardwerte verwenden, enthalten i.d.R einen Parameter vom Typ [StringComparison](xref:System.StringComparison). Dabei handelt es sich um eine Enumeration, die explizit Regeln für Zeichenfolgenvergleiche anhand von Kultur und Schreibweise angibt.</span><span class="sxs-lookup"><span data-stu-id="14a37-139">Most of the methods that do not rely on defaults include a parameter of type [StringComparison](xref:System.StringComparison), which is an enumeration that explicitly specifies rules for string comparison by culture and case.</span></span> <span data-ttu-id="14a37-140">In der folgenden Tabelle werden die Member der [StringComparison](xref:System.StringComparison)-Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14a37-140">The following table describes the [StringComparison](xref:System.StringComparison) enumeration members.</span></span> 

<span data-ttu-id="14a37-141">StringComparison-Member</span><span class="sxs-lookup"><span data-stu-id="14a37-141">StringComparison member</span></span> | <span data-ttu-id="14a37-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14a37-142">Description</span></span>
----------------------- | -----------
[<span data-ttu-id="14a37-143">StringComparison.CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="14a37-143">StringComparison.CurrentCulture</span></span>](xref:System.StringComparison.CurrentCulture) | <span data-ttu-id="14a37-144">Führt einen Vergleich mit der aktuellen Kultur unter Beachtung der Groß- und Kleinschreibung durch.</span><span class="sxs-lookup"><span data-stu-id="14a37-144">Performs a case-sensitive comparison using the current culture.</span></span>
[<span data-ttu-id="14a37-145">CurrentCultureIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="14a37-145">CurrentCultureIgnoreCase</span></span>](xref:System.StringComparison.CurrentCultureIgnoreCase) | <span data-ttu-id="14a37-146">Führt einen Vergleich mit der aktuellen Kultur ohne Beachtung der Groß- und Kleinschreibung durch.</span><span class="sxs-lookup"><span data-stu-id="14a37-146">Performs a case-insensitive comparison using the current culture.</span></span>
[<span data-ttu-id="14a37-147">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="14a37-147">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal) | <span data-ttu-id="14a37-148">Führt einen Ordinalvergleich durch.</span><span class="sxs-lookup"><span data-stu-id="14a37-148">Performs an ordinal comparison.</span></span>
[<span data-ttu-id="14a37-149">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="14a37-149">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase) | <span data-ttu-id="14a37-150">Führt einen Ordinalvergleich ohne Beachtung der Groß- und Kleinschreibung durch.</span><span class="sxs-lookup"><span data-stu-id="14a37-150">Performs a case-insensitive ordinal comparison.</span></span>

<span data-ttu-id="14a37-151">Die [String](xref:System.String)`IndexOf`-Methode, die den Index einer Teilzeichenfolge in einem [String](xref:System.String)-Objekt zurückgibt, das einem Zeichen oder einer Zeichenfolge entspricht, weist beispielsweise neun Überladungen auf:</span><span class="sxs-lookup"><span data-stu-id="14a37-151">For example, the [String](xref:System.String) `IndexOf` method, which returns the index of a substring in a [String](xref:System.String) object that matches either a character or a string, has nine overloads:</span></span>

* <span data-ttu-id="14a37-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)) und [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)) führen standardmäßig eine kulturunabhängige Ordinalsuche nach einem Zeichen in der Zeichenfolge unter Beachtung der Groß- und Kleinschreibung durch.</span><span class="sxs-lookup"><span data-stu-id="14a37-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)), and [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)), which by default perform an ordinal (case-sensitive and culture-insensitive) search for a character in the string.</span></span>

* <span data-ttu-id="14a37-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)) und [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)) führen standardmäßig eine kulturunabhängige Ordinalsuche nach einer Teilzeichenfolge in der Zeichenfolge unter Beachtung der Groß- und Kleinschreibung durch.</span><span class="sxs-lookup"><span data-stu-id="14a37-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)), and [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)), which by default perform a case-sensitive and culture-sensitive search for a substring in the string.</span></span>

* <span data-ttu-id="14a37-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)) und [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)) enthalten einen Parameter vom Typ StringComparison, mit dem die Form des Vergleichs angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="14a37-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)), and [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)), which include a parameter of type StringComparison that allows the form of the comparison to be specified.</span></span>

<span data-ttu-id="14a37-155">Aus den folgenden Gründen wird empfohlen, eine Überladung ohne Standardwerte auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="14a37-155">We recommend that you select an overload that does not use default values, for the following reasons:</span></span>

* <span data-ttu-id="14a37-156">Einige Überladungen mit Standardparametern (die in der Zeichenfolgeninstanz nach einem [Char](xref:System.Char) suchen) führen einen Ordinalvergleich durch, während andere Überladungen (die in der Zeichenfolgeninstanz nach einer Zeichenfolge suchen) kulturabhängig sind.</span><span class="sxs-lookup"><span data-stu-id="14a37-156">Some overloads with default parameters (those that search for a [Char](xref:System.Char) in the string instance) perform an ordinal comparison, whereas others (those that search for a string in the string instance) are culture-sensitive.</span></span> <span data-ttu-id="14a37-157">Es ist nicht leicht, sich zu merken, welche Methode welchen Standardwert verwendet, und Überladungen können schnell verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-157">It is difficult to remember which method uses which default value, and easy to confuse the overloads.</span></span>

* <span data-ttu-id="14a37-158">Der Zweck des Codes, der Standardwerte für Methodenaufrufe verwendet, ist nicht klar.</span><span class="sxs-lookup"><span data-stu-id="14a37-158">The intent of the code that relies on default values for method calls is not clear.</span></span> <span data-ttu-id="14a37-159">Im folgenden Beispiel werden Standardwerte verwendet. Dabei ist nicht klar, ob der Entwickler tatsächlich einen ordinalen oder linguistischen Vergleich zweier Zeichenfolgen durchführen wollte oder ob der Unterschied in der Groß- und Kleinschreibung zwischen `protocol` und "http" möglicherweise dazu führt, dass bei einer Überprüfung auf Gleichheit `false` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="14a37-159">In the following example, which relies on defaults, it is difficult to know whether the developer actually intended an ordinal or a linguistic comparison of two strings, or whether a case difference between `protocol` and "http" might cause the test for equality to return `false`.</span></span>

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http") Then
  ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

<span data-ttu-id="14a37-160">Im Allgemeinen empfiehlt es sich, eine Methode aufzurufen, die keine Standardwerte verwendet, da der Zweck des Codes andernfalls möglicherweise nicht eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="14a37-160">In general, we recommend that you call a method that does not rely on defaults, because it makes the intent of the code unambiguous.</span></span> <span data-ttu-id="14a37-161">Dies erleichtert wiederum das Lesen, Verwalten und Debuggen des Codes.</span><span class="sxs-lookup"><span data-stu-id="14a37-161">This, in turn, makes the code more readable and easier to debug and maintain.</span></span> <span data-ttu-id="14a37-162">Im folgenden Beispiel wird auf die Fragen eingegangen, die sich zum vorherigen Beispiel stellen.</span><span class="sxs-lookup"><span data-stu-id="14a37-162">The following example addresses the questions raised about the previous example.</span></span> <span data-ttu-id="14a37-163">Es wird deutlich gemacht, dass der Ordinalvergleich verwendet wird und dass Unterschiede in der Groß- und Kleinschreibung ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-163">It makes it clear that ordinal comparison is used and that differences in case are ignored.</span></span> 

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase) Then
   ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

## <a name="the-details-of-string-comparison"></a><span data-ttu-id="14a37-164">Details zum Zeichenfolgenvergleich</span><span class="sxs-lookup"><span data-stu-id="14a37-164">The details of string comparison</span></span>

<span data-ttu-id="14a37-165">Zeichenfolgenvergleiche bilden den Kern zahlreicher Operationen, die sich auf Zeichenfolgen beziehen; dies gilt insbesondere für Sortierungen und Überprüfungen auf Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="14a37-165">String comparison is the heart of many string-related operations, particularly sorting and testing for equality.</span></span> <span data-ttu-id="14a37-166">Zeichenfolgen werden in einer bestimmten Reihenfolge sortiert: Wenn "my" in einer sortierten Zeichenfolgenliste vor "string" angezeigt wird, muss "my" bei einem Vergleich einen kleineren oder gleichen Wert wie "string" haben.</span><span class="sxs-lookup"><span data-stu-id="14a37-166">Strings sort in a determined order: If "my" appears before "string" in a sorted list of strings, "my" must compare less than or equal to "string".</span></span> <span data-ttu-id="14a37-167">Darüber hinaus wird beim Vergleich implizit Gleichheit definiert.</span><span class="sxs-lookup"><span data-stu-id="14a37-167">Additionally, comparison implicitly defines equality.</span></span> <span data-ttu-id="14a37-168">Die Vergleichsoperation gibt 0 (null) für Zeichenfolgen zurück, die als gleich betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-168">The comparison operation returns zero for strings it deems equal.</span></span> <span data-ttu-id="14a37-169">Dies kann so interpretiert werden, dass keine Zeichenfolge kleiner ist als die andere.</span><span class="sxs-lookup"><span data-stu-id="14a37-169">A good interpretation is that neither string is less than the other.</span></span> <span data-ttu-id="14a37-170">Sinnvolle Operationen mit Zeichenfolgen schließen i. d. R. mindestens eines der folgenden Verfahren ein: Vergleich mit einer anderen Zeichenfolge und Ausführen eines genau definierten Sortiervorgangs.</span><span class="sxs-lookup"><span data-stu-id="14a37-170">Most meaningful operations involving strings include one or both of these procedures: comparing with another string, and executing a well-defined sort operation.</span></span>

<span data-ttu-id="14a37-171">Die Überprüfung der Sortierreihenfolge zweier Zeichenfolgen oder ihre Überprüfung auf Gleichheit ergibt jedoch nicht ein einzelnes richtiges Ergebnis. Das Ergebnis ist vielmehr abhängig von den Kriterien, die dem Zeichenfolgenvergleich zugrunde liegen.</span><span class="sxs-lookup"><span data-stu-id="14a37-171">However, evaluating two strings for equality or sort order does not yield a single, correct result; the outcome depends on the criteria used to compare the strings.</span></span> <span data-ttu-id="14a37-172">Insbesondere können Zeichenfolgenvergleiche zu unterschiedlichen Ergebnissen führen, die Ordinalvergleiche darstellen oder auf der Schreibweise und den Sortierungskonventionen der aktuellen oder der invarianten Kultur (eine auf der englischen Sprache basierende Kultur, die nicht von einem Gebietsschema abhängig ist) basieren.</span><span class="sxs-lookup"><span data-stu-id="14a37-172">In particular, string comparisons that are ordinal or that are based on the casing and sorting conventions of the current culture or the invariant culture (a locale-agnostic culture based on the English language) may produce different results.</span></span>

### <a name="string-comparisons-that-use-the-current-culture"></a><span data-ttu-id="14a37-173">Zeichenfolgenvergleiche mit der aktuellen Kultur</span><span class="sxs-lookup"><span data-stu-id="14a37-173">String comparisons that use the current culture</span></span>

<span data-ttu-id="14a37-174">Ein Kriterium für Zeichenfolgenvergleiche stellt die Verwendung der Konventionen der aktuellen Kultur dar.</span><span class="sxs-lookup"><span data-stu-id="14a37-174">One criterion involves using the conventions of the current culture when comparing strings.</span></span> <span data-ttu-id="14a37-175">Vergleiche, die auf der aktuellen Kultur basieren, verwenden die aktuelle Kultur oder das aktuelle Gebietsschema des Threads.</span><span class="sxs-lookup"><span data-stu-id="14a37-175">Comparisons that are based on the current culture use the thread's current culture or locale.</span></span> <span data-ttu-id="14a37-176">Vergleiche, die auf der aktuellen Kultur basieren, sollten immer dann verwendet werden, wenn Daten linguistisch relevant sind und kulturabhängige Interaktionen von Benutzern widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="14a37-176">You should always use comparisons that are based on the current culture when data is linguistically relevant, and when it reflects culture-sensitive user interaction.</span></span> 

<span data-ttu-id="14a37-177">Das Verhalten im Hinblick auf Vergleiche und die Groß- und Kleinschreibung in .NET ändert sich jedoch, wenn sich die Kultur ändert.</span><span class="sxs-lookup"><span data-stu-id="14a37-177">However, comparison and casing behavior in .NET changes when the culture changes.</span></span> <span data-ttu-id="14a37-178">Dies ist der Fall, wenn eine Anwendung auf einem Computer mit einer anderen Kultur ausgeführt wird, als der Computer, auf dem die Anwendung entwickelt wurde, oder wenn der ausführende Thread seine Kultur ändert.</span><span class="sxs-lookup"><span data-stu-id="14a37-178">This happens when an application executes on a computer that has a different culture than the computer on which the application was developed, or when the executing thread changes its culture.</span></span> <span data-ttu-id="14a37-179">Dieses Verhalten ist beabsichtigt, für viele Entwickler jedoch nicht offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="14a37-179">This behavior is intentional, but it remains non-obvious to many developers.</span></span> <span data-ttu-id="14a37-180">Im folgenden Beispiel werden die Unterschiede zwischen den Sortierreihenfolgen in der englischen (amerikanisch, "en-US") und schwedischen ("sv-SE") Kultur herausgestellt.</span><span class="sxs-lookup"><span data-stu-id="14a37-180">The following example illustrates differences in sort order between the U.S. English ("en-US") and Swedish ("sv-SE") cultures.</span></span> <span data-ttu-id="14a37-181">Beachten Sie, dass die Wörter „ångström“, „Windows“ und „Visual Studio“ in den sortierten Zeichenfolgenarrays an unterschiedlichen Positionen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-181">Note that the words "ångström", "Windows", and "Visual Studio" appear in different positions in the sorted string arrays.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] values= { "able", "ångström", "apple", "Æble", 
                         "Windows", "Visual Studio" };
      Array.Sort(values);
      DisplayArray(values);

      // Change culture to Swedish (Sweden).
      string originalCulture = CultureInfo.CurrentCulture.Name;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("sv-SE");
      Array.Sort(values);
      DisplayArray(values);

      // Restore the original culture.
      Thread.CurrentThread.CurrentCulture = new CultureInfo(originalCulture);
    }

    private static void DisplayArray(string[] values)
    {
      Console.WriteLine("Sorting using the {0} culture:",  
                        CultureInfo.CurrentCulture.Name);
      foreach (string value in values)
         Console.WriteLine("   {0}", value);

      Console.WriteLine();
    }
}
// The example displays the following output:
//       Sorting using the en-US culture:
//          able
//          Æble
//          ångström
//          apple
//          Visual Studio
//          Windows
//       
//       Sorting using the sv-SE culture:
//          able
//          Æble
//          apple
//          Windows
//          Visual Studio
//          ångström
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim values() As String = { "able", "ångström", "apple", _
                                 "Æble", "Windows", "Visual Studio" }
      Array.Sort(values)
      DisplayArray(values)

      ' Change culture to Swedish (Sweden).
      Dim originalCulture As String = CultureInfo.CurrentCulture.Name
      Thread.CurrentThread.CurrentCulture = New CultureInfo("sv-SE")
      Array.Sort(values)
      DisplayArray(values)

      ' Restore the original culture.
      Thread.CurrentThread.CurrentCulture = New CultureInfo(originalCulture)
    End Sub

    Private Sub DisplayArray(values() As String)
      Console.WRiteLine("Sorting using the {0} culture:", _ 
                        CultureInfo.CurrentCulture.Name)
      For Each value As String In values
         Console.WriteLine("   {0}", value)
      Next
      Console.WriteLine()   
    End Sub
End Module
' The example displays the following output:
'       Sorting using the en-US culture:
'          able
'          Æble
'          ångström
'          apple
'          Visual Studio
'          Windows
'       
'       Sorting using the sv-SE culture:
'          able
'          Æble
'          apple
'          Windows
'          Visual Studio
'          ångström
```

<span data-ttu-id="14a37-182">Vergleiche mit der aktuellen Kultur, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, entsprechen kulturabhängigen Vergleichen, ignorieren jedoch die Schreibweise, die von der aktuellen Kultur des Threads vorgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="14a37-182">Case-insensitive comparisons that use the current culture are the same as culture-sensitive comparisons, except that they ignore case as dictated by the thread's current culture.</span></span> <span data-ttu-id="14a37-183">Dieses Verhalten zeigt sich möglicherweise auch bei Sortierreihenfolgen.</span><span class="sxs-lookup"><span data-stu-id="14a37-183">This behavior may manifest itself in sort orders as well.</span></span> 

<span data-ttu-id="14a37-184">Vergleiche mit der Semantik der aktuellen Kultur werden standardmäßig für folgende Methoden verwendet:</span><span class="sxs-lookup"><span data-stu-id="14a37-184">Comparisons that use current culture semantics are the default for the following methods:</span></span>

* <span data-ttu-id="14a37-185">[String](xref:System.String)`Compare`-Überladungen, die keinen [StringComparison](xref:System.StringComparison)-Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="14a37-185">[String](xref:System.String) `Compare` overloads that do not include a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="14a37-186">[String.CompareTo](xref:System.String.CompareTo(System.String))-Überladungen.</span><span class="sxs-lookup"><span data-stu-id="14a37-186">[String.CompareTo](xref:System.String.CompareTo(System.String)) overloads.</span></span>

* <span data-ttu-id="14a37-187">Die standardmäßige [String.StartsWith(String)](xref:System.String.StartsWith(System.String))-Methode.</span><span class="sxs-lookup"><span data-stu-id="14a37-187">The default [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) method.</span></span> 

* <span data-ttu-id="14a37-188">Die standardmäßige [String.EndsWith(String)](xref:System.String.EndsWith(System.String))-Methode.</span><span class="sxs-lookup"><span data-stu-id="14a37-188">The default [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) method.</span></span>

* <span data-ttu-id="14a37-189">[String](xref:System.String)`IndexOf`-Überladungen, die einen [String](xref:System.String) als Suchparameter akzeptieren und keinen [StringComparison](xref:System.StringComparison)-Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="14a37-189">[String](xref:System.String) `IndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="14a37-190">[String](xref:System.String)`LastIndexOf`-Überladungen, die einen [String](xref:System.String) als Suchparameter akzeptieren und keinen [StringComparison](xref:System.StringComparison)-Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="14a37-190">[String](xref:System.String) `LastIndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

<span data-ttu-id="14a37-191">In jedem Fall sollten Sie eine Überladung mit einem [StringComparison](xref:System.StringComparison)-Parameter aufrufen, um den Zweck des Methodenaufrufs eindeutig anzugeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-191">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter to make the intent of the method call clear.</span></span> 

<span data-ttu-id="14a37-192">Wenn nicht linguistische Zeichenfolgendaten linguistisch interpretiert werden, oder wenn Zeichenfolgendaten in einer bestimmten Kultur mit den Konventionen einer anderen Kultur interpretiert werden, können offensichtliche und nur schwer erkennbare Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="14a37-192">Subtle and not so subtle bugs can emerge when non-linguistic string data is interpreted linguistically, or when string data from a particular culture is interpreted using the conventions of another culture.</span></span> <span data-ttu-id="14a37-193">Kanonisches Beispiel ist das Problem mit dem Zeichen "I" im Türkischen.</span><span class="sxs-lookup"><span data-stu-id="14a37-193">The canonical example is the Turkish-I problem.</span></span>

<span data-ttu-id="14a37-194">In beinahe allen lateinischen Alphabetarten,  einschließlich des englischen (USA) Alphabets, ist das Zeichen "i" (\u0069) die Kleinschreibungsvariante des Zeichens "I" (\u0049).</span><span class="sxs-lookup"><span data-stu-id="14a37-194">For nearly all Latin alphabets, including U.S. English, the character "i" (\u0069) is the lowercase version of the character "I" (\u0049).</span></span> <span data-ttu-id="14a37-195">Diese Regel zur Groß- und Kleinschreibung wird von Entwicklern, die in den entsprechenden Kulturen programmieren, leicht als Standard zugrunde gelegt.</span><span class="sxs-lookup"><span data-stu-id="14a37-195">This casing rule quickly becomes the default for someone programming in such a culture.</span></span> <span data-ttu-id="14a37-196">Das türkische Alphabet („tr-TR“) enthält jedoch ein „I“ mit einem Punkt („İ“ bzw. \u0130), welches den Großbuchstaben des Zeichens „i“ darstellt.</span><span class="sxs-lookup"><span data-stu-id="14a37-196">However, the Turkish ("tr-TR") alphabet includes an "I with a dot" character "İ" (\u0130), which is the capital version of "i".</span></span> <span data-ttu-id="14a37-197">Ferner verfügt Türkisch auch über ein kleines „i ohne Punkt“ („ı“ bzw. \u0131), dessen Entsprechung als Großbuchstabe das Zeichen „I“ ist.</span><span class="sxs-lookup"><span data-stu-id="14a37-197">Turkish also includes a lowercase "i without a dot" character, "ı" (\u0131), which capitalizes to "I".</span></span> <span data-ttu-id="14a37-198">Die Kultur Aserbaidschanisch (az-AZ) weist ein analoges Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="14a37-198">This behavior occurs in the Azerbaijani ("az") culture as well.</span></span>

<span data-ttu-id="14a37-199">Annahmen über die Großschreibung von "i" oder die Kleinschreibung von "I" sind daher nicht für alle Kulturen gleichermaßen gültig.</span><span class="sxs-lookup"><span data-stu-id="14a37-199">Therefore, assumptions made about capitalizing "i" or lowercasing "I" are not valid among all cultures.</span></span> <span data-ttu-id="14a37-200">Wenn Sie die Standardüberladungen für Zeichenfolgenvergleichsroutinen verwenden, weisen diese je nach der zugrunde liegenden Kultur Unterschiede auf.</span><span class="sxs-lookup"><span data-stu-id="14a37-200">If you use the default overloads for string comparison routines, they will be subject to variance between cultures.</span></span> <span data-ttu-id="14a37-201">Bei einem Vergleich nicht linguistischer Daten kann die Verwendung der Standardüberladungen zu unerwünschten Ergebnissen führen. Dies wird durch den folgenden Versuch veranschaulicht, einen Vergleich der Zeichenfolgen "file" und "FILE" ohne Beachtung der Groß- und Kleinschreibung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="14a37-201">If the data to be compared is non-linguistic, using the default overloads can produce undesirable results, as the following attempt to perform a case-insensitive comparison of the strings "file" and "FILE" illustrates.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fileUrl = "file";
      Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                       fileUrl.StartsWith("FILE", true, null));
      Console.WriteLine();

      Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                        fileUrl.StartsWith("FILE", true, null));
   }
}
// The example displays the following output:
//       Culture = English (United States)
//       (file == FILE) = True
//       
//       Culture = Turkish (Turkey)
//       (file == FILE) = False
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fileUrl = "file"
      Thread.CurrentThread.CurrentCulture = New CultureInfo("en-US")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                       fileUrl.StartsWith("FILE", True, Nothing))
      Console.WriteLine()

      Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                        fileUrl.StartsWith("FILE", True, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Culture = English (United States)
'       (file == FILE) = True
'       
'       Culture = Turkish (Turkey)
'       (file == FILE) = False
```

<span data-ttu-id="14a37-202">Dieser Vergleich kann signifikante Probleme verursachen, wenn die Kultur versehentlich in sicherheitsrelevanten Einstellungen verwendet wird, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="14a37-202">This comparison could cause significant problems if the culture is inadvertently used in security-sensitive settings, as in the following example.</span></span> <span data-ttu-id="14a37-203">Ein Methodenaufruf wie `IsFileURI("file:")` gibt `true` zurück, wenn die aktuelle Kultur "Englisch (USA)" ist und `false`, wenn die aktuelle Kultur "Türkisch" ist.</span><span class="sxs-lookup"><span data-stu-id="14a37-203">A method call such as `IsFileURI("file:")` returns `true` if the current culture is U.S. English, but `false` if the current culture is Turkish.</span></span> <span data-ttu-id="14a37-204">In einem System mit der Kultur "Türkisch" wäre es daher vorstellbar, dass Sicherheitsvorkehrungen umgangen werden, die den Zugriff auf URIs blockieren, die mit "FILE:" beginnen und nicht zwischen Groß- und Kleinschreibung unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="14a37-204">Thus, on Turkish systems, someone could circumvent security measures that block access to case-insensitive URIs that begin with "FILE:".</span></span>

```csharp
public static bool IsFileURI(String path) 
{
   return path.StartsWith("FILE:", true, null);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
   Return path.StartsWith("FILE:", True, Nothing)
End Function
```

<span data-ttu-id="14a37-205">Stattdessen sollte der Code daher in diesem Fall wie im folgenden Beispiel geschrieben werden, da "file:" als nicht linguistischer und kulturunabhängiger Bezeichner interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="14a37-205">In this case, because "file:" is meant to be interpreted as a non-linguistic, culture-insensitive identifier, the code should instead be written as shown in the following example.</span></span>

```csharp
public static bool IsFileURI(string path) 
{
   return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
    Return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase)
End Function
```

## <a name="ordinal-string-operations"></a><span data-ttu-id="14a37-206">Ordinalzeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="14a37-206">Ordinal String Operations</span></span>

<span data-ttu-id="14a37-207">Der [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)- oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)-Wert in einem Methodenaufruf kennzeichnet einen nicht linguistischen Vergleich, in dem die Features von natürlichen Sprachen ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-207">Specifying the [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) value in a method call signifies a non-linguistic comparison in which the features of natural languages are ignored.</span></span> <span data-ttu-id="14a37-208">Bei Methoden, die mit diesen [StringComparison](xref:System.StringComparison)-Werten aufgerufen werden, werden für Entscheidungen bezüglich Zeichenfolgenoperation einfache Bytevergleiche anstelle von Groß- und Kleinschreibung oder nach Kultur parametrisierten Entsprechungstabellen zugrunde gelegt.</span><span class="sxs-lookup"><span data-stu-id="14a37-208">Methods that are invoked with these [StringComparison](xref:System.StringComparison) values base string operation decisions on simple byte comparisons instead of casing or equivalence tables that are parameterized by culture.</span></span> <span data-ttu-id="14a37-209">In aller Regel ist diese Vorgehensweise am besten für die beabsichtigte Interpretation von Zeichenfolgen geeignet und macht den Code sicherer und zuverlässiger.</span><span class="sxs-lookup"><span data-stu-id="14a37-209">In most cases, this approach best fits the intended interpretation of strings while making code faster and more reliable.</span></span> 

<span data-ttu-id="14a37-210">Ordinalvergleiche sind Zeichenfolgenvergleiche, in denen die einzelnen Bytes einer Zeichenfolge ohne linguistische Interpretation verglichen werden, z. B. entspricht "windows" nicht "Windows".</span><span class="sxs-lookup"><span data-stu-id="14a37-210">Ordinal comparisons are string comparisons in which each byte of each string is compared without linguistic interpretation; for example, "windows" does not match "Windows".</span></span> <span data-ttu-id="14a37-211">Verwenden Sie diesen Vergleich, wenn der Kontext eine exakte Entsprechung von Zeichenfolgen oder eine konservative Entsprechungsrichtlinie verlangt.</span><span class="sxs-lookup"><span data-stu-id="14a37-211">Use this comparison when the context dictates that strings should be matched exactly or demands conservative matching policy.</span></span> <span data-ttu-id="14a37-212">Darüber hinaus werden Ordinalvergleiche am schnellsten durchgeführt, da beim Bestimmen eines Ergebnisses keine linguistischen Regeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-212">Additionally, ordinal comparison is the fastest comparison operation because it applies no linguistic rules when determining a result.</span></span>

<span data-ttu-id="14a37-213">Zeichenfolgen in .NET können eingebettete NULL-Zeichen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="14a37-213">Strings in .NET can contain embedded null characters.</span></span> <span data-ttu-id="14a37-214">Einer der auffälligsten Unterschiede zwischen einem ordinalen und einem kulturabhängigen Vergleich (einschließlich Vergleichen, die die invariante Kultur verwenden) betrifft die Behandlung von eingebetteten NULL-Zeichen in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="14a37-214">One of the clearest differences between ordinal and culture-sensitive comparison (including comparisons that use the invariant culture) concerns the handling of embedded null characters in a string.</span></span> <span data-ttu-id="14a37-215">Wenn Sie die [String](xref:System.String)`Compare`-Methode und die [String](xref:System.String)`Equals`-Methode verwenden, um kulturabhängige Vergleiche (einschließlich Vergleichen, die die invariante Kultur verwenden) durchzuführen, werden diese Zeichen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="14a37-215">These characters are ignored when you use the [String](xref:System.String) `Compare` and [String](xref:System.String) `Equals` methods to perform culture-sensitive comparisons (including comparisons that use the invariant culture).</span></span> <span data-ttu-id="14a37-216">Bei kulturabhängigen Vergleichen können Zeichenfolgen mit eingebetteten NULL-Zeichen daher als gleichwertig mit Zeichenfolgen ohne diese Zeichen angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-216">As a result, in culture-sensitive comparisons, strings that contain embedded null characters can be considered equal to strings that do not.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="14a37-217">Auch wenn eingebettete NULL-Zeichen von Zeichenfolgenvergleichs-Methoden ignoriert werden, bei Zeichenfolgensuch-Methoden wie z.B. [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)) und [String.StartsWith](xref:System.String.StartsWith(System.String)) ist dies nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="14a37-217">Although string comparison methods disregard embedded null characters, string search methods such as [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)), and [String.StartsWith](xref:System.String.StartsWith(System.String)) do not.</span></span> 

<span data-ttu-id="14a37-218">Im folgenden Beispiel wird ein kulturabhängiger Vergleich der Zeichenfolge "Aa" mit einer ähnlichen Zeichenfolge durchgeführt, die mehrere eingebettete NULL-Zeichen zwischen "A" und "a" enthält, und es wird angezeigt, inwieweit die beiden Zeichenfolgen als gleich betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-218">The following example performs a culture-sensitive comparison of the string "Aa" with a similar string that contains several embedded null characters between "A" and "a", and shows how the two strings are considered equal.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string str1 = "Aa";
      string str2 = "A" + new String('\u0000', 3) + "a";
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                        str1, ShowBytes(str1), str2, ShowBytes(str2));
      Console.WriteLine("   With String.Compare:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.InvariantCulture));

      Console.WriteLine("   With String.Equals:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.InvariantCulture));
   }

   private static string ShowBytes(string str)
   {
      string hexString = String.Empty;
      for (int ctr = 0; ctr < str.Length; ctr++)
      {
         string result = String.Empty;
         result = Convert.ToInt32(str[ctr]).ToString("X4");
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2);
         hexString += result;
      }
      return hexString.Trim();
   }
}
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Current Culture: 0
//          Invariant Culture: 0
//       With String.Equals:
//          Current Culture: True
//          Invariant Culture: True
```

```vb
Module Example
   Public Sub Main()
      Dim str1 As String = "Aa"
      Dim str2 As String = "A" + New String(Convert.ToChar(0), 3) + "a"
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                        str1, ShowBytes(str1), str2, ShowBytes(str2))
      Console.WriteLine("   With String.Compare:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.InvariantCulture))

      Console.WriteLine("   With String.Equals:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.InvariantCulture))
   End Sub

   Private Function ShowBytes(str As String) As String
      Dim hexString As String = String.Empty
      For ctr As Integer = 0 To str.Length - 1
         Dim result As String = String.Empty
         result = Convert.ToInt32(str.Chars(ctr)).ToString("X4")
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2)
         hexString += result
      Next
      Return hexString.Trim()
   End Function
End Module
```

<span data-ttu-id="14a37-219">Bei einem Ordinalvergleich werden die Zeichenfolgen jedoch nicht als gleich betrachtet, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="14a37-219">However, the strings are not considered equal when you use ordinal comparison, as the following example shows.</span></span>

```csharp
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                  str1, ShowBytes(str1), str2, ShowBytes(str2));
Console.WriteLine("   With String.Compare:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Compare(str1, str2, StringComparison.Ordinal));

Console.WriteLine("   With String.Equals:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Equals(str1, str2, StringComparison.Ordinal));
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Ordinal: 97
//       With String.Equals:
//          Ordinal: False
```

```vb
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                  str1, ShowBytes(str1), str2, ShowBytes(str2))
Console.WriteLine("   With String.Compare:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Compare(str1, str2, StringComparison.Ordinal))

Console.WriteLine("   With String.Equals:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Equals(str1, str2, StringComparison.Ordinal))
' The example displays the following output:
'    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
'       With String.Compare:
'          Ordinal: 97
'       With String.Equals:
'          Ordinal: False
```

<span data-ttu-id="14a37-220">Ordinalvergleiche, bei denen die Groß- und Kleinschreibung nicht beachtet wird, folgen als nächster konservativer Ansatz.</span><span class="sxs-lookup"><span data-stu-id="14a37-220">Case-insensitive ordinal comparisons are the next most conservative approach.</span></span> <span data-ttu-id="14a37-221">Diese Vergleichen ignorieren die Groß- und Kleinschreibung i. d. R.; "windows" entspricht dann beispielsweise "Windows".</span><span class="sxs-lookup"><span data-stu-id="14a37-221">These comparisons ignore most casing; for example, "windows" matches "Windows".</span></span> <span data-ttu-id="14a37-222">Im Hinblick auf ASCII-Zeichen entspricht diese Richtlinie [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), mit der Ausnahme, dass die üblichen ASCII-Schreibungsregeln nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-222">When dealing with ASCII characters, this policy is equivalent to [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), except that it ignores the usual ASCII casing.</span></span> <span data-ttu-id="14a37-223">Ein beliebiges Zeichen in \[A, Z\] (\u0041-\u005A) entspricht daher dem zugehörigen Zeichen in \[a, z\] (\u0061-\007A).</span><span class="sxs-lookup"><span data-stu-id="14a37-223">Therefore, any character in \[A, Z\] (\u0041-\u005A) matches the corresponding character in \[a,z\] (\u0061-\007A).</span></span> <span data-ttu-id="14a37-224">Die Groß- und Kleinschreibung außerhalb des ASCII-Bereichs verwendet die Tabellen der invarianten Kultur.</span><span class="sxs-lookup"><span data-stu-id="14a37-224">Casing outside the ASCII range uses the invariant culture's tables.</span></span> <span data-ttu-id="14a37-225">Daher entspricht der folgende Vergleich</span><span class="sxs-lookup"><span data-stu-id="14a37-225">Therefore, the following comparison:</span></span>

```csharp
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase);
```

```vb
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase)
```

<span data-ttu-id="14a37-226">dem nachstehenden Vergleich (ist jedoch schneller):</span><span class="sxs-lookup"><span data-stu-id="14a37-226">is equivalent to (but faster than) this comparison:</span></span> 

```csharp
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal);
```

```vb
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal)
```

<span data-ttu-id="14a37-227">Diese Vergleiche werden immer noch sehr schnell durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="14a37-227">These comparisons are still very fast.</span></span>

<span data-ttu-id="14a37-228">Sowohl [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) als auch [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) verwendet die Binärwerte direkt und eignet sich am besten für Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="14a37-228">Both [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) and [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) use the binary values directly, and are best suited for matching.</span></span> <span data-ttu-id="14a37-229">Wenn Sie nicht sicher über die Vergleichseinstellungen sind, verwenden Sie einen dieser beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="14a37-229">When you are not sure about your comparison settings, use one of these two values.</span></span> <span data-ttu-id="14a37-230">Da hier jedoch ein Vergleich auf Byteebene durchgeführt wird, erfolgt die Sortierung nicht anhand einer linguistischen Sortierreihenfolge (analog zu einem englischen Wörterbuch), sondern anhand einer binären Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="14a37-230">However, because they perform a byte-by-byte comparison, they do not sort by a linguistic sort order (like an English dictionary) but by a binary sort order.</span></span> <span data-ttu-id="14a37-231">Die Ergebnisse erscheinen Benutzern möglicherweise in den meisten Kontexten seltsam.</span><span class="sxs-lookup"><span data-stu-id="14a37-231">The results may look odd in most contexts if displayed to users.</span></span>

<span data-ttu-id="14a37-232">Ordinalsemantik ist die Standardeinstellung für [String](xref:System.String)`Equals`-Überladungen, die kein [StringComparison](xref:System.StringComparison)-Argument (einschließlich des Gleichheitsoperators) enthalten.</span><span class="sxs-lookup"><span data-stu-id="14a37-232">Ordinal semantics are the default for [String](xref:System.String) `Equals` overloads that do not include a [StringComparison](xref:System.StringComparison) argument (including the equality operator).</span></span> <span data-ttu-id="14a37-233">In jedem Fall wird empfohlen, eine Überladung mit einem [StringComparison](xref:System.StringComparison)-Parameter aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="14a37-233">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter.</span></span>

### <a name="string-operations-that-use-the-invariant-culture"></a><span data-ttu-id="14a37-234">Zeichenfolgenoperationen mit der invarianten Kultur</span><span class="sxs-lookup"><span data-stu-id="14a37-234">String operations that use the invariant culture</span></span>

<span data-ttu-id="14a37-235">Vergleiche mit der invarianten Kultur verwenden die [CompareInfo](xref:System.Globalization.CompareInfo)-Eigenschaft, die von der statischen [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="14a37-235">Comparisons with the invariant culture use the [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="14a37-236">Dieses Verhalten ist in allen Systemen gleich: Zeichen außerhalb des Bereichs werden in Zeichen übersetzt, von denen angenommen wird, dass es sich um die invarianten Entsprechungen handelt.</span><span class="sxs-lookup"><span data-stu-id="14a37-236">This behavior is the same on all systems; it translates any characters outside its range into what it believes are equivalent invariant characters.</span></span> <span data-ttu-id="14a37-237">Diese Richtlinie kann für das kulturübergreifende Beibehalten eines Satzes von Zeichenfolgenverhalten hilfreich sein, führt jedoch oftmals zu unerwarteten Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="14a37-237">This policy can be useful for maintaining one set of string behavior across cultures, but it often provides unexpected results.</span></span>

<span data-ttu-id="14a37-238">Vergleiche mit der invarianten Kultur, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, verwenden für Vergleichsinformationen ebenfalls die statische [CompareInfo](xref:System.Globalization.CompareInfo)-Eigenschaft, die von der statischen [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="14a37-238">Case-insensitive comparisons with the invariant culture use the static [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property for comparison information as well.</span></span> <span data-ttu-id="14a37-239">Alle Unterschiede bezüglich der Groß- und Kleinschreibung in den übersetzten Zeichen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="14a37-239">Any case differences among these translated characters are ignored.</span></span>

<span data-ttu-id="14a37-240">Das [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)-Objekt führt dazu, dass eine [String](xref:System.String)`Compare`-Methode bestimmte Zeichensätze als äquivalent interpretiert.</span><span class="sxs-lookup"><span data-stu-id="14a37-240">The [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) object makes a [String](xref:System.String) `Compare` method interpret certain sets of characters as equivalent.</span></span> <span data-ttu-id="14a37-241">Die folgende Äquivalenz ist beispielsweise in der invarianten Kultur gültig:</span><span class="sxs-lookup"><span data-stu-id="14a37-241">For example, the following equivalence is valid under the invariant culture:</span></span>

<span data-ttu-id="14a37-242">InvariantCulture: a + ̊ = å</span><span class="sxs-lookup"><span data-stu-id="14a37-242">InvariantCulture: a + ̊ = å</span></span>

<span data-ttu-id="14a37-243">Der lateinische Kleinbuchstabe „a“ (\u0061) wird, wenn er sich neben dem kombinierenden übergesetzten Ring "+ " ̊" (\u030a) befindet, als lateinischer Kleinbuchstabe mit übergesetztem Ring „å“ (\u00e5) interpretiert.</span><span class="sxs-lookup"><span data-stu-id="14a37-243">The latin small lette A character "a" (\u0061), when it is next to the combining ring above character "+ " ̊" (\u030a), is interpreted as the latin small letter A with ring above character "å" (\u00e5).</span></span> <span data-ttu-id="14a37-244">Wie das folgende Beispiel zeigt, unterscheidet sich dieses Verhalten vom Ordinalvergleich.</span><span class="sxs-lookup"><span data-stu-id="14a37-244">As the following example shows, this behavior differs from ordinal comparison.</span></span>

```csharp
string separated = "\u0061\u030a";
string combined = "\u00e5";

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}",
                  separated, combined, 
                  String.Compare(separated, combined, 
                                 StringComparison.InvariantCulture) == 0);

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}",
                  separated, combined,
                  String.Compare(separated, combined, 
                                 StringComparison.Ordinal) == 0);
// The example displays the following output:
//    Equal sort weight of a° and å using InvariantCulture: True
//    Equal sort weight of a° and å using Ordinal: False 
```

```vb
Dim separated As String = ChrW(&h61) + ChrW(&h30a)
Dim combined As String = ChrW(&he5)

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _ 
                                 StringComparison.InvariantCulture) = 0)

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _
                                 StringComparison.Ordinal) = 0)
' The example displays the following output:
'    Equal sort weight of a° and å using InvariantCulture: True
'    Equal sort weight of a° and å using Ordinal: False
```

<span data-ttu-id="14a37-245">Wenn sie Dateinamen, Cookies oder andere Elemente interpretieren, die eine Kombination wie „å“ enthalten können, bieten Ordinalvergleiche immer noch das transparenteste und am besten geeignete Verhalten an.</span><span class="sxs-lookup"><span data-stu-id="14a37-245">When interpreting file names, cookies, or anything else where a combination such as "å" can appear, ordinal comparisons still offer the most transparent and fitting behavior.</span></span>

<span data-ttu-id="14a37-246">Insgesamt verfügt die invariante Kultur nur über sehr wenige Eigenschaften, die für einen Vergleich hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="14a37-246">On balance, the invariant culture has very few properties that make it useful for comparison.</span></span> <span data-ttu-id="14a37-247">Sie führt Vergleiche mit linguistischer Relevanz durch und kann daher keine vollständige symbolische Äquivalenz garantieren, eignet sich jedoch nicht unbedingt für die Anzeige in einer beliebigen Kultur.</span><span class="sxs-lookup"><span data-stu-id="14a37-247">It does comparison in a linguistically relevant manner, which prevents it from guaranteeing full symbolic equivalence, but it is not the choice for display in any culture.</span></span> <span data-ttu-id="14a37-248">Wenn beispielsweise eine große Datendatei mit einer Liste sortierter Anzeigebezeichner einer Anwendung angehört, würde das Hinzufügen von Elementen zu dieser Liste einen Einfügevorgang mit invarianter Sortierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="14a37-248">For example, if a large data file that contains a list of sorted identifiers for display accompanies an application, adding to this list would require an insertion with invariant-style sorting.</span></span>

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a><span data-ttu-id="14a37-249">Auswählen eines StringComparison-Members für den Methodenaufruf</span><span class="sxs-lookup"><span data-stu-id="14a37-249">Choosing a StringComparison member for your method call</span></span>

<span data-ttu-id="14a37-250">In der folgenden Tabelle wird die Zuordnung von semantischem Zeichenfolgenkontext zu einem [StringComparison](xref:System.StringComparison)-Enumerationsmember beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14a37-250">The following table outlines the mapping from semantic string context to a [StringComparison](xref:System.StringComparison) enumeration member.</span></span>

<span data-ttu-id="14a37-251">Daten</span><span class="sxs-lookup"><span data-stu-id="14a37-251">Data</span></span> | <span data-ttu-id="14a37-252">Verhalten</span><span class="sxs-lookup"><span data-stu-id="14a37-252">Behavior</span></span> | <span data-ttu-id="14a37-253">System.StringComparison-Entsprechungswert</span><span class="sxs-lookup"><span data-stu-id="14a37-253">Corresponding System.StringComparison value</span></span>
---- | -------- | -------------------------------------------
<span data-ttu-id="14a37-254">Interne Bezeichner, die Groß-/Kleinschreibung beachten, Bezeichner in Standards wie XML und HTTP, die Groß-/Kleinschreibung beachten, oder sicherheitsbezogene Einstellungen, die Groß-/Kleinschreibung beachten.</span><span class="sxs-lookup"><span data-stu-id="14a37-254">Case-sensitive internal identifiers, case-sensitive identifiers in standards such as XML and HTTP, or case-sensitive security-related settings.</span></span> | <span data-ttu-id="14a37-255">Ein nicht linguistischer Bezeichner mit exakt übereinstimmenden Bytes.</span><span class="sxs-lookup"><span data-stu-id="14a37-255">A non-linguistic identifier, where bytes match exactly.</span></span> | [<span data-ttu-id="14a37-256">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="14a37-256">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal)
<span data-ttu-id="14a37-257">Interne Bezeichner, die Groß-/Kleinschreibung beachten, Bezeichner in Standards wie XML und HTTP, Dateipfade, Registrierungsschlüssel und Werte, Umgebungsvariablen, Ressourcenbezeichner (z.B. Handlenamen), die Groß-/Kleinschreibung beachten, oder sicherheitsbezogene Einstellungen, die Groß-/Kleinschreibung beachten.</span><span class="sxs-lookup"><span data-stu-id="14a37-257">Case-insensitive internal identifiers, case-insensitive identifiers in standards such as XML and HTTP, file paths, registry keys and values, environment variables, resource identifiers (for example, handle names), or case-insensitive security-related settings.</span></span> | <span data-ttu-id="14a37-258">Ein nicht linguistischer Bezeichner, wo die Groß-/Kleinschreibung irrelevant ist.</span><span class="sxs-lookup"><span data-stu-id="14a37-258">A non-linguistic identifier, where case is irrelevant.</span></span> | [<span data-ttu-id="14a37-259">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="14a37-259">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase)
<span data-ttu-id="14a37-260">Daten, die für den Benutzer angezeigt werden, oder die meisten Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="14a37-260">Data displayed to the user or most user input.</span></span> | <span data-ttu-id="14a37-261">Daten, die lokale linguistische Regeln erfordern.</span><span class="sxs-lookup"><span data-stu-id="14a37-261">Data that requires local linguistic customs.</span></span> | <span data-ttu-id="14a37-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) oder [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span><span class="sxs-lookup"><span data-stu-id="14a37-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) or [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span></span>

## <a name="common-string-comparison-methods"></a><span data-ttu-id="14a37-263">Allgemeine Methoden für den Zeichenfolgenvergleich</span><span class="sxs-lookup"><span data-stu-id="14a37-263">Common string comparison methods</span></span>

<span data-ttu-id="14a37-264">In den folgenden Abschnitten werden die Methoden beschrieben, die am häufigsten für Zeichenfolgenvergleiche verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-264">The following sections describe the methods that are most commonly used for string comparison.</span></span>

### <a name="stringcompare"></a><span data-ttu-id="14a37-265">String.Compare</span><span class="sxs-lookup"><span data-stu-id="14a37-265">String.Compare</span></span>

<span data-ttu-id="14a37-266">Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="14a37-266">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="14a37-267">Der Aufruf dieser Methode stellt die zentrale Operation für Zeichenfolgeninterpretation dar. Aus diesem Grund sollten alle Instanzen von Methodenaufrufen untersucht werden, um zu bestimmen, ob Zeichenfolgen anhand der aktuellen Kultur oder unabhängig von der Kultur (symbolisch) interpretiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="14a37-267">As the operation most central to string interpretation, all instances of these method calls should be examined to determine whether strings should be interpreted according to the current culture, or dissociated from the culture (symbolically).</span></span> <span data-ttu-id="14a37-268">Üblicherweise handelt es sich um eine symbolische Interpretation, und stattdessen sollte ein [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)-Vergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-268">Typically, it is the latter, and a [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) comparison should be used instead.</span></span>

<span data-ttu-id="14a37-269">Die [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo)-Klasse, die von der [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo)-Eigenschaft zurückgegeben wird, enthält auch eine [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions))-Methode, die zahlreiche Vergleichsoptionen (ordinal, ohne Leerraumzeichen, ohne Zeichen vom Typ Kana usw.) über die [CompareOptions](xref:System.Globalization.CompareOptions)-Flagenumeration zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="14a37-269">The [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo) class, which is returned by the [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo) property, also includes a [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) method that provides a large number of matching options (ordinal, ignoring white space, ignoring kana type, and so on) by means of the [CompareOptions](xref:System.Globalization.CompareOptions) flag enumeration.</span></span> 

### <a name="stringcompareto"></a><span data-ttu-id="14a37-270">String.CompareTo</span><span class="sxs-lookup"><span data-stu-id="14a37-270">String.CompareTo</span></span>

<span data-ttu-id="14a37-271">Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="14a37-271">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="14a37-272">Diese Methode bietet derzeit keine Überladung an, die einen [StringComparison](xref:System.StringComparison)-Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="14a37-272">This method does not currently offer an overload that specifies a [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="14a37-273">Es ist in der Regel möglich, diese Methode in die empfohlene [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison))-Form zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="14a37-273">It is usually possible to convert this method to the recommended [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)) form.</span></span>

<span data-ttu-id="14a37-274">Diese Methode wird von Typen implementiert, die die [IComparable](xref:System.IComparable)- und [IComparable&lt;T&gt;](xref:System.IComparable%601)-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="14a37-274">Types that implement the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces implement this method.</span></span> <span data-ttu-id="14a37-275">Da der [StringComparison](xref:System.StringComparison)-Parameter hier nicht verfügbar ist, ermöglichen implementierende Typen oftmals das Angeben eines [StringComparer](xref:System.StringComparer) im entsprechenden Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="14a37-275">Because it does not offer the option of a [StringComparison](xref:System.StringComparison) parameter, implementing types often let the user specify a [StringComparer](xref:System.StringComparer) in their constructor.</span></span> <span data-ttu-id="14a37-276">Im folgenden Beispiel wird eine `FileName`-Klasse definiert, deren Klassenkonstruktor einen [StringComparer](xref:System.StringComparer)-Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="14a37-276">The following example defines a `FileName` class whose class constructor includes a [StringComparer](xref:System.StringComparer) parameter.</span></span> <span data-ttu-id="14a37-277">Dieses [StringComparer](xref:System.StringComparer)-Objekt wird dann in der `FileName.CompareTo`-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="14a37-277">This [StringComparer](xref:System.StringComparer) object is then used in the `FileName.CompareTo` method.</span></span>

```csharp
using System;

public class FileName : IComparable
{
   string fname;
   StringComparer comparer; 

   public FileName(string name, StringComparer comparer)
   {
      if (String.IsNullOrEmpty(name))
         throw new ArgumentNullException("name");

      this.fname = name;

      if (comparer != null)
         this.comparer = comparer;
      else
         this.comparer = StringComparer.OrdinalIgnoreCase;
   }

   public string Name
   {
      get { return fname; }
   }

   public int CompareTo(object obj)
   {
      if (obj == null) return 1;

      if (! (obj is FileName))
         return comparer.Compare(this.fname, obj.ToString());
      else
         return comparer.Compare(this.fname, ((FileName) obj).Name);
   }
}
```

```vb
Public Class FileName : Implements IComparable
   Dim fname As String
   Dim comparer As StringComparer 

   Public Sub New(name As String, comparer As StringComparer)
      If String.IsNullOrEmpty(name) Then
         Throw New ArgumentNullException("name")
      End If

      Me.fname = name

      If comparer IsNot Nothing Then
         Me.comparer = comparer
      Else
         Me.comparer = StringComparer.OrdinalIgnoreCase
      End If      
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return fname
      End Get   
   End Property

   Public Function CompareTo(obj As Object) As Integer _
          Implements IComparable.CompareTo
      If obj Is Nothing Then Return 1

      If Not TypeOf obj Is FileName Then
         obj = obj.ToString()
      Else
         obj = CType(obj, FileName).Name
      End If         
      Return comparer.Compare(Me.fname, obj)
   End Function
End Class
```

### <a name="stringequals"></a><span data-ttu-id="14a37-278">String.Equals</span><span class="sxs-lookup"><span data-stu-id="14a37-278">String.Equals</span></span>

<span data-ttu-id="14a37-279">Standardinterpretation: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="14a37-279">Default interpretation: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="14a37-280">Mit der [String](xref:System.String)-Klasse können Sie eine Überprüfung auf Gleichheit durchführen, indem Sie die Überladungen der statischen `Equals`-Methode oder der entsprechenden Instanzenmethode aufrufen, oder indem Sie den statischen Gleichheitsoperator verwenden.</span><span class="sxs-lookup"><span data-stu-id="14a37-280">The [String](xref:System.String) class lets you test for equality by calling either the static or instance `Equals` method overloads, or by using the static equality operator.</span></span> <span data-ttu-id="14a37-281">Die Überladungen und der Operator verwenden standardmäßig einen Ordinalvergleich .</span><span class="sxs-lookup"><span data-stu-id="14a37-281">The overloads and operator use ordinal comparison by default.</span></span> <span data-ttu-id="14a37-282">Unabhängig davon wird jedoch empfohlen, eine Überladung aufzurufen, die den [StringComparison](xref:System.StringComparison)-Typ explizit angibt; dies gilt auch, wenn Sie einen Ordinalvergleich ausführen möchten. Auf diese Weise können bestimmte Zeichenfolgeninterpretationen leichter in Code gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-282">However, we still recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type even if you want to perform an ordinal comparison; this makes it easier to search code for a certain string interpretation.</span></span> 

### <a name="stringtoupper-and-stringtolower"></a><span data-ttu-id="14a37-283">String.ToUpper und String.ToLower</span><span class="sxs-lookup"><span data-stu-id="14a37-283">String.ToUpper and String.ToLower</span></span>

<span data-ttu-id="14a37-284">Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="14a37-284">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="14a37-285">Diese Methoden sollten mit besonderer Sorgfalt verwendet werden, da das Erzwingen der Groß- oder Kleinschreibung einer Zeichenfolge oftmals unabhängig von der Schreibweise als kleine Normalisierung für Zeichenfolgenvergleiche verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14a37-285">You should be careful when you use these methods, because forcing a string to a uppercase or lowercase is often used as a small normalization for comparing strings regardless of case.</span></span> <span data-ttu-id="14a37-286">Wenn dies der Fall ist, sollten Sie einen Vergleich ohne Beachtung der Groß- und Kleinschreibung in Erwägung ziehen.</span><span class="sxs-lookup"><span data-stu-id="14a37-286">If so, consider using a case-insensitive comparison.</span></span> 

<span data-ttu-id="14a37-287">Die [String.ToUpperInvariant](xref:System.String.ToUpperInvariant)- und [String.ToLowerInvariant](xref:System.String.ToLowerInvariant)-Methode sind ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="14a37-287">The [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) and [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) methods are also available.</span></span> <span data-ttu-id="14a37-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) wird standardmäßig zur Normalisierung der Schreibweise verwendet.</span><span class="sxs-lookup"><span data-stu-id="14a37-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) is the standard way to normalize case.</span></span> <span data-ttu-id="14a37-289">Mit [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) durchgeführte Vergleiche entsprechen der Zusammensetzung von zwei Aufrufen: Aufruf von [ToUpperInvariant](xref:System.String.ToUpperInvariant) für beide Zeichenfolgenargumente und ein Vergleich mithilfe von [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="14a37-289">Comparisons made using [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) are behaviorally the composition of two calls: calling [ToUpperInvariant](xref:System.String.ToUpperInvariant) on both string arguments, and doing a comparison using [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="14a37-290">Überladungen sind auch für die Konvertierung in Groß- und Kleinschreibung in einer bestimmten Kultur verfügbar. Dazu wird ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt übergeben, das die Kultur für die Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="14a37-290">Overloads are also available for converting to uppercase and lowercase in a specific culture, by passing a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents that culture to the method.</span></span>

### <a name="chartoupper-and-chartolower"></a><span data-ttu-id="14a37-291">Char.ToUpper und Char.ToLower</span><span class="sxs-lookup"><span data-stu-id="14a37-291">Char.ToUpper and Char.ToLower</span></span>

<span data-ttu-id="14a37-292">Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="14a37-292">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="14a37-293">Diese Methoden funktionieren ähnlich wie die [String.ToUpper](xref:System.String.ToUpper)-Methode und [String.ToLower](xref:System.String.ToLower)-Methode, die im vorherigen Abschnitt beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-293">These methods work similarly to the [String.ToUpper](xref:System.String.ToUpper) and [String.ToLower](xref:System.String.ToLower) methods described in the previous section.</span></span>

### <a name="stringstartswith-and-stringendswith"></a><span data-ttu-id="14a37-294">String.StartsWith und String.EndsWith</span><span class="sxs-lookup"><span data-stu-id="14a37-294">String.StartsWith and String.EndsWith</span></span>

<span data-ttu-id="14a37-295">Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="14a37-295">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="14a37-296">Standardmäßig führen beide Methoden einen kulturabhängigen Vergleich durch.</span><span class="sxs-lookup"><span data-stu-id="14a37-296">By default, both of these methods perform a culture-sensitive comparison.</span></span>

### <a name="stringindexof-and-stringlastindexof"></a><span data-ttu-id="14a37-297">String.IndexOf und String.LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="14a37-297">String.IndexOf and String.LastIndexOf</span></span>

<span data-ttu-id="14a37-298">Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="14a37-298">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="14a37-299">Die Durchführung von Vergleichen durch die Standardüberladungen dieser Methoden ist nicht konsistent.</span><span class="sxs-lookup"><span data-stu-id="14a37-299">There is a lack of consistency in how the default overloads of these methods perform comparisons.</span></span> <span data-ttu-id="14a37-300">Alle [String](xref:System.String)`IndexOf`- und [String](xref:System.String)`LastIndexOf`-Methoden mit einem [Char](xref:System.Char)-Parameter führen einen Ordinalvergleich durch. Die [String](xref:System.String)`IndexOf`- und die [String`](xref:System.String) `LastIndexOf\`-Methode mit einem [String](xref:System.String)-Parameter führen dagegen einen kulturabhängigen Vergleich durch.</span><span class="sxs-lookup"><span data-stu-id="14a37-300">All [String](xref:System.String) `IndexOf` and [String](xref:System.String) `LastIndexOf` methods that include a [Char](xref:System.Char) parameter perform an ordinal comparison, but the default [String](xref:System.String) `IndexOf` and [String`](xref:System.String) `LastIndexOf\` methods that include a [String](xref:System.String) parameter perform a culture-sensitive comparison.</span></span> 

<span data-ttu-id="14a37-301">Wenn Sie die ` `IndexOf-` or `LastIndexOf\`-Methode aufrufen und eine Zeichenfolge übergeben, die in der aktuellen Instanz gesucht werden soll, empfiehlt es sich, eine Überladung aufrufen, die den [StringComparison](xref:System.StringComparison)-Typ explizit angibt.</span><span class="sxs-lookup"><span data-stu-id="14a37-301">If you call ` `IndexOf` or `LastIndexOf\` method and pass it a string to locate in the current instance, we recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="14a37-302">Mit den Überladungen, die ein [Char](xref:System.Char)-Argument enthalten, können Sie keinen [StringComparison](xref:System.StringComparison)-Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-302">The overloads that include a [Char](xref:System.Char) argument do not allow you to specify a [StringComparison](xref:System.StringComparison) type.</span></span>

## <a name="methods-that-perform-string-comparison-indirectly"></a><span data-ttu-id="14a37-303">Methoden für den indirekten Zeichenfolgenvergleich</span><span class="sxs-lookup"><span data-stu-id="14a37-303">Methods that perform string comparison indirectly</span></span>

<span data-ttu-id="14a37-304">Einige Methoden, die keine Zeichenfolgenmethoden darstellen, und deren zentrale Operation ein Zeichenfolgenvergleich ist, verwenden den [StringComparer](xref:System.StringComparer)-Typ.</span><span class="sxs-lookup"><span data-stu-id="14a37-304">Some non-string methods that have string comparison as a central operation use the [StringComparer](xref:System.StringComparer) type.</span></span> <span data-ttu-id="14a37-305">Die [StringComparer](xref:System.StringComparer)-Klasse enthält vier statische Eigenschaften, die [StringComparer](xref:System.StringComparer)-Instanzen zurückgeben, deren `Compare`-Methoden folgende Arten von Zeichenfolgenvergleichen durchführen:</span><span class="sxs-lookup"><span data-stu-id="14a37-305">The [StringComparer](xref:System.StringComparer) class includes four static properties that return [StringComparer](xref:System.StringComparer) instances whose `Compare` methods perform the following types of string comparisons:</span></span>

* <span data-ttu-id="14a37-306">Kulturabhängige Zeichenfolgenvergleiche mit der aktuellen Kultur.</span><span class="sxs-lookup"><span data-stu-id="14a37-306">Culture-sensitive string comparisons using the current culture.</span></span> <span data-ttu-id="14a37-307">Dieses [StringComparer](xref:System.StringComparer)-Objekt wird von der [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture)-Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-307">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture) property.</span></span>

* <span data-ttu-id="14a37-308">Vergleiche mit der aktuellen Kultur ohne Beachtung der Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="14a37-308">Case-insensitive comparisons using the current culture.</span></span> <span data-ttu-id="14a37-309">Dieses [StringComparer](xref:System.StringComparer)-Objekt wird von der [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase)-Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-309">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase) property.</span></span>

* <span data-ttu-id="14a37-310">Ordinalvergleich.</span><span class="sxs-lookup"><span data-stu-id="14a37-310">Ordinal comparison.</span></span> <span data-ttu-id="14a37-311">Dieses [StringComparer](xref:System.StringComparer)-Objekt wird von der [StringComparer.Ordinal](xref:System.StringComparer.Ordinal)-Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-311">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.Ordinal](xref:System.StringComparer.Ordinal) property.</span></span> 

* <span data-ttu-id="14a37-312">Ordinalvergleich ohne Beachtung der Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="14a37-312">Case-insensitive ordinal comparison.</span></span> <span data-ttu-id="14a37-313">Dieses [StringComparer](xref:System.StringComparer)-Objekt wird von der [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)-Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-313">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span>

### <a name="arraysort-and-arraybinarysearch"></a><span data-ttu-id="14a37-314">Array.Sort und Array.BinarySearch</span><span class="sxs-lookup"><span data-stu-id="14a37-314">Array.Sort and Array.BinarySearch</span></span>

<span data-ttu-id="14a37-315">Standardinterpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="14a37-315">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="14a37-316">Wenn Sie Daten in einer Auflistung speichern oder beibehaltene Daten aus einer Datei oder einer Datenbank in eine Auflistung lesen, können die Invarianten in der Auflistung durch einen Wechsel der aktuellen Kultur ungültig werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-316">When you store any data in a collection, or read persisted data from a file or database into a collection, switching the current culture can invalidate the invariants in the collection.</span></span> <span data-ttu-id="14a37-317">Die [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object))-Methode geht davon aus, dass die Elemente im zu durchsuchenden Array bereits sortiert wurden.</span><span class="sxs-lookup"><span data-stu-id="14a37-317">The [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) method assumes that the elements in the array to be searched are already sorted.</span></span> <span data-ttu-id="14a37-318">Um die einzelnen Zeichenfolgenelemente im Array zu sortieren, ruft die [Array.Sort](xref:System.Array.Sort(System.Array))-Methode die String.`Compare`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="14a37-318">To sort any string element in the array, the [Array.Sort](xref:System.Array.Sort(System.Array)) method calls the [String] `Compare` method to order individual elements.</span></span> <span data-ttu-id="14a37-319">Kulturabhängige Vergleich bergen ein gewisses Risiko, falls sich die Kultur zwischen dem Zeitpunkt der Sortierung des Arrays und dem Durchsuchen des Inhalts ändert.</span><span class="sxs-lookup"><span data-stu-id="14a37-319">Using a culture-sensitive comparer can be dangerous if the culture changes between the time that the array is sorted and its contents are searched.</span></span> <span data-ttu-id="14a37-320">Im folgenden Code wird das Speichern und Abrufen beispielsweise für den Comparer ausgeführt, der implizit von der `Thread.CurrentThread.CurrentCulture`-Eigenschaft bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="14a37-320">For example, in the following code, storage and retrieval operate on the comparer that is provided implicitly by the `Thread.CurrentThread.CurrentCulture` property.</span></span> <span data-ttu-id="14a37-321">Wenn sich die Kultur zwischen dem Aufruf von `StoreNames` und dem Aufruf von `DoesNameExist` möglicherweise ändert, kann bei der binären Suche ein Fehler auftreten; dies gilt insbesondere, wenn der Arrayinhalt zwischen den beiden Methodenaufrufen beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="14a37-321">If the culture can change between the calls to `StoreNames` and `DoesNameExist`, and especially if the array contents are persisted somewhere between the two method calls, the binary search may fail.</span></span> 

```csharp
// Incorrect.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names); // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name) >= 0);  // Line B.
}
```

```vb
' Incorrect.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names)          ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name) >= 0      ' Line B.
End Function
```

<span data-ttu-id="14a37-322">Eine empfohlene Variante wird im folgenden Beispiel angezeigt, in dem die gleiche (kulturunabhängige) Ordinalvergleichsmethode verwendet wird, um das Array zu sortieren und zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="14a37-322">A recommended variation appears in the following example, which uses the same ordinal (culture-insensitive) comparison method both to sort and to search the array.</span></span> <span data-ttu-id="14a37-323">Der Änderungscode wird in den zwei Beispielen in den Zeilen mit der Bezeichnung `Line A` und `Line B` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14a37-323">The change code is reflected in the lines labeled `Line A` and `Line B` in the two examples.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.Ordinal);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.Ordinal) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.Ordinal)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.Ordinal) >= 0      ' Line B.
End Function
```

<span data-ttu-id="14a37-324">Wenn diese Daten beibehalten und zwischen Kulturen verschoben werden, und wenn eine Sortierung verwendet wird, um die Daten für den Benutzer anzuzeigen, können Sie `StringComparison.InvariantCulture` verwenden, da durch die linguistische Verarbeitung eine bessere Benutzerausgabe erzielt wird und Änderungen der Kultur keine Auswirkungen haben.</span><span class="sxs-lookup"><span data-stu-id="14a37-324">If this data is persisted and moved across cultures, and sorting is used to present this data to the user, you might consider using `StringComparison.InvariantCulture`, which operates linguistically for better user output but is unaffected by changes in culture.</span></span> <span data-ttu-id="14a37-325">Im folgenden Beispiel werden die zwei vorherigen Beispiele geändert, um die invariante Kultur zum Sortieren und Durchsuchen des Arrays zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="14a37-325">The following example modifies the two previous examples to use the invariant culture for sorting and searching the array.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.InvariantCulture);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.InvariantCulture) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.InvariantCulture)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.InvariantCulture) >= 0      ' Line B.
End Function
```

### <a name="collections-example-hashtable-constructor"></a><span data-ttu-id="14a37-326">Beispiel für Auflistungen: Hashtable-Konstruktor</span><span class="sxs-lookup"><span data-stu-id="14a37-326">Collections Example: Hashtable Constructor</span></span>

<span data-ttu-id="14a37-327">Auch beim Hashen von Zeichenfolgen können sich, je nachdem, wie die Zeichenfolgen verglichen werden, Auswirkungen auf die Operation ergeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-327">Hashing strings provides a second example of an operation that is affected by the way in which strings are compared.</span></span> 

<span data-ttu-id="14a37-328">Im folgenden Beispiel wird ein [Hashtable](xref:System.Collections.Hashtable)-Objekt durch Übergabe des [StringComparer](xref:System.StringComparer)-Objekts instanziiert, das von der [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="14a37-328">The following example instantiates a [Hashtable](xref:System.Collections.Hashtable) object by passing it the [StringComparer](xref:System.StringComparer) object that is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span> <span data-ttu-id="14a37-329">Da eine Klasse [StringComparer](xref:System.StringComparer), die von [StringComparer](xref:System.StringComparer) abgeleitet wird, die [IEqualityComparer](xref:System.Collections.IEqualityComparer)-Schnittstelle implementiert, wird die [GetHashCode](xref:System.Collections.IEqualityComparer)-Methode verwendet, um den Hashcode von Zeichenfolgen in der Hashtabelle zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="14a37-329">Because a class [StringComparer](xref:System.StringComparer) that is derived from [StringComparer](xref:System.StringComparer) implements the [IEqualityComparer](xref:System.Collections.IEqualityComparer) interface, its [GetHashCode](xref:System.Collections.IEqualityComparer) method is used to compute the hash code of strings in the hash table.</span></span>

```csharp
const int initialTableCapacity = 100;
Hashtable h;

public void PopulateFileTable(string directory)
{
   h = new Hashtable(initialTableCapacity, 
                     StringComparer.OrdinalIgnoreCase);

   foreach (string file in Directory.GetFiles(directory))
         h.Add(file, File.GetCreationTime(file));
}

public void PrintCreationTime(string targetFile)
{
   Object dt = h[targetFile];
   if (dt != null)
   {
      Console.WriteLine("File {0} was created at time {1}.",
         targetFile, 
         (DateTime) dt);
   }
   else
   {
      Console.WriteLine("File {0} does not exist.", targetFile);
   }
}
```

```vb
Const initialTableCapacity As Integer = 100
Dim h As Hashtable

Public Sub PopulateFileTable(dir As String)
   h = New Hashtable(initialTableCapacity, _
                     StringComparer.OrdinalIgnoreCase)

   For Each filename As String In Directory.GetFiles(dir)
      h.Add(filename, File.GetCreationTime(filename))
   Next                        
End Sub

Public Sub PrintCreationTime(targetFile As String)
   Dim dt As Object = h(targetFile)
   If dt IsNot Nothing Then
      Console.WriteLine("File {0} was created at {1}.", _
         targetFile, _
         CDate(dt))
   Else
      Console.WriteLine("File {0} does not exist.", targetFile)
   End If
End Sub  
```

## <a name="displaying-and-persisting-formatted-data"></a><span data-ttu-id="14a37-330">Anzeigen und Beibehalten von formatierten Daten</span><span class="sxs-lookup"><span data-stu-id="14a37-330">Displaying and persisting formatted data</span></span>

<span data-ttu-id="14a37-331">Wenn Sie Benutzern Daten anzeigen, die keine Zeichenfolge sind, z. B. Zahlen sowie Datumsangaben und Zeitangaben, formatieren Sie diese den Kultureinstellungen des Benutzers entsprechend.</span><span class="sxs-lookup"><span data-stu-id="14a37-331">When you display non-string data such as numbers and dates and times to users, format them by using the user's cultural settings.</span></span> <span data-ttu-id="14a37-332">Standardmäßig verwenden die [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode und die `ToString`-Methoden der numerischen Typen und der Datums- und Uhrzeittypen die aktuelle Threadkultur für Formatierungsvorgänge.</span><span class="sxs-lookup"><span data-stu-id="14a37-332">By default, the [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) method and the `ToString` methods of the numeric types and the date and time types use the current thread culture for formatting operations.</span></span> <span data-ttu-id="14a37-333">Um explizit anzugeben, dass die Formatierungsmethode die aktuelle Kultur verwenden soll, können Sie eine Überladung einer Formatierungsmethode mit einem Provider-Parameter aufrufen, wie z.B. [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) oder [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), und ihr die [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture)-Eigenschaft übergeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-333">To explicitly specify that the formatting method should use the current culture, you can call an overload of a formatting method that has a provider parameter, such as [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) or [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), and pass it the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property.</span></span> 

<span data-ttu-id="14a37-334">Sie können Daten, die keine Zeichenfolge sind, entweder als Binärdaten oder als formatierte Daten beibehalten.</span><span class="sxs-lookup"><span data-stu-id="14a37-334">You can persist non-string data either as binary data or as formatted data.</span></span> <span data-ttu-id="14a37-335">Wenn Sie möchten, dass sie als formatierte Daten gespeichert werden, sollten Sie eine Überladung einer Formatierungsmethode aufrufen, die einen *Provider*-Parameter einschließt, und ihr die [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)-Eigenschaft übergeben.</span><span class="sxs-lookup"><span data-stu-id="14a37-335">If you choose to save it as formatted data, you should call a formatting method overload that includes a *provider* parameter and pass it the [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="14a37-336">Die invariante Kultur stellt ein konsistentes Format für formatierte Daten bereit, das unabhängig von der Kultur und dem Computers ist.</span><span class="sxs-lookup"><span data-stu-id="14a37-336">The invariant culture provides a consistent format for formatted data that is independent of culture and machine.</span></span> <span data-ttu-id="14a37-337">Im Gegensatz dazu bringt das Beibehalten von Daten, die mit anderen Kulturen als der invarianten Kultur formatiert werden, einige Einschränkungen mit sich:</span><span class="sxs-lookup"><span data-stu-id="14a37-337">In contrast, persisting data that is formatted by using cultures other than the invariant culture has a number of limitations:</span></span> 

* <span data-ttu-id="14a37-338">Die Daten sind wahrscheinlich unbrauchbar, wenn sie auf einem System mit einer andere Kultur abgerufen werden oder wenn der Benutzer des aktuellen Systems die aktuelle Kultur ändert und versucht, die Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="14a37-338">The data is likely to be unusable if it is retrieved on a system that has a different culture, or if the user of the current system changes the current culture and tries to retrieve the data.</span></span> 

* <span data-ttu-id="14a37-339">Die Eigenschaften einer Kultur auf einem bestimmten Computer können von den Standardwerten abweichen.</span><span class="sxs-lookup"><span data-stu-id="14a37-339">The properties of a culture on a specific computer can differ from standard values.</span></span> <span data-ttu-id="14a37-340">Ein Benutzer kann kulturabhängige Anzeigeeinstellungen jederzeit anpassen.</span><span class="sxs-lookup"><span data-stu-id="14a37-340">At any time, a user can customize culture-sensitive display settings.</span></span> <span data-ttu-id="14a37-341">Aufgrund dessen können formatierte Daten, die in einem System gespeichert sind, möglicherweise nicht mehr gelesen werden, wenn der Benutzer die Kultureinstellungen anpasst.</span><span class="sxs-lookup"><span data-stu-id="14a37-341">Because of this, formatted data that is saved on a system may not be readable after the user customizes cultural settings.</span></span> <span data-ttu-id="14a37-342">Die computerübergreifende Portabilität von formatierten Daten wird wahrscheinlich sogar noch eingeschränkter.</span><span class="sxs-lookup"><span data-stu-id="14a37-342">The portability of formatted data across computers is likely to be even more limited.</span></span> 

* <span data-ttu-id="14a37-343">Internationale, regionale oder nationale Standards, die die Formatierung von Zahlen oder Datumsangaben und Uhrzeiten regeln, ändern sich mit der Zeit, und diese Änderungen werden in Betriebssystemupdates integriert.</span><span class="sxs-lookup"><span data-stu-id="14a37-343">International, regional, or national standards that govern the formatting of numbers or dates and times change over time, and these changes are incorporated into operating system updates.</span></span> <span data-ttu-id="14a37-344">Wenn sich die Formatierungskonventionen ändern, können Daten, die anhand früherer Konventionen formatiert wurden, möglicherweise nicht mehr gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="14a37-344">When formatting conventions change, data that was formatted by using the previous conventions may become unreadable.</span></span> 

<span data-ttu-id="14a37-345">Das folgende Beispiel veranschaulicht die eingeschränkte Portabilität, die sich aus der Verwendung von kulturabhängiger Formatierung zum Beibehalten von Daten ergibt.</span><span class="sxs-lookup"><span data-stu-id="14a37-345">The following example illustrates the limited portability that results from using culture-sensitive formatting to persist data.</span></span> <span data-ttu-id="14a37-346">In dem Beispiel wird ein Array von Daten- und Uhrzeitwerten in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="14a37-346">The example saves an array of date and time values to a file.</span></span> <span data-ttu-id="14a37-347">Diese werden anhand der Konventionen der Kultur Englisch (USA) formatiert.</span><span class="sxs-lookup"><span data-stu-id="14a37-347">These are formatted by using the conventions of the English (United States) culture.</span></span> <span data-ttu-id="14a37-348">Nachdem die aktuelle Threadkultur der Anwendung in Französisch (Schweiz) geändert wird, versucht die Anwendung, die gespeicherten Werte mithilfe der Formatierungskonventionen der aktuellen Kultur zu lesen.</span><span class="sxs-lookup"><span data-stu-id="14a37-348">After the application changes the current thread culture to French (Switzerland), it tries to read the saved values by using the formatting conventions of the current culture.</span></span> <span data-ttu-id="14a37-349">Der Versuch, zwei der Datenelemente zu lesen, löst eine [FormatException](xref:System.FormatException)-Ausnahme aus, und das Array von Datumsangaben enthält nun zwei falsche Elemente, die [MinValue](xref:System.DateTime.MinValue) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="14a37-349">The attempt to read two of the data items throws a [FormatException](xref:System.FormatException) exception, and the array of dates now contains two incorrect elements that are equal to [MinValue](xref:System.DateTime.MinValue).</span></span> 

```csharp
using System;
using System.Globalization;
using System.IO;
using System.Text;
using System.Threading;

public class Example
{
   private static string filename = @".\dates.dat";

   public static void Main()
   {
      DateTime[] dates = { new DateTime(1758, 5, 6, 21, 26, 0), 
                           new DateTime(1818, 5, 5, 7, 19, 0), 
                           new DateTime(1870, 4, 22, 23, 54, 0),  
                           new DateTime(1890, 9, 8, 6, 47, 0), 
                           new DateTime(1905, 2, 18, 15, 12, 0) }; 
      // Write the data to a file using the current culture.
      WriteData(dates);
      // Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH");
      // Read the data using the current culture.
      DateTime[] newDates = ReadData();
      foreach (var newDate in newDates)
         Console.WriteLine(newDate.ToString("g"));
   }

   private static void WriteData(DateTime[] dates) 
   {
      StreamWriter sw = new StreamWriter(filename, false, Encoding.UTF8);    
      for (int ctr = 0; ctr < dates.Length; ctr++) {
         sw.Write("{0}", dates[ctr].ToString("g", CultureInfo.CurrentCulture));
         if (ctr < dates.Length - 1) sw.Write("|");   
      }      
      sw.Close();
   }

   private static DateTime[] ReadData() 
   {
      bool exceptionOccurred = false;

      // Read file contents as a single string, then split it.
      StreamReader sr = new StreamReader(filename, Encoding.UTF8);
      string output = sr.ReadToEnd();
      sr.Close();   

      string[] values = output.Split( new char[] { '|' } );
      DateTime[] newDates = new DateTime[values.Length]; 
      for (int ctr = 0; ctr < values.Length; ctr++) {
         try {
            newDates[ctr] = DateTime.Parse(values[ctr], CultureInfo.CurrentCulture);
         }
         catch (FormatException) {
            Console.WriteLine("Failed to parse {0}", values[ctr]);
            exceptionOccurred = true;
         }
      }      
      if (exceptionOccurred) Console.WriteLine();
      return newDates;
   }
}
// The example displays the following output:
//       Failed to parse 4/22/1870 11:54 PM
//       Failed to parse 2/18/1905 3:12 PM
//       
//       05.06.1758 21:26
//       05.05.1818 07:19
//       01.01.0001 00:00
//       09.08.1890 06:47
//       01.01.0001 00:00
//       01.01.0001 00:00
```

```vb
Imports System.Globalization
Imports System.IO
Imports System.Text
Imports System.Threading

Module Example
   Private filename As String = ".\dates.dat"

   Public Sub Main()
      Dim dates() As Date = { #5/6/1758 9:26PM#, #5/5/1818 7:19AM#, _ 
                              #4/22/1870 11:54PM#, #9/8/1890 6:47AM#, _ 
                              #2/18/1905 3:12PM# }
      ' Write the data to a file using the current culture.
      WriteData(dates)
      ' Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH")
      ' Read the data using the current culture.
      Dim newDates() As Date = ReadData()
      For Each newDate In newDates
         Console.WriteLine(newDate.ToString("g"))
      Next
   End Sub

   Private Sub WriteData(dates() As Date)
      Dim sw As New StreamWriter(filename, False, Encoding.Utf8)    
      For ctr As Integer = 0 To dates.Length - 1
         sw.Write("{0}", dates(ctr).ToString("g", CultureInfo.CurrentCulture))
         If ctr < dates.Length - 1 Then sw.Write("|")   
      Next      
      sw.Close()
   End Sub

   Private Function ReadData() As Date()
      Dim exceptionOccurred As Boolean = False

      ' Read file contents as a single string, then split it.
      Dim sr As New StreamReader(filename, Encoding.Utf8)
      Dim output As String = sr.ReadToEnd()
      sr.Close()   

      Dim values() As String = output.Split( {"|"c } )
      Dim newDates(values.Length - 1) As Date 
      For ctr As Integer = 0 To values.Length - 1
         Try
            newDates(ctr) = DateTime.Parse(values(ctr), CultureInfo.CurrentCulture)
         Catch e As FormatException
            Console.WriteLine("Failed to parse {0}", values(ctr))
            exceptionOccurred = True
         End Try
      Next      
      If exceptionOccurred Then Console.WriteLine()
      Return newDates
   End Function
End Module
' The example displays the following output:
'       Failed to parse 4/22/1870 11:54 PM
'       Failed to parse 2/18/1905 3:12 PM
'       
'       05.06.1758 21:26
'       05.05.1818 07:19
'       01.01.0001 00:00
'       09.08.1890 06:47
'       01.01.0001 00:00
'       01.01.0001 00:00
'
```

<span data-ttu-id="14a37-350">Wenn Sie jedoch die [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture)-Eigenschaft in den Aufrufen von [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) und [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)) durch [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) ersetzen, werden die beibehaltenen Datums- und Uhrzeitdaten erfolgreich wiederhergestellt, wie die folgende Ausgabe zeigt.</span><span class="sxs-lookup"><span data-stu-id="14a37-350">However, if you replace the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property with [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) in the calls to [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), the persisted date and time data is successfully restored, as the following output shows.</span></span>

```
// 06.05.1758 21:26
// 05.05.1818 07:19
// 22.04.1870 23:54
// 08.09.1890 06:47
// 18.02.1905 15:12
```

## <a name="see-also"></a><span data-ttu-id="14a37-351">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14a37-351">See also</span></span>

[<span data-ttu-id="14a37-352">Bearbeiten von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="14a37-352">Manipulating strings</span></span>](manipulating-strings.md)


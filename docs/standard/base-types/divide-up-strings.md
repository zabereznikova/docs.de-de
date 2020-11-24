---
title: Aufteilen von Zeichenfolgen in Teilzeichenfolgen
description: Lernen Sie verschiedene Techniken zum Extrahieren von Teilzeichenfolgen kennen, darunter String.Split, reguläre Ausdrücke und String.Substring.
ms.date: 10/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: b753476b7d8e5808fdcacc6f28bd1de5f8b232bb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829648"
---
# <a name="extract-substrings-from-a-string"></a><span data-ttu-id="d0bfe-103">Extrahieren von Teilzeichenfolgen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0bfe-103">Extract substrings from a string</span></span>

<span data-ttu-id="d0bfe-104">In diesem Artikel werden verschiedene Techniken zum Extrahieren von Teilen einer Zeichenfolge behandelt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-104">This article covers some different techniques for extracting parts of a string.</span></span>

- <span data-ttu-id="d0bfe-105">Verwenden Sie die [Split-Methode](#stringsplit-method), wenn die gewünschten Teilzeichenfolgen durch ein bekanntes Trennzeichen (oder mehrere) getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-105">Use the [Split method](#stringsplit-method) when the substrings you want are separated by a known delimiting character (or characters).</span></span>
- <span data-ttu-id="d0bfe-106">[Reguläre Ausdrücke](#regular-expressions) sind nützlich, wenn die Zeichenfolge einem festen Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-106">[Regular expressions](#regular-expressions) are useful when the string conforms to a fixed pattern.</span></span>
- <span data-ttu-id="d0bfe-107">Verwenden Sie die Methoden [IndexOf und Substring](#stringindexof-and-stringsubstring-methods) in Verbindung miteinander, wenn Sie nicht *alle* Teilzeichenfolgen in einer Zeichenfolge extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-107">Use the [IndexOf and Substring methods](#stringindexof-and-stringsubstring-methods) in conjunction when you don't want to extract *all* of the substrings in a string.</span></span>

## <a name="stringsplit-method"></a><span data-ttu-id="d0bfe-108">String.Split-Methode</span><span class="sxs-lookup"><span data-stu-id="d0bfe-108">String.Split method</span></span>

<span data-ttu-id="d0bfe-109"><xref:System.String.Split%2A?displayProperty=nameWithType> bietet mehrere Überladungen, die Ihnen helfen, eine Zeichenfolge in eine Gruppe von Teilzeichenfolgen zu zerlegen, die auf einem oder mehreren von Ihnen angegebenen Trennzeichen basieren.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-109"><xref:System.String.Split%2A?displayProperty=nameWithType> provides a handful of overloads to help you break up a string into a group of substrings based on one or more delimiting characters that you specify.</span></span> <span data-ttu-id="d0bfe-110">Sie können die Gesamtanzahl der Teilzeichenfolgen im Endergebnis begrenzen, Leerzeichen aus Teilzeichenfolgen entfernen oder leere Teilzeichenfolgen ausschließen.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-110">You can choose to limit the total number of substrings in the final result, trim white-space characters from substrings, or exclude empty substrings.</span></span>

<span data-ttu-id="d0bfe-111">Die folgenden Beispiele zeigen drei verschiedene Überladungen von `String.Split()`.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-111">The following examples show three different overloads of `String.Split()`.</span></span> <span data-ttu-id="d0bfe-112">Im ersten Beispiel wird die Überladung <xref:System.String.Split(System.Char[])> ohne Übergabe von Trennzeichen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-112">The first example calls the <xref:System.String.Split(System.Char[])> overload without passing any separator characters.</span></span> <span data-ttu-id="d0bfe-113">Wenn Sie keine Trennzeichen angeben, verwendet `String.Split()` Standardtrennzeichen, bei denen es sich um Leerzeichen handelt, um die Zeichenfolge aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-113">When you don't specify any delimiting characters, `String.Split()` uses default delimiters, which are white-space characters, to split up the string.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

<span data-ttu-id="d0bfe-114">Wie Sie sehen können, sind die Punktzeichen (`.`) in zwei der Teilzeichenfolgen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-114">As you can see, the period characters (`.`) are included in two of the substrings.</span></span> <span data-ttu-id="d0bfe-115">Wenn Sie die Punktzeichen ausschließen möchten, können Sie das Punktzeichen als zusätzliches Trennzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-115">If you want to exclude the period characters, you can add the period character as an additional delimiting character.</span></span> <span data-ttu-id="d0bfe-116">Im nächsten Beispiel wird gezeigt, wie dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-116">The next example shows how to do this.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

<span data-ttu-id="d0bfe-117">Die Punkte sind aus den Teilzeichenfolgen verschwunden, aber jetzt wurden zwei zusätzliche leere Teilzeichenfolgen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-117">The periods are gone from the substrings, but now two extra empty substrings have been included.</span></span> <span data-ttu-id="d0bfe-118">Diese leere Teilzeichenfolge stellt die Teilzeichenfolge zwischen dem Wort und dem darauf folgenden Punkt dar.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-118">These empty substring represent the substring between the word and the period that follows it.</span></span> <span data-ttu-id="d0bfe-119">Um leere Teilzeichenfolgen aus dem resultierenden Array auszuschließen, können Sie die Überladung <xref:System.String.Split(System.Char[],System.StringSplitOptions)> aufrufen und <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> für den Parameter `options` angeben.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-119">To omit empty substrings from the resulting array, you can call the <xref:System.String.Split(System.Char[],System.StringSplitOptions)> overload and specify <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> for the `options` parameter.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a><span data-ttu-id="d0bfe-120">Reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="d0bfe-120">Regular expressions</span></span>

<span data-ttu-id="d0bfe-121">Wenn Ihre Zeichenfolge mit einem festen Muster übereinstimmt, können Sie mit einem regulären Ausdruck dessen Elemente extrahieren und verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-121">If your string conforms to a fixed pattern, you can use a regular expression to extract and handle its elements.</span></span> <span data-ttu-id="d0bfe-122">Wenn Zeichenfolgen zum Beispiel die Form „*Zahl* *Operand* *Zahl*“ haben, können Sie einen [regulären Ausdruck](regular-expressions.md) verwenden, um die Zeichenfolge zu extrahieren und die Elemente der Zeichenfolge zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-122">For example, if strings take the form "*number* *operand* *number*", you can use a [regular expression](regular-expressions.md) to extract and handle the string's elements.</span></span> <span data-ttu-id="d0bfe-123">Hier sehen Sie ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d0bfe-123">Here's an example:</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

<span data-ttu-id="d0bfe-124">Das Muster für reguläre Ausdrücke, `(\d+)\s+([-+*/])\s+(\d+)`, ist so definiert:</span><span class="sxs-lookup"><span data-stu-id="d0bfe-124">The regular expression pattern `(\d+)\s+([-+*/])\s+(\d+)` is defined like this:</span></span>

|<span data-ttu-id="d0bfe-125">Muster</span><span class="sxs-lookup"><span data-stu-id="d0bfe-125">Pattern</span></span>|<span data-ttu-id="d0bfe-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0bfe-126">Description</span></span>|
|-------------|-----------------|
|`(\d+)`|<span data-ttu-id="d0bfe-127">Übereinstimmung mit mindestens einer Dezimalstelle finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-127">Match one or more decimal digits.</span></span> <span data-ttu-id="d0bfe-128">Dies ist die erste Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-128">This is the first capturing group.</span></span>|
|`\s+`|<span data-ttu-id="d0bfe-129">Übereinstimmung mit mindestens einem Leerzeichen finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-129">Match one or more white-space characters.</span></span>|
|`([-+*/])`|<span data-ttu-id="d0bfe-130">Übereinstimmung mit dem Zeichen eines arithmetischen Operators (+, -, \* oder /) finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-130">Match an arithmetic operator sign (+, -, \*, or /).</span></span> <span data-ttu-id="d0bfe-131">Dies ist die zweite Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-131">This is the second capturing group.</span></span>|
|`\s+`|<span data-ttu-id="d0bfe-132">Übereinstimmung mit mindestens einem Leerzeichen finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-132">Match one or more white-space characters.</span></span>|
|`(\d+)`|<span data-ttu-id="d0bfe-133">Übereinstimmung mit mindestens einer Dezimalstelle finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-133">Match one or more decimal digits.</span></span> <span data-ttu-id="d0bfe-134">Dies ist die dritte Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-134">This is the third capturing group.</span></span>|

<span data-ttu-id="d0bfe-135">Sie können auch einen regulären Ausdruck verwenden, um Teilzeichenfolgen aus einer Zeichenfolge zu extrahieren, die auf einem Muster statt auf einem festen Satz von Zeichen basieren.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-135">You can also use a regular expression to extract substrings from a string based on a pattern rather than a fixed set of characters.</span></span> <span data-ttu-id="d0bfe-136">Dies ist ein gängiges Szenario, wenn eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d0bfe-136">This is a common scenario when either of these conditions occurs:</span></span>

- <span data-ttu-id="d0bfe-137">Mindestens eines der Trennzeichen dient in der <xref:System.String>-Instanz nicht *immer* als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-137">One or more of the delimiter characters does not *always* serve as a delimiter in the <xref:System.String> instance.</span></span>

- <span data-ttu-id="d0bfe-138">Sequenz und Anzahl der Trennzeichen sind variabel oder unbekannt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-138">The sequence and number of delimiter characters is variable or unknown.</span></span>

<span data-ttu-id="d0bfe-139">Beispielsweise kann die <xref:System.String.Split%2A>-Methode nicht verwendet werden, um die folgende Zeichenfolge aufzuteilen, da die Anzahl von `\n`-Zeichen (Zeilenvorschub) variabel ist und sie nicht immer als Trennzeichen dienen.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-139">For example, the <xref:System.String.Split%2A> method cannot be used to split the following string, because the number of `\n` (newline) characters is variable, and they don't always serve as delimiters.</span></span>

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

<span data-ttu-id="d0bfe-140">Ein regulärer Ausdruck kann diese Zeichenfolge problemlos aufteilen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-140">A regular expression can split this string easily, as the following example shows.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

<span data-ttu-id="d0bfe-141">Das Muster für reguläre Ausdrücke, `\[([^\[\]]+)\]`, ist so definiert:</span><span class="sxs-lookup"><span data-stu-id="d0bfe-141">The regular expression pattern `\[([^\[\]]+)\]` is defined like this:</span></span>

|<span data-ttu-id="d0bfe-142">Muster</span><span class="sxs-lookup"><span data-stu-id="d0bfe-142">Pattern</span></span>|<span data-ttu-id="d0bfe-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0bfe-143">Description</span></span>|
|-------------|-----------------|
|`\[`|<span data-ttu-id="d0bfe-144">Übereinstimmung mit einer öffnenden geschweiften Klammer finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-144">Match an opening bracket.</span></span>|
|`([^\[\]]+)`|<span data-ttu-id="d0bfe-145">Einmal oder mehrmals eine Übereinstimmung mit einem beliebigen Zeichen finden, das keine öffnende oder schließende eckige Klammer ist.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-145">Match any character that is not an opening or a closing bracket one or more times.</span></span> <span data-ttu-id="d0bfe-146">Dies ist die erste Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-146">This is the first capturing group.</span></span>|
|`\]`|<span data-ttu-id="d0bfe-147">Übereinstimmung mit einer schließenden geschweiften Klammer finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-147">Match a closing bracket.</span></span>|

<span data-ttu-id="d0bfe-148">Die Methode <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> ist fast identisch mit <xref:System.String.Split%2A?displayProperty=nameWithType>, außer dass sie eine Zeichenfolge auf Grundlage eines Musters regulärer Ausdrücke anstelle eines festen Satzes von Zeichen aufteilt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-148">The <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method is almost identical to <xref:System.String.Split%2A?displayProperty=nameWithType>, except that it splits a string based on a regular expression pattern instead of a fixed character set.</span></span> <span data-ttu-id="d0bfe-149">Im folgenden Beispiel wird beispielsweise die <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>-Methode verwendet, um eine Zeichenfolge mit Teilzeichenfolgen zu teilen, die durch verschiedene Kombinationen von Bindestrichen und anderen Zeichen voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-149">For example, the following example uses the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to split a string that contains substrings delimited by various combinations of hyphens and other characters.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

<span data-ttu-id="d0bfe-150">Das Muster für reguläre Ausdrücke, `\s-\s?[+*]?\s?-\s`, ist so definiert:</span><span class="sxs-lookup"><span data-stu-id="d0bfe-150">The regular expression pattern `\s-\s?[+*]?\s?-\s` is defined like this:</span></span>

|<span data-ttu-id="d0bfe-151">Muster</span><span class="sxs-lookup"><span data-stu-id="d0bfe-151">Pattern</span></span>|<span data-ttu-id="d0bfe-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0bfe-152">Description</span></span>|
|-------------|-----------------|
|`\s-`|<span data-ttu-id="d0bfe-153">Übereinstimmung mit einem Leerzeichen gefolgt von einem Bindestrich finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-153">Match a white-space character followed by a hyphen.</span></span>|
|`\s?`|<span data-ttu-id="d0bfe-154">Übereinstimmung mit keinem oder einem Leerzeichen finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-154">Match zero or one white-space character.</span></span>|
|`[+*]?`|<span data-ttu-id="d0bfe-155">Übereinstimmung mit null oder einem Vorkommen von entweder dem Zeichen + oder \* finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-155">Match zero or one occurrence of either the + or \* character.</span></span>|
|`\s?`|<span data-ttu-id="d0bfe-156">Übereinstimmung mit keinem oder einem Leerzeichen finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-156">Match zero or one white-space character.</span></span>|
|`-\s`|<span data-ttu-id="d0bfe-157">Übereinstimmung mit einem Bindestrich gefolgt von einem Leerzeichen finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-157">Match a hyphen followed by a white-space character.</span></span>|

## <a name="stringindexof-and-stringsubstring-methods"></a><span data-ttu-id="d0bfe-158">Die Methoden String.IndexOf und String.Substring</span><span class="sxs-lookup"><span data-stu-id="d0bfe-158">String.IndexOf and String.Substring methods</span></span>

<span data-ttu-id="d0bfe-159">Wenn Sie nicht an allen Teilzeichenfolgen in einer Zeichenfolge interessiert sind, können Sie auch mit einer der Methoden zum Vergleichen von Zeichenfolgen arbeiten, die den Index zurückgibt, bei dem die Übereinstimmung beginnt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-159">If you aren't interested in all of the substrings in a string, you might prefer to work with one of the string comparison methods that returns the index at which the match begins.</span></span> <span data-ttu-id="d0bfe-160">Sie können dann die <xref:System.String.Substring%2A>-Methode aufrufen, um die gewünschte Teilzeichenfolge zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-160">You can then call the <xref:System.String.Substring%2A> method to extract the substring that you want.</span></span> <span data-ttu-id="d0bfe-161">Es gibt die folgenden Methoden zum Vergleichen von Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="d0bfe-161">The string comparison methods include:</span></span>

- <span data-ttu-id="d0bfe-162"><xref:System.String.IndexOf%2A>, die den auf null basierenden Index des ersten Vorkommens eines Zeichens oder einer Zeichenfolge in einer Zeichenfolgeninstanz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-162"><xref:System.String.IndexOf%2A>, which returns the zero-based index of the first occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="d0bfe-163"><xref:System.String.IndexOfAny%2A>, die den auf null basierenden Index in der aktuellen Zeichenfolgeninstanz beim ersten Vorkommen eines beliebigen Zeichens in einem Zeichenarray zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-163"><xref:System.String.IndexOfAny%2A>, which returns the zero-based index in the current string instance of the first occurrence of any character in a character array.</span></span>

- <span data-ttu-id="d0bfe-164"><xref:System.String.LastIndexOf%2A>, die den auf null basierenden Index des letzten Vorkommens eines Zeichens oder einer Zeichenfolge in einer Zeichenfolgeninstanz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-164"><xref:System.String.LastIndexOf%2A>, which returns the zero-based index of the last occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="d0bfe-165"><xref:System.String.LastIndexOfAny%2A>, die einen auf null basierenden Index in der aktuellen Zeichenfolgeninstanz des letzten Vorkommens eines beliebigen Zeichens in einem Zeichenarray zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-165"><xref:System.String.LastIndexOfAny%2A>, which returns a zero-based index in the current string instance of the last occurrence of any character in a character array.</span></span>

<span data-ttu-id="d0bfe-166">Im folgenden Beispiel wird die <xref:System.String.IndexOf%2A>-Methode verwendet, um die Punkte in einer Zeichenfolge zu finden.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-166">The following example uses the <xref:System.String.IndexOf%2A> method to find the periods in a string.</span></span> <span data-ttu-id="d0bfe-167">Anschließend wird die <xref:System.String.Substring%2A>-Methode verwendet, um vollständige Sätze zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d0bfe-167">It then uses the <xref:System.String.Substring%2A> method to return full sentences.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a><span data-ttu-id="d0bfe-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0bfe-168">See also</span></span>

- [<span data-ttu-id="d0bfe-169">Grundlegende Zeichenfolgenvorgänge in .NET</span><span class="sxs-lookup"><span data-stu-id="d0bfe-169">Basic string operations in .NET</span></span>](basic-string-operations.md)
- [<span data-ttu-id="d0bfe-170">Reguläre Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="d0bfe-170">.NET regular expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="d0bfe-171">Analysieren von Zeichenfolgen mithilfe von String.Split in C#</span><span class="sxs-lookup"><span data-stu-id="d0bfe-171">How to parse strings using String.Split in C#</span></span>](../../csharp/how-to/parse-strings-using-split.md)

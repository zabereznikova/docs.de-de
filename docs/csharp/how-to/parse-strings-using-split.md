---
title: 'Vorgehensweise: Analysieren von Zeichenfolgen mithilfe von „String.Split“ (C#-Anleitung)'
description: „String.Split“ gibt einen Array mit Zeichenfolgen an, die von mehreren Trennzeichen getrennt werden. So können Sie auf einfache Weise Zeichenfolgen analysieren.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: b46429f3b55658e1f2a7d21eed714c1d02236c57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "73973235"
---
# <a name="how-to-parse-strings-using-stringsplit-c-guide"></a><span data-ttu-id="df241-104">Vorgehensweise: Analysieren von Zeichenfolgen mithilfe von „String.Split“ (C#-Anleitung)</span><span class="sxs-lookup"><span data-stu-id="df241-104">How to parse strings using String.Split (C# Guide)</span></span>

<span data-ttu-id="df241-105">Die <xref:System.String.Split%2A?displayProperty=nameWithType>-Methode erstellt ein Array mit Teilzeichenfolgen, indem die Eingabezeichenfolge von mindestens einem Trennzeichen geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="df241-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="df241-106">Dies stellt in der Regel die einfachste Methode dar, eine Zeichenfolge an Wortgrenzen zu teilen.</span><span class="sxs-lookup"><span data-stu-id="df241-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="df241-107">Sie wird außerdem verwendet, um Zeichenfolgen nach anderen bestimmten Zeichen und Zeichenfolgen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="df241-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="df241-108">Mithilfe des folgenden Codes wird ein häufig verwendeter Ausdruck in ein Array mit Zeichenfolgen für jedes Wort unterteilt.</span><span class="sxs-lookup"><span data-stu-id="df241-108">The following code splits a common phrase into an array of strings for each word.</span></span>

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

<span data-ttu-id="df241-109">Jede Instanz eines Trennzeichens gibt einen Wert in dem zurückgegebenen Array zurück.</span><span class="sxs-lookup"><span data-stu-id="df241-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="df241-110">Aufeinander folgende Trennzeichen geben eine leere Zeichenfolge als Wert in einem zurückgegebenen Array zurück.</span><span class="sxs-lookup"><span data-stu-id="df241-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span>  <span data-ttu-id="df241-111">Dies wird im folgenden Beispiel dargestellt, in dem Leerräume als Trennlinien verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="df241-111">You can see this in the following example, which uses space as a separator:</span></span>

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

<span data-ttu-id="df241-112">Dieses Verhalten vereinfacht den Vorgang für Dateien mit Formaten wie CSV (Comma Separated Values = durch Trennzeichen getrennte Werte), die Tabellendaten darstellen.</span><span class="sxs-lookup"><span data-stu-id="df241-112">This behavior makes it easier for formats like comma separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="df241-113">Aufeinander folgende Kommas stellen eine leere Spalte dar.</span><span class="sxs-lookup"><span data-stu-id="df241-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="df241-114">Sie können einen optionalen <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>-Parameter übergeben, um jegliche leeren Zeichenfolgen aus dem zurückgegebenen Array auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="df241-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="df241-115">Für kompliziertere Prozesse der zurückgegebenen Auflistung können Sie [LINQ](../programming-guide/concepts/linq/index.md) verwenden, um die Ergebnissequenz zu manipulieren.</span><span class="sxs-lookup"><span data-stu-id="df241-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="df241-116"><xref:System.String.Split%2A?displayProperty=nameWithType> kann mehrere Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="df241-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="df241-117">In diesem Beispiel werden Leerräume, Kommas, Punkte, Doppelpunkte und Tabstopps verwendet, die alle in einem Array, das diese Trennzeichen enthält, an <xref:System.String.Split%2A>übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="df241-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>
<span data-ttu-id="df241-118">Die Schleife am Ende des Codes zeigt sämtliche Wörter im zurückgegeben Array an.</span><span class="sxs-lookup"><span data-stu-id="df241-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

<span data-ttu-id="df241-119">Aufeinander folgende Instanzen einer beliebigen Trennlinie geben die leere Zeichenfolge im Ausgabearray zurück:</span><span class="sxs-lookup"><span data-stu-id="df241-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<span data-ttu-id="df241-120"><xref:System.String.Split%2A?displayProperty=nameWithType> kann ein Array mit Zeichenfolgen aufnehmen (Zeichenfolgen, die als Trennzeichen für die Analyse der Zielzeichenfolge fungieren, statt einzelne Zeichen).</span><span class="sxs-lookup"><span data-stu-id="df241-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

<span data-ttu-id="df241-121">Sie können diese Beispiele ausprobieren, indem Sie sich den Code in unserem [GitHub-Repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings) ansehen.</span><span class="sxs-lookup"><span data-stu-id="df241-121">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="df241-122">Alternativ dazu können Sie die Beispiele [als ZIP-Datei](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="df241-122">Or you can download the samples [as a zip file](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="df241-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df241-123">See also</span></span>

- [<span data-ttu-id="df241-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="df241-124">C# Programming Guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="df241-125">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="df241-125">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="df241-126">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="df241-126">.NET Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)

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
ms.openlocfilehash: 4f0056426fb29ec3d76093e57fa45e2046f27a4f
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662991"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a><span data-ttu-id="fa640-104">Analysieren von Zeichenfolgen mithilfe von String.Split in C\#</span><span class="sxs-lookup"><span data-stu-id="fa640-104">How to parse strings using String.Split in C\#</span></span>

<span data-ttu-id="fa640-105">Die <xref:System.String.Split%2A?displayProperty=nameWithType>-Methode erstellt ein Array mit Teilzeichenfolgen, indem die Eingabezeichenfolge von mindestens einem Trennzeichen geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="fa640-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="fa640-106">Dies stellt in der Regel die einfachste Methode dar, eine Zeichenfolge an Wortgrenzen zu teilen.</span><span class="sxs-lookup"><span data-stu-id="fa640-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="fa640-107">Sie wird außerdem verwendet, um Zeichenfolgen nach anderen bestimmten Zeichen und Zeichenfolgen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="fa640-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="fa640-108">Mithilfe des folgenden Codes wird ein häufig verwendeter Ausdruck in ein Array mit Zeichenfolgen für jedes Wort unterteilt.</span><span class="sxs-lookup"><span data-stu-id="fa640-108">The following code splits a common phrase into an array of strings for each word.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

<span data-ttu-id="fa640-109">Jede Instanz eines Trennzeichens gibt einen Wert in dem zurückgegebenen Array zurück.</span><span class="sxs-lookup"><span data-stu-id="fa640-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="fa640-110">Aufeinander folgende Trennzeichen geben eine leere Zeichenfolge als Wert in einem zurückgegebenen Array zurück.</span><span class="sxs-lookup"><span data-stu-id="fa640-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span> <span data-ttu-id="fa640-111">Im folgenden Beispiel sehen Sie, wie ein leere Zeichenfolge erstellt wird. Hier wird das Leerzeichen als Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa640-111">You can see how an empty string is created in the following example, which uses the space character as a separator.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

<span data-ttu-id="fa640-112">Dieses Verhalten vereinfacht den Vorgang für Formate wie CSV (Comma Separated Values, durch Trennzeichen getrennte Werte), die Tabellendaten darstellen.</span><span class="sxs-lookup"><span data-stu-id="fa640-112">This behavior makes it easier for formats like comma-separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="fa640-113">Aufeinander folgende Kommas stellen eine leere Spalte dar.</span><span class="sxs-lookup"><span data-stu-id="fa640-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="fa640-114">Sie können einen optionalen <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>-Parameter übergeben, um jegliche leeren Zeichenfolgen aus dem zurückgegebenen Array auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="fa640-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="fa640-115">Für kompliziertere Prozesse der zurückgegebenen Auflistung können Sie [LINQ](../programming-guide/concepts/linq/index.md) verwenden, um die Ergebnissequenz zu manipulieren.</span><span class="sxs-lookup"><span data-stu-id="fa640-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="fa640-116"><xref:System.String.Split%2A?displayProperty=nameWithType> kann mehrere Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa640-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="fa640-117">In diesem Beispiel werden Leerräume, Kommas, Punkte, Doppelpunkte und Tabstopps verwendet, die alle in einem Array, das diese Trennzeichen enthält, an <xref:System.String.Split%2A>übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="fa640-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>
<span data-ttu-id="fa640-118">Die Schleife am Ende des Codes zeigt sämtliche Wörter im zurückgegeben Array an.</span><span class="sxs-lookup"><span data-stu-id="fa640-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

<span data-ttu-id="fa640-119">Aufeinander folgende Instanzen einer beliebigen Trennlinie geben die leere Zeichenfolge im Ausgabearray zurück:</span><span class="sxs-lookup"><span data-stu-id="fa640-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<span data-ttu-id="fa640-120"><xref:System.String.Split%2A?displayProperty=nameWithType> kann ein Array mit Zeichenfolgen aufnehmen (Zeichenfolgen, die als Trennzeichen für die Analyse der Zielzeichenfolge fungieren, statt einzelne Zeichen).</span><span class="sxs-lookup"><span data-stu-id="fa640-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a><span data-ttu-id="fa640-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa640-121">See also</span></span>

- [<span data-ttu-id="fa640-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fa640-122">C# programming guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="fa640-123">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fa640-123">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="fa640-124">Reguläre Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="fa640-124">.NET regular expressions</span></span>](../../standard/base-types/regular-expressions.md)

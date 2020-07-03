---
title: Analysieren von Zeichenfolgen mithilfe von „String.Split“ (C#-Anleitung)
description: Die Split-Methode gibt ein Array mit Zeichenfolgen an, die von mehreren Trennzeichen getrennt werden. So können Sie auf einfache Weise Zeichenfolgen analysieren.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 7c5d8fa462775c6f3a9981693129997dda6c2286
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324141"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a><span data-ttu-id="9360b-104">Analysieren von Zeichenfolgen mithilfe von String.Split in C\#</span><span class="sxs-lookup"><span data-stu-id="9360b-104">How to parse strings using String.Split in C\#</span></span>

<span data-ttu-id="9360b-105">Die <xref:System.String.Split%2A?displayProperty=nameWithType>-Methode erstellt ein Array mit Teilzeichenfolgen, indem die Eingabezeichenfolge von mindestens einem Trennzeichen geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="9360b-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="9360b-106">Sie stellt in der Regel die einfachste Möglichkeit dar, eine Zeichenfolge an Wortgrenzen zu teilen.</span><span class="sxs-lookup"><span data-stu-id="9360b-106">This method is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="9360b-107">Sie wird außerdem verwendet, um Zeichenfolgen nach anderen bestimmten Zeichen und Zeichenfolgen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="9360b-107">It's also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="9360b-108">Mithilfe des folgenden Codes wird ein häufig verwendeter Ausdruck in ein Array mit Zeichenfolgen für jedes Wort unterteilt.</span><span class="sxs-lookup"><span data-stu-id="9360b-108">The following code splits a common phrase into an array of strings for each word.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

<span data-ttu-id="9360b-109">Jede Instanz eines Trennzeichens gibt einen Wert in dem zurückgegebenen Array zurück.</span><span class="sxs-lookup"><span data-stu-id="9360b-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="9360b-110">Aufeinander folgende Trennzeichen geben eine leere Zeichenfolge als Wert in einem zurückgegebenen Array zurück.</span><span class="sxs-lookup"><span data-stu-id="9360b-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span> <span data-ttu-id="9360b-111">Im folgenden Beispiel sehen Sie, wie ein leere Zeichenfolge erstellt wird. Hier wird das Leerzeichen als Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9360b-111">You can see how an empty string is created in the following example, which uses the space character as a separator.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

<span data-ttu-id="9360b-112">Dieses Verhalten vereinfacht den Vorgang für Formate wie CSV (Comma Separated Values, durch Trennzeichen getrennte Werte), die Tabellendaten darstellen.</span><span class="sxs-lookup"><span data-stu-id="9360b-112">This behavior makes it easier for formats like comma-separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="9360b-113">Aufeinander folgende Kommas stellen eine leere Spalte dar.</span><span class="sxs-lookup"><span data-stu-id="9360b-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="9360b-114">Sie können einen optionalen <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>-Parameter übergeben, um jegliche leeren Zeichenfolgen aus dem zurückgegebenen Array auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="9360b-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="9360b-115">Für kompliziertere Prozesse der zurückgegebenen Auflistung können Sie [LINQ](../programming-guide/concepts/linq/index.md) verwenden, um die Ergebnissequenz zu manipulieren.</span><span class="sxs-lookup"><span data-stu-id="9360b-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="9360b-116"><xref:System.String.Split%2A?displayProperty=nameWithType> kann mehrere Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9360b-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="9360b-117">In diesem Beispiel werden Leerräume, Kommas, Punkte, Doppelpunkte und Tabstopps verwendet, die an <xref:System.String.Split%2A> in einem Array übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9360b-117">The following example uses spaces, commas, periods, colons, and tabs as separating characters, which are passed to <xref:System.String.Split%2A> in an array .</span></span>
<span data-ttu-id="9360b-118">Die Schleife am Ende des Codes zeigt sämtliche Wörter im zurückgegeben Array an.</span><span class="sxs-lookup"><span data-stu-id="9360b-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

<span data-ttu-id="9360b-119">Aufeinander folgende Instanzen einer beliebigen Trennlinie geben die leere Zeichenfolge im Ausgabearray zurück:</span><span class="sxs-lookup"><span data-stu-id="9360b-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<span data-ttu-id="9360b-120"><xref:System.String.Split%2A?displayProperty=nameWithType> kann ein Array mit Zeichenfolgen aufnehmen (Zeichenfolgen, die als Trennzeichen für die Analyse der Zielzeichenfolge fungieren, statt einzelne Zeichen).</span><span class="sxs-lookup"><span data-stu-id="9360b-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a><span data-ttu-id="9360b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9360b-121">See also</span></span>

- [<span data-ttu-id="9360b-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9360b-122">C# programming guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="9360b-123">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9360b-123">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="9360b-124">Reguläre Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="9360b-124">.NET regular expressions</span></span>](../../standard/base-types/regular-expressions.md)

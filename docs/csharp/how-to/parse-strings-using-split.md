---
title: "Vorgehensweise: Analysieren von Zeichenfolgen mithilfe von „String.Split“ (C#-Anleitung)"
description: "„String.Split“ gibt einen Array mit Zeichenfolgen an, die von mehreren Trennzeichen getrennt werden. So können Sie auf einfache Weise Zeichenfolgen analysieren."
ms.date: 01/03/2018
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
author: BillWagner
ms.author: wiwagn
ms.custom: mvc
ms.openlocfilehash: fc1032f2cdf6706ec933323643dbf6ecff3e9f6f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-parse-strings-using-stringsplit-c-guide"></a><span data-ttu-id="ed878-104">Vorgehensweise: Analysieren von Zeichenfolgen mithilfe von „String.Split“ (C#-Anleitung)</span><span class="sxs-lookup"><span data-stu-id="ed878-104">How to: Parse Strings Using String.Split (C# Guide)</span></span>

<span data-ttu-id="ed878-105">Die <xref:System.String.Split%2A?displayProperty=nameWithType>-Methode erstellt ein Array mit Teilzeichenfolgen, indem die Eingabezeichenfolge von mindestens einem Trennzeichen geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="ed878-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="ed878-106">Dies stellt in der Regel die einfachste Methode dar, eine Zeichenfolge an Wortgrenzen zu teilen.</span><span class="sxs-lookup"><span data-stu-id="ed878-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="ed878-107">Sie wird außerdem verwendet, um Zeichenfolgen nach anderen bestimmten Zeichen und Zeichenfolgen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="ed878-107">It is also used to split strings on other specific characters or strings.</span></span>

<span data-ttu-id="ed878-108">Mithilfe des folgenden Codes wird ein häufig verwendeter Ausdruck in ein Array mit Zeichenfolgen für jedes Wort unterteilt.</span><span class="sxs-lookup"><span data-stu-id="ed878-108">The following code splits a common phrase into an array of strings for each word.</span></span>
<span data-ttu-id="ed878-109">Versuchen Sie es selbst, und klicken Sie auf die Schaltfläche *Ausführen*.</span><span class="sxs-lookup"><span data-stu-id="ed878-109">Try it yourself by pressing the *Run* button.</span></span>

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

<span data-ttu-id="ed878-110">Jede Instanz eines Trennzeichens gibt einen Wert in dem zurückgegebenen Array zurück.</span><span class="sxs-lookup"><span data-stu-id="ed878-110">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="ed878-111">Aufeinander folgende Trennzeichen geben eine leere Zeichenfolge als Wert in einem zurückgegebenen Array zurück.</span><span class="sxs-lookup"><span data-stu-id="ed878-111">Consecutive separator characters produce the empty string as a value in the returned array.</span></span>  <span data-ttu-id="ed878-112">Dies wird im folgenden Beispiel dargestellt, in dem Leerräume als Trennlinien verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ed878-112">You can see this in the following example, which uses space as a separator:</span></span>

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

<span data-ttu-id="ed878-113">Dieses Verhalten vereinfacht den Vorgang für Dateien mit Formaten wie CSV (Comma Separated Values = durch Trennzeichen getrennte Werte), die Tabellendaten darstellen.</span><span class="sxs-lookup"><span data-stu-id="ed878-113">This behavior makes it easier for formats like comma separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="ed878-114">Aufeinander folgende Kommas stellen eine leere Spalte dar.</span><span class="sxs-lookup"><span data-stu-id="ed878-114">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="ed878-115">Sie können einen optionalen <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=fullName>-Parameter übergeben, um jegliche leeren Zeichenfolgen aus dem zurückgegebenen Array auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="ed878-115">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=fullName> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="ed878-116">Für kompliziertere Prozesse der zurückgegebenen Auflistung können Sie [LINQ](../programming-guide/concepts/linq/index.md) verwenden, um die Ergebnissequenz zu manipulieren.</span><span class="sxs-lookup"><span data-stu-id="ed878-116">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>    

<span data-ttu-id="ed878-117"><xref:System.String.Split%2A?displayProperty=nameWithType> kann mehrere Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed878-117"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span> <span data-ttu-id="ed878-118">In diesem Beispiel werden Leerräume, Kommas, Punkte, Doppelpunkte und Tabstopps verwendet, die alle in einem Array, das diese Trennzeichen enthält, an <xref:System.String.Split%2A>übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed878-118">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="ed878-119">Die Schleife am Ende des Codes zeigt sämtliche Wörter im zurückgegeben Array an.</span><span class="sxs-lookup"><span data-stu-id="ed878-119">The loop at the bottom of the code displays each of the words in the returned array.</span></span>  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

<span data-ttu-id="ed878-120">Aufeinander folgende Instanzen einer beliebigen Trennlinie geben die leere Zeichenfolge im Ausgabearray zurück:</span><span class="sxs-lookup"><span data-stu-id="ed878-120">Consecutive instances of any separator produce the empty string in the output array:</span></span>

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<span data-ttu-id="ed878-121"><xref:System.String.Split%2A?displayProperty=nameWithType> kann ein Array mit Zeichenfolgen aufnehmen (Zeichenfolgen, die als Trennzeichen für die Analyse der Zielzeichenfolge fungieren, statt einzelne Zeichen).</span><span class="sxs-lookup"><span data-stu-id="ed878-121"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

<span data-ttu-id="ed878-122">Sie können diese Beispiele ausprobieren, indem Sie sich den Code in unserem [GitHub-Repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings) ansehen.</span><span class="sxs-lookup"><span data-stu-id="ed878-122">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings)</span></span>

## <a name="see-also"></a><span data-ttu-id="ed878-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed878-123">See Also</span></span>  
 [<span data-ttu-id="ed878-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ed878-124">C# Programming Guide</span></span>](../programming-guide/index.md)  
 [<span data-ttu-id="ed878-125">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ed878-125">Strings</span></span>](../programming-guide/strings/index.md)  
 [<span data-ttu-id="ed878-126">Reguläre Ausdrücke von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed878-126">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)

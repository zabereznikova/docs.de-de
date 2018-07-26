---
title: Speichern der Ergebnisse einer Abfrage im Speicher
description: So speichern Sie Ergebnisse.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 52d502a841c428bd90a26c803ba577e76c17197c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404300"
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="924d4-103">Speichern der Ergebnisse einer Abfrage im Speicher</span><span class="sxs-lookup"><span data-stu-id="924d4-103">Store the results of a query in memory</span></span>

<span data-ttu-id="924d4-104">Eine Abfrage besteht im Grunde aus einer Reihe von Anweisungen für das Abrufen und Organisieren von Daten.</span><span class="sxs-lookup"><span data-stu-id="924d4-104">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="924d4-105">Abfragen werden verzögert ausgeführt, da jedes nachfolgende Element im Ergebnis angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="924d4-105">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="924d4-106">Wenn Sie `foreach` zum Durchlaufen der Ergebnisse verwenden, werden Elemente so zurückgegeben, wie auf sie zugegriffen wurde.</span><span class="sxs-lookup"><span data-stu-id="924d4-106">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="924d4-107">Rufen Sie einfach eine der folgenden Methoden für die Abfragevariable auf, um eine Abfrage auszuwerten und ihre Ergebnisse ohne das Ausführen einer `foreach`-Schleife zu speichern:</span><span class="sxs-lookup"><span data-stu-id="924d4-107">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 <span data-ttu-id="924d4-108">Es wird empfohlen, dass Sie die zurückgegebenen Auflistungsobjekte beim Speichern der Abfrageergebnisse einer neuen Variable zuweisen, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="924d4-108">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>

## <a name="example"></a><span data-ttu-id="924d4-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="924d4-109">Example</span></span>

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a><span data-ttu-id="924d4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="924d4-110">See also</span></span>

[<span data-ttu-id="924d4-111">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="924d4-111">Language Integrated Query (LINQ)</span></span>](index.md)
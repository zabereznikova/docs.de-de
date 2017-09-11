---
title: Speichern der Ergebnisse einer Abfrage im Speicher
description: So speichern Sie Ergebnisse.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 35d908bde06ef55ba2dc93a73211f7be33b9332c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="f8ee9-104">Speichern der Ergebnisse einer Abfrage im Speicher</span><span class="sxs-lookup"><span data-stu-id="f8ee9-104">Store the results of a query in memory</span></span>

<span data-ttu-id="f8ee9-105">Eine Abfrage besteht im Grunde aus einer Reihe von Anweisungen für das Abrufen und Organisieren von Daten.</span><span class="sxs-lookup"><span data-stu-id="f8ee9-105">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="f8ee9-106">Abfragen werden verzögert ausgeführt, da jedes nachfolgende Element im Ergebnis angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="f8ee9-106">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="f8ee9-107">Wenn Sie `foreach` zum Durchlaufen der Ergebnisse verwenden, werden Elemente so zurückgegeben, wie auf sie zugegriffen wurde.</span><span class="sxs-lookup"><span data-stu-id="f8ee9-107">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="f8ee9-108">Rufen Sie einfach eine der folgenden Methoden für die Abfragevariable auf, um eine Abfrage auszuwerten und ihre Ergebnisse ohne das Ausführen einer `foreach`-Schleife zu speichern:</span><span class="sxs-lookup"><span data-stu-id="f8ee9-108">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 <span data-ttu-id="f8ee9-109">Es wird empfohlen, dass Sie die zurückgegebenen Auflistungsobjekte beim Speichern der Abfrageergebnisse einer neuen Variable zuweisen, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="f8ee9-109">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8ee9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8ee9-110">Example</span></span>  
 <span data-ttu-id="f8ee9-111">[!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8ee9-111">[!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="f8ee9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8ee9-112">See Also</span></span>  
 [<span data-ttu-id="f8ee9-113">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="f8ee9-113">LINQ Query Expressions</span></span>](index.md)


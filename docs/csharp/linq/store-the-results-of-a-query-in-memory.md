---
title: Speichern der Ergebnisse einer Abfrage im Speicher
description: So speichern Sie Ergebnisse.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 86a9c2d464eac83cabb5faa68987ad580fc31248
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="f7951-104">Speichern der Ergebnisse einer Abfrage im Speicher</span><span class="sxs-lookup"><span data-stu-id="f7951-104">Store the results of a query in memory</span></span>

<span data-ttu-id="f7951-105">Eine Abfrage besteht im Grunde aus einer Reihe von Anweisungen für das Abrufen und Organisieren von Daten.</span><span class="sxs-lookup"><span data-stu-id="f7951-105">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="f7951-106">Abfragen werden verzögert ausgeführt, da jedes nachfolgende Element im Ergebnis angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="f7951-106">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="f7951-107">Wenn Sie `foreach` zum Durchlaufen der Ergebnisse verwenden, werden Elemente so zurückgegeben, wie auf sie zugegriffen wurde.</span><span class="sxs-lookup"><span data-stu-id="f7951-107">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="f7951-108">Rufen Sie einfach eine der folgenden Methoden für die Abfragevariable auf, um eine Abfrage auszuwerten und ihre Ergebnisse ohne das Ausführen einer `foreach`-Schleife zu speichern:</span><span class="sxs-lookup"><span data-stu-id="f7951-108">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 <span data-ttu-id="f7951-109">Es wird empfohlen, dass Sie die zurückgegebenen Auflistungsobjekte beim Speichern der Abfrageergebnisse einer neuen Variable zuweisen, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="f7951-109">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7951-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7951-110">Example</span></span>  
 [!code-csharp[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="f7951-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7951-111">See Also</span></span>  
 [<span data-ttu-id="f7951-112">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="f7951-112">LINQ Query Expressions</span></span>](index.md)

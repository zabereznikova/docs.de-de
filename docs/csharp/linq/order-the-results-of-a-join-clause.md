---
title: Sortieren der Ergebnisse einer Join-Klausel
description: So sortieren Sie die Ergebnisse einer Join-Klausel.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6272181647bb200c18231c5fc836e3dd1a2d6d55
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="76d0f-104">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="76d0f-104">Order the results of a join clause</span></span>
<span data-ttu-id="76d0f-105">Dieses Beispiel zeigt, wie Sie die Ergebnisse einer Verknüpfungsoperation sortieren.</span><span class="sxs-lookup"><span data-stu-id="76d0f-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="76d0f-106">Beachten Sie, dass die Sortierung nach der Verknüpfung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76d0f-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="76d0f-107">Obwohl Sie eine `orderby`-Klausel mit einer oder mehreren Quellsequenzen verwenden können, wird dies normalerweise nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="76d0f-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="76d0f-108">Einige LINQ-Anbieter könnten diese Sortierung nach der Verknüpfung vielleicht nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="76d0f-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76d0f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76d0f-109">Example</span></span>  
 <span data-ttu-id="76d0f-110">Diese Abfrage erstellt eine Gruppenverknüpfung und sortiert die Gruppen anschließend anhand des Elements der Kategorie, das sich noch im Geltungsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="76d0f-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="76d0f-111">Innerhalb des anonymen Typinitialisierers ordnet eine Unterabfrage alle übereinstimmende Elemente aus der Produktsequenz.</span><span class="sxs-lookup"><span data-stu-id="76d0f-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 <span data-ttu-id="76d0f-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="76d0f-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="76d0f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76d0f-113">See also</span></span>  
 <span data-ttu-id="76d0f-114">[LINQ-Abfrageausdrücke](index.md) </span><span class="sxs-lookup"><span data-stu-id="76d0f-114">[LINQ query expressions](index.md) </span></span>  
 <span data-ttu-id="76d0f-115">[orderby-Klausel](../language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="76d0f-115">[orderby clause](../language-reference/keywords/orderby-clause.md) </span></span>  
 [<span data-ttu-id="76d0f-116">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="76d0f-116">join clause</span></span>](../language-reference/keywords/join-clause.md) 


---
title: Sortieren der Ergebnisse einer Join-Klausel
description: So sortieren Sie die Ergebnisse einer Join-Klausel.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f948c18fb16a4f3ac02945b4a63583f1b01cad40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="6e0e4-104">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="6e0e4-104">Order the results of a join clause</span></span>
<span data-ttu-id="6e0e4-105">Dieses Beispiel zeigt, wie Sie die Ergebnisse einer Verknüpfungsoperation sortieren.</span><span class="sxs-lookup"><span data-stu-id="6e0e4-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="6e0e4-106">Beachten Sie, dass die Sortierung nach der Verknüpfung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e0e4-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="6e0e4-107">Obwohl Sie eine `orderby`-Klausel mit einer oder mehreren Quellsequenzen verwenden können, wird dies normalerweise nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="6e0e4-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="6e0e4-108">Einige LINQ-Anbieter könnten diese Sortierung nach der Verknüpfung vielleicht nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6e0e4-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e0e4-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e0e4-109">Example</span></span>  
 <span data-ttu-id="6e0e4-110">Diese Abfrage erstellt eine Gruppenverknüpfung und sortiert die Gruppen anschließend anhand des Elements der Kategorie, das sich noch im Geltungsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="6e0e4-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="6e0e4-111">Innerhalb des anonymen Typinitialisierers ordnet eine Unterabfrage alle übereinstimmende Elemente aus der Produktsequenz.</span><span class="sxs-lookup"><span data-stu-id="6e0e4-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="6e0e4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e0e4-112">See also</span></span>  
 [<span data-ttu-id="6e0e4-113">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="6e0e4-113">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="6e0e4-114">orderby-Klausel</span><span class="sxs-lookup"><span data-stu-id="6e0e4-114">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="6e0e4-115">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="6e0e4-115">join clause</span></span>](../language-reference/keywords/join-clause.md) 

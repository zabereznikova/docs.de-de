---
title: Erstellen einer geschachtelten Gruppe
description: So erstellen Sie eine geschachtelte Gruppe
ms.date: 12/1/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: dd1158bfa1456342fe8967aed5e02ecebae591c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273142"
---
# <a name="create-a-nested-group"></a><span data-ttu-id="68a90-103">Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="68a90-103">Create a nested group</span></span>

<span data-ttu-id="68a90-104">Im folgenden Beispiel wird veranschaulicht, wie geschachtelte Gruppen in einem LINQ-Abfrageausdruck erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="68a90-104">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="68a90-105">Jede Gruppe, die nach Studienjahr oder Klassenstufe erstellt wird, wird basierend auf den Namen der einzelnen Personen weiter in Gruppen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="68a90-105">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68a90-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="68a90-106">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="68a90-107">Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind.</span><span class="sxs-lookup"><span data-stu-id="68a90-107">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 [!code-csharp[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 <span data-ttu-id="68a90-108">Beachten Sie, das drei geschachtelte `foreach`-Schleifen für die Iteration über die inneren Elemente einer geschachtelten Gruppe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="68a90-108">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a90-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68a90-109">See also</span></span>  
 [<span data-ttu-id="68a90-110">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="68a90-110">LINQ Query Expressions</span></span>](index.md)

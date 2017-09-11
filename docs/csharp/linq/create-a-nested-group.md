---
title: Erstellen einer geschachtelten Gruppe
description: So erstellen Sie eine geschachtelte Gruppe
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 361ac1f224c6eef292fcf8434c7e465c9448b19c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-nested-group"></a><span data-ttu-id="b1fb4-104">Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="b1fb4-104">Create a nested group</span></span>

<span data-ttu-id="b1fb4-105">Im folgenden Beispiel wird veranschaulicht, wie geschachtelte Gruppen in einem LINQ-Abfrageausdruck erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b1fb4-105">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="b1fb4-106">Jede Gruppe, die nach Studienjahr oder Klassenstufe erstellt wird, wird basierend auf den Namen der einzelnen Personen weiter in Gruppen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="b1fb4-106">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1fb4-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1fb4-107">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="b1fb4-108">Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b1fb4-108">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 <span data-ttu-id="b1fb4-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b1fb4-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span></span>  
  
 <span data-ttu-id="b1fb4-110">Beachten Sie, das drei geschachtelte `foreach`-Schleifen für die Iteration über die inneren Elemente einer geschachtelten Gruppe erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b1fb4-110">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1fb4-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1fb4-111">See also</span></span>  
 [<span data-ttu-id="b1fb4-112">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="b1fb4-112">LINQ Query Expressions</span></span>](index.md)


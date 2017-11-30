---
title: "Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b28ff0bb8436fefc4956918889435e258ae98b12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="98012-102">Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren</span><span class="sxs-lookup"><span data-stu-id="98012-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="98012-103">Das folgende Beispiel zeigt eine Möglichkeit, einen einfachen benutzerdefinierten Partitionierer für PLINQ implementiert wird, statische Partitionierung ausführt.</span><span class="sxs-lookup"><span data-stu-id="98012-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="98012-104">Da der Partitionierer dynamische Partitionen nicht unterstützt, ist es nicht von <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="98012-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="98012-105">Diese speziellen Partitionierer möglicherweise über dem Bereich Standardpartitionierer für Datenquellen Beschleunigung bereit für die jedes Element eine zunehmende Zeitspanne Verarbeitung erfordert.</span><span class="sxs-lookup"><span data-stu-id="98012-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98012-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98012-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="98012-107">Die Partitionen in diesem Beispiel basiert auf der Annahme der ein linearer Anstieg bei Verarbeitungszeit für jedes Element.</span><span class="sxs-lookup"><span data-stu-id="98012-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="98012-108">In der Realität kann es schwer Verarbeitungszeiten auf diese Weise vorhersagbar sein.</span><span class="sxs-lookup"><span data-stu-id="98012-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="98012-109">Bei Verwendung ein statisches Partitionierers mit einer bestimmten Datenquelle können Sie optimieren Sie die Partitionierung Formel für die Quelle, Lastenausgleich Logik hinzufügen, oder verwenden Sie ein Segment Partitionierung Ansatz wie gezeigt in [Vorgehensweise: Implementieren dynamische Partitionen](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="98012-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98012-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98012-110">See Also</span></span>  
 [<span data-ttu-id="98012-111">Benutzerdefinierte Partitionierer für PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="98012-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)

---
title: 'Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren'
ms.date: 03/30/2017
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
ms.openlocfilehash: 1593f1bc3c17f162b20f8bd9f645d51393f2198c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817132"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="2c104-102">Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren</span><span class="sxs-lookup"><span data-stu-id="2c104-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="2c104-103">Das folgende Beispiel zeigt eine Möglichkeit, einen einfachen benutzerdefinierten Partitionierer für PLINQ zu implementieren, der statische Partitionierung ausführt.</span><span class="sxs-lookup"><span data-stu-id="2c104-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="2c104-104">Da der Partitionierer keine dynamischen Partitionen unterstützt, kann er von <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> nicht genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="2c104-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2c104-105">Dieser spezielle Partitionierer kann möglicherweise bei Datenquellen, für die jedes Element zunehmende Verarbeitungszeit erfordert, gegenüber dem Standardbereichspartitionierer für Beschleunigung sorgen.</span><span class="sxs-lookup"><span data-stu-id="2c104-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c104-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c104-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="2c104-107">Bei den Partitionen in diesem Beispiel wird ein linearer Anstieg der Verarbeitungszeit für jedes Element vorausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2c104-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="2c104-108">In der Realität kann es schwierig sein, Verarbeitungszeiten auf diese Weise vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="2c104-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="2c104-109">Bei Verwendung eines statischen Partitionierers mit einer bestimmten Datenquelle können Sie die Partitionierungsformel für die Quelle optimieren, Lastenausgleichslogik hinzufügen oder einen Blockpartitionierungansatz wie in [Gewusst wie: Implementieren von dynamischen Partitionen](how-to-implement-dynamic-partitions.md) beschrieben verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c104-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c104-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c104-110">See also</span></span>

- [<span data-ttu-id="2c104-111">Benutzerdefinierte Partitionierer für PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="2c104-111">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)

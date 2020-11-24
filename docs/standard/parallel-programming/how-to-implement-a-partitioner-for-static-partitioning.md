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
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren
Das folgende Beispiel zeigt eine Möglichkeit, einen einfachen benutzerdefinierten Partitionierer für PLINQ zu implementieren, der statische Partitionierung ausführt. Da der Partitionierer keine dynamischen Partitionen unterstützt, kann er von <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> nicht genutzt werden. Dieser spezielle Partitionierer kann möglicherweise bei Datenquellen, für die jedes Element zunehmende Verarbeitungszeit erfordert, gegenüber dem Standardbereichspartitionierer für Beschleunigung sorgen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Bei den Partitionen in diesem Beispiel wird ein linearer Anstieg der Verarbeitungszeit für jedes Element vorausgesetzt. In der Realität kann es schwierig sein, Verarbeitungszeiten auf diese Weise vorherzusagen. Bei Verwendung eines statischen Partitionierers mit einer bestimmten Datenquelle können Sie die Partitionierungsformel für die Quelle optimieren, Lastenausgleichslogik hinzufügen oder einen Blockpartitionierungansatz wie in [Gewusst wie: Implementieren von dynamischen Partitionen](how-to-implement-dynamic-partitions.md) beschrieben verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Benutzerdefinierte Partitionierer für PLINQ und TPL](custom-partitioners-for-plinq-and-tpl.md)

---
title: 'Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 302d7d98d04e528d205edf38c3fa13bb3f2b2252
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863072"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren
Das folgende Beispiel zeigt eine Möglichkeit, einen einfachen benutzerdefinierten Partitionierer für PLINQ zu implementieren, der statische Partitionierung ausführt. Da der Partitionierer keine dynamischen Partitionen unterstützt, kann er von <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> nicht genutzt werden. Dieser spezielle Partitionierer kann möglicherweise bei Datenquellen, für die jedes Element zunehmende Verarbeitungszeit erfordert, gegenüber dem Standardbereichspartitionierer für Beschleunigung sorgen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Bei den Partitionen in diesem Beispiel wird ein linearer Anstieg der Verarbeitungszeit für jedes Element vorausgesetzt. In der Realität kann es schwierig sein, Verarbeitungszeiten auf diese Weise vorherzusagen. Bei Verwendung eines statischen Partitionierers mit einer bestimmten Datenquelle können Sie die Partitionierungsformel für die Quelle optimieren, Lastenausgleichslogik hinzufügen oder einen Blockpartitionierungansatz wie in [Gewusst wie: Implementieren von dynamischen Partitionen](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) beschrieben verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Partitionierer für PLINQ und TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)

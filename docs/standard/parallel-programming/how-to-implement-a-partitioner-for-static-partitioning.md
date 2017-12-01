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
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren
Das folgende Beispiel zeigt eine Möglichkeit, einen einfachen benutzerdefinierten Partitionierer für PLINQ implementiert wird, statische Partitionierung ausführt. Da der Partitionierer dynamische Partitionen nicht unterstützt, ist es nicht von <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Diese speziellen Partitionierer möglicherweise über dem Bereich Standardpartitionierer für Datenquellen Beschleunigung bereit für die jedes Element eine zunehmende Zeitspanne Verarbeitung erfordert.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Die Partitionen in diesem Beispiel basiert auf der Annahme der ein linearer Anstieg bei Verarbeitungszeit für jedes Element. In der Realität kann es schwer Verarbeitungszeiten auf diese Weise vorhersagbar sein. Bei Verwendung ein statisches Partitionierers mit einer bestimmten Datenquelle können Sie optimieren Sie die Partitionierung Formel für die Quelle, Lastenausgleich Logik hinzufügen, oder verwenden Sie ein Segment Partitionierung Ansatz wie gezeigt in [Vorgehensweise: Implementieren dynamische Partitionen](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Partitionierer für PLINQ und TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)

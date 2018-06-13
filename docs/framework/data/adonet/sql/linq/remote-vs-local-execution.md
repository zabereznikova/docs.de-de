---
title: Remoteausführung von Abfragen im Vergleich zur lokaler Ausführung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: 9488cb4c15c2e0646d91bdba36e7d4e2be2efbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360046"
---
# <a name="remote-vs-local-execution"></a>Remoteausführung von Abfragen im Vergleich zur lokaler Ausführung
Sie können festlegen, ob Ihre Abfragen remote (das Datenbankmodul führt eine Abfrage mit der Datenbank aus ) oder lokal ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] führt die Abfrage mit einem lokalen Cache aus) erfolgen sollen.  
  
## <a name="remote-execution"></a>Remoteausführung  
 Betrachten Sie die folgende Abfrage:  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 Wenn Ihre Datenbank Tausende von Zeilen mit Bestellungen aufweist, möchten Sie diese nicht alle abrufen müssen, um eine kleinere Teilmenge zu bearbeiten. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementiert die <xref:System.Data.Linq.EntitySet%601>-Klasse die <xref:System.Linq.IQueryable>-Schnittstelle. Dieser Ansatz stellt sicher, dass solche Abfragen remote ausgeführt werden können. Aus dieser Technik ergeben sich zwei wesentliche Vorteile:  
  
-   Unnötige Daten werden nicht abgerufen.  
  
-   Eine vom Datenbankmodul ausgeführte Abfrage ist aufgrund der Datenbankindizes oft effizienter.  
  
## <a name="local-execution"></a>lokaler Ausführung  
 In anderen Situationen möchten Sie ggf. alle verbundenen Entitäten in den lokalen Cache übertragen. Zu diesem Zweck stellt <xref:System.Data.Linq.EntitySet%601> die <xref:System.Data.Linq.EntitySet%601.Load%2A>-Methode bereit, um explizit alle Member von <xref:System.Data.Linq.EntitySet%601> zu laden.  
  
 Wenn ein <xref:System.Data.Linq.EntitySet%601> bereits geladen ist, werden nachfolgende Abfragen lokal ausgeführt. Dieser Ansatz unterstützt Sie auf zwei Arten:  
  
-   Wenn der gesamte Satz lokal oder mehrmals verwendet werden muss, können Sie Remoteabfragen und die zugehörige Latenz vermeiden.  
  
-   Die Entität kann als vollständige Entität serialisiert werden.  
  
 Das folgende Codefragment zeigt, wie die lokale Ausführung erreicht werden kann:  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a>Vergleich  
 Diese beiden Möglichkeiten bieten eine leistungsfähige Kombination aus Optionen: Remoteausführung für große Auflistungen und lokale Ausführung für kleine Auflistungen bzw. wenn die gesamte Auflistung benötigt wird. Die Remoteausführung wird mit <xref:System.Linq.IQueryable> implementiert, die lokale Ausführung mit einer <xref:System.Collections.Generic.IEnumerable%601>-Auflistung im Arbeitsspeicher. Lokalen Ausführung erzwingen (d. h. <xref:System.Collections.Generic.IEnumerable%601>), finden Sie unter [Konvertieren eines Typs in eine generische "IEnumerable"](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).  
  
### <a name="queries-against-unordered-sets"></a>Abfragen von ungeordneten Sätzen  
 Beachten Sie die wichtigen Unterschied zwischen einer lokalen Auflistung mit Implementierung <xref:System.Collections.Generic.List%601> und eine Auflistung, die Remoteabfragen mit *ungeordneten Sätzen* in einer relationalen Datenbank. <xref:System.Collections.Generic.List%601>-Methoden wie jene, die Indexwerte verwenden, erfordern Listensemantik, die in der Regel nicht durch eine Remoteabfrage mit einem ungeordneten Satz erreicht werden kann. Aus diesem Grund laden diese Methoden implizit den <xref:System.Data.Linq.EntitySet%601>, um die lokale Ausführung zu ermöglichen.  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)

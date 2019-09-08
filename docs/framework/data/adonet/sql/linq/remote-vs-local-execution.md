---
title: Remoteausführung im Vergleich zu lokaler Ausführung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: a21d5bbffdb1a78d3062929a1ca384a750af59a7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781157"
---
# <a name="remote-vs-local-execution"></a>Remoteausführung im Vergleich zu lokaler Ausführung
Sie können festlegen, ob Ihre Abfragen remote (die Datenbank-Engine führt eine Abfrage mit der Datenbank aus ) oder lokal ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] führt die Abfrage mit einem lokalen Cache aus) erfolgen sollen.  
  
## <a name="remote-execution"></a>Remoteausführung  
 Betrachten Sie die folgende Abfrage:  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 Wenn Ihre Datenbank Tausende von Zeilen mit Bestellungen aufweist, möchten Sie diese nicht alle abrufen müssen, um eine kleinere Teilmenge zu bearbeiten. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementiert die <xref:System.Data.Linq.EntitySet%601>-Klasse die <xref:System.Linq.IQueryable>-Schnittstelle. Dieser Ansatz stellt sicher, dass solche Abfragen remote ausgeführt werden können. Aus dieser Technik ergeben sich zwei wesentliche Vorteile:  
  
- Unnötige Daten werden nicht abgerufen.  
  
- Eine von der Datenbank-Engine ausgeführte Abfrage ist aufgrund der Datenbankindizes oft effizienter.  
  
## <a name="local-execution"></a>lokaler Ausführung  
 In anderen Situationen möchten Sie ggf. alle verbundenen Entitäten in den lokalen Cache übertragen. Zu diesem Zweck stellt <xref:System.Data.Linq.EntitySet%601> die <xref:System.Data.Linq.EntitySet%601.Load%2A>-Methode bereit, um explizit alle Member von <xref:System.Data.Linq.EntitySet%601> zu laden.  
  
 Wenn ein <xref:System.Data.Linq.EntitySet%601> bereits geladen ist, werden nachfolgende Abfragen lokal ausgeführt. Dieser Ansatz unterstützt Sie auf zwei Arten:  
  
- Wenn der gesamte Satz lokal oder mehrmals verwendet werden muss, können Sie Remoteabfragen und die zugehörige Latenz vermeiden.  
  
- Die Entität kann als vollständige Entität serialisiert werden.  
  
 Das folgende Codefragment zeigt, wie die lokale Ausführung erreicht werden kann:  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a>Vergleich  
 Diese beiden Möglichkeiten bieten eine leistungsfähige Kombination aus Optionen: Remoteausführung für große Auflistungen und lokale Ausführung für kleine Auflistungen bzw. wenn die gesamte Auflistung benötigt wird. Die Remoteausführung wird mit <xref:System.Linq.IQueryable> implementiert, die lokale Ausführung mit einer <xref:System.Collections.Generic.IEnumerable%601>-Auflistung im Arbeitsspeicher. Informationen zum Erzwingen der <xref:System.Collections.Generic.IEnumerable%601>lokalen Ausführung (d. h.) finden Sie unter [Konvertieren eines Typs in eine generische IEnumerable](convert-a-type-to-a-generic-ienumerable.md)-Schnittstelle.  
  
### <a name="queries-against-unordered-sets"></a>Abfragen von ungeordneten Sätzen  
 Beachten Sie den wichtigen Unterschied zwischen einer lokalen- <xref:System.Collections.Generic.List%601> Auflistung, die implementiert, und einer-Auflistung, die Remote Abfragen für *ungeordnete Sätze* in einer relationalen Datenbank bereitstellt. <xref:System.Collections.Generic.List%601>-Methoden wie jene, die Indexwerte verwenden, erfordern Listensemantik, die in der Regel nicht durch eine Remoteabfrage mit einem ungeordneten Satz erreicht werden kann. Aus diesem Grund laden diese Methoden implizit den <xref:System.Data.Linq.EntitySet%601>, um die lokale Ausführung zu ermöglichen.  
  
## <a name="see-also"></a>Siehe auch

- [Abfragekonzepte](query-concepts.md)

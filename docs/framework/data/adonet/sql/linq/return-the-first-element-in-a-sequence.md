---
title: Zurückgeben des ersten Elements in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 39cf9270b08fce64590fef418bb428c5a781b0e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963809"
---
# <a name="return-the-first-element-in-a-sequence"></a>Zurückgeben des ersten Elements in einer Sequenz
Verwenden Sie den <xref:System.Linq.Enumerable.First%2A>-Operator, um das erste Element in einer Sequenz zurückzugeben. Abfragen, die <xref:System.Linq.Enumerable.First%2A> verwenden, werden sofort ausgeführt.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt den <xref:System.Linq.Enumerable.Last%2A>-Operator nicht.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird der erste `Shipper` (Spediteur) in einer Tabelle gesucht:  
  
 Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lauten die Ergebnisse:  
  
 `ID = 1, Company = Speedy Express`  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code ermittelt den einzigen `Customer` (Kunden) mit `CustomerID`-BONAP.  
  
 Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lauten die Ergebnisse `ID = BONAP, Contact = Laurence Lebihan`.  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)

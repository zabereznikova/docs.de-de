---
title: Zurückgeben des ersten Elements in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 9faeed754942d7b176872484ac776c1df592bbd8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792724"
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

- [Abfragebeispiele](query-examples.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](downloading-sample-databases.md)

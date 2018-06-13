---
title: Zählen der Anzahl von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 928cfd33a187637c6d18da3cccefb22bb2950acf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353833"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a>Zählen der Anzahl von Elementen in einer Sequenz
Verwenden Sie den <xref:System.Linq.Enumerable.Count%2A>-Operator, um die Anzahl von Elementen in einer Sequenz zu zählen.  
  
 Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, wird eine Ausgabe von `91` erzeugt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Anzahl von `Customers` (Kunden) in der Datenbank gezählt.  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Anzahl von Produkten in der Datenbank gezählt, die nicht eingestellt wurden.  
  
 Wenn Sie dieses Beispiel mit der Beispieldatenbank Northwind ausführen, wird eine Ausgabe von `69` erzeugt.  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Aggregatabfragen](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)

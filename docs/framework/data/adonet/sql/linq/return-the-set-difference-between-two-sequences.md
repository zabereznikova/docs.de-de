---
title: Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 7edc60c7ab8510aadd9ac273529a88adeb41352a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124279"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen
Verwenden Sie den <xref:System.Linq.Queryable.Except%2A>-Operator, um die Satzdifferenz zwischen zwei Sequenzen zurückzugeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird <xref:System.Linq.Queryable.Except%2A> verwendet, um eine Sequenz aller Länder zurückzugeben, in denen `Customers` (Kunden), aber keine `Employees` (Mitarbeiter) leben.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Except%2A>-Operation nur für Sätze gut definiert. Die Semantik für Multisets ist nicht definiert.  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Übersetzen von Standardabfrageoperatoren](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)

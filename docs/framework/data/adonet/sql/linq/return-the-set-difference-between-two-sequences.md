---
title: Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 5bb7d797ad2adc4374f7a10c11d66be69feeb7a1
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380050"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen
Verwenden Sie den <xref:System.Linq.Queryable.Except%2A>-Operator, um die Satzdifferenz zwischen zwei Sequenzen zurückzugeben.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet <xref:System.Linq.Queryable.Except%2A> um eine Sequenz aller Länder/Regionen in der `Customers` live, aber keine `Employees` live.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Except%2A>-Operation nur für Sätze gut definiert. Die Semantik für Multisets ist nicht definiert.  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Übersetzen von Standardabfrageoperatoren](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)

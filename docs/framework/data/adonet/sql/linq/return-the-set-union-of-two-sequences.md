---
title: Zurückgeben der Vereinigungsmenge von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: ffdc1dc0f9b5c2ed3b9898d0c71c9b384723fe05
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200553"
---
# <a name="return-the-set-union-of-two-sequences"></a>Zurückgeben der Vereinigungsmenge von zwei Sequenzen
Verwenden Sie den <xref:System.Linq.Queryable.Union%2A>-Operator, um die Vereinigungsmenge von zwei Sequenzen zurückzugeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird <xref:System.Linq.Queryable.Union%2A> verwendet, um eine Sequenz aller Länder zurückzugeben, in denen `Customers` (Kunden) oder `Employees` (Mitarbeiter) vorkommen.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> Operator ist für Multisets als ungeordnete Verkettung der Multisets definiert (effektiv das Ergebnis der [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) -Klausel in SQL).

Weitere Informationen und Beispiele finden Sie unter <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Siehe auch  
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Übersetzen von Standardabfrageoperatoren](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)

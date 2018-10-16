---
title: Zurückgeben der Vereinigungsmenge von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: c7d7a267df13cfa54d682ab9b65953f2c0a85a27
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347545"
---
# <a name="return-the-set-union-of-two-sequences"></a>Zurückgeben der Vereinigungsmenge von zwei Sequenzen
Verwenden Sie den <xref:System.Linq.Queryable.Union%2A>-Operator, um die Vereinigungsmenge von zwei Sequenzen zurückzugeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird <xref:System.Linq.Queryable.Union%2A> verwendet, um eine Sequenz aller Länder zurückzugeben, in denen `Customers` (Kunden) oder `Employees` (Mitarbeiter) vorkommen.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> Operator ist für Multisets als ungeordnete Verkettung der Multisets definiert (effektiv das Ergebnis der [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) -Klausel in SQL).  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Übersetzen von Standardabfrageoperatoren](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)

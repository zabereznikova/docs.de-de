---
title: Zurückgeben der Vereinigungsmenge von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 058856243b2a8daaecd653a9b5999013de5407a8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182527"
---
# <a name="return-the-set-union-of-two-sequences"></a>Zurückgeben der Vereinigungsmenge von zwei Sequenzen
Verwenden Sie den <xref:System.Linq.Queryable.Union%2A>-Operator, um die Vereinigungsmenge von zwei Sequenzen zurückzugeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel <xref:System.Linq.Queryable.Union%2A> wird verwendet, um eine Sequenz aller Länder/Regionen zurückzugeben, in `Customers` denen `Employees`entweder oder vorhanden ist.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]wird der <xref:System.Linq.Queryable.Union%2A> -Operator für Multisets als ungeordnete Verkettung der Multisets definiert ( [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) effektiv das Ergebnis der-Klausel in SQL).

Weitere Informationen und Beispiele finden <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>Sie unter.
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](query-examples.md)
- [Übersetzen von Standardabfrageoperatoren](standard-query-operator-translation.md)

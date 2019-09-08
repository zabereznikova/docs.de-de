---
title: Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 92513ed33e2afb785edbdd462ba7bc14923aa6b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781148"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen
Verwenden Sie den <xref:System.Linq.Queryable.Except%2A>-Operator, um die Satzdifferenz zwischen zwei Sequenzen zurückzugeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel <xref:System.Linq.Queryable.Except%2A> wird verwendet, um eine Sequenz aller Länder/Regionen zurück `Customers` zugeben, in denen Live `Employees` , aber ohne Live ist.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Except%2A>-Operation nur für Sätze gut definiert. Die Semantik für Multisets ist nicht definiert.  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](query-examples.md)
- [Übersetzen von Standardabfrageoperatoren](standard-query-operator-translation.md)

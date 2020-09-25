---
title: Zurückgeben der Schnittmenge von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 421ec544345e41f910bf80c855a3a6b4de1c46a6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200224"
---
# <a name="return-the-set-intersection-of-two-sequences"></a>Zurückgeben der Schnittmenge von zwei Sequenzen

Verwenden Sie den <xref:System.Linq.Queryable.Intersect%2A>-Operator, um die Schnittmenge von zwei Sequenzen zurückzugeben.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird verwendet <xref:System.Linq.Queryable.Intersect%2A> , um eine Sequenz aller Länder/Regionen zurückzugeben, in denen und aktiv sind `Customers` `Employees` .  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Intersect%2A>-Operation nur für Sätze gut definiert. Die Semantik für Multisets ist nicht definiert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfrage Beispiele](query-examples.md)
- [Übersetzen von Standardabfrageoperatoren](standard-query-operator-translation.md)

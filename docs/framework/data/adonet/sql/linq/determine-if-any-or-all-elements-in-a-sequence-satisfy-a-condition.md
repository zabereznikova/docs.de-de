---
title: Bestimmen, ob ein Element oder alle Elemente einer Sequenz eine Bedingung erfüllen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: 7de65579cb41641aded0b9a320fac59804959ff5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782229"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a>Bestimmen, ob ein Element oder alle Elemente einer Sequenz eine Bedingung erfüllen
Der <xref:System.Linq.Enumerable.All%2A>-Operator gibt `true` zurück, wenn alle Elemente in einer Sequenz eine Bedingung erfüllen.  
  
 Der <xref:System.Linq.Queryable.Any%2A>-Operator gibt `true` zurück, wenn ein beliebiges Element in einer Sequenz eine Bedingung erfüllt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Sequenz von Kunden mit mindestens einer Bestellung zurückgegeben. Die `Where` `true` `Customer` -Klausel wertet zu aus, wenn der `Order`angegebene über einen verfügt. / `where`  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Visual Basic-Code ermittelt die Liste der Kunden, die noch keine Bestellungen übermittelt haben. Außerdem wird sichergestellt, dass für jeden Kunden in dieser Liste Kontaktinformationen angegeben werden.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden C#-Beispiel wird eine Sequenz von Kunden zurückgegeben, deren Bestellungen einen `ShipCity` (Lieferort) aufweisen, der mit "C" anfängt. Außerdem werden Kunden ohne bisherige Bestellungen zurückgegeben. (Per Definition gibt der <xref:System.Linq.Queryable.All%2A>-Operator bei einer leeren Sequenz `true` zurück.) Kunden ohne Bestellungen werden mithilfe des `Count`-Operators von der Konsolenausgabe ausgeschlossen.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](query-examples.md)

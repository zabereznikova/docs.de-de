---
title: Verketten von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: 87d341357b8d11eafbc3f3867c45ac5a32270688
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164401"
---
# <a name="concatenate-two-sequences"></a>Verketten von zwei Sequenzen

Verwenden Sie den <xref:System.Linq.Queryable.Concat%2A>-Operator, um zwei Sequenzen zu verketten.  
  
 Der <xref:System.Linq.Queryable.Concat%2A>-Operator wurde für geordnete Multisets definiert, bei denen die Reihenfolgen des Empfängers und das Argument identisch sind.  
  
 Die Sortierung in SQL ist der letzte Schritt vor dem Erzeugen von Ergebnissen. Aus diesem Grund wird der <xref:System.Linq.Queryable.Concat%2A> durch Verwendung von `UNION ALL`-Operator implementiert, und die Reihenfolge der Argumente wird nicht beibehalten. Um zu gewährleisten, dass die Sortierung der Ergebnisse richtig ist, stellen Sie sicher, dass diese explizit sortiert werden.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird <xref:System.Linq.Queryable.Concat%2A> verwendet, um eine Sequenz der Telefon- und Faxnummern aller `Customer` (Kunden) und `Employee` (Mitarbeiter) zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird <xref:System.Linq.Queryable.Concat%2A> verwendet, um eine Sequenz aller Namens- und Telefonnummernzuordnungen für `Customer` (Kunden) und `Employee` (Mitarbeiter) zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfrage Beispiele](query-examples.md)
- [Übersetzen von Standardabfrageoperatoren](standard-query-operator-translation.md)

---
title: 'Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 002a644ff5d48b25351228dcd74330707491d6c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782095"
---
# <a name="formulate-joins-and-cross-product-queries"></a>Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen
In den folgenden Beispielen wird gezeigt, wie Ergebnisse aus mehreren Tabellen kombiniert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Fremdschlüssel Navigation in `From` der-Klausel in`from` Visual Basic ( C#-Klausel in) verwendet, um alle Bestellungen für Kunden in London auszuwählen.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Fremdschlüssel Navigation in `Where` der-Klausel in`where` Visual Basic ( C#-Klausel in) verwendet, um nach außen `Products` zu `Supplier` filtern, dessen im USA ist.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Fremdschlüssel Navigation in `From` der-Klausel in`from` Visual Basic ( C#-Klausel in) zum Filtern von Mitarbeitern in Seattle und zum Auflisten ihrer Gebiete verwendet.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Fremdschlüssel Navigation in `Select` der-Klausel in`select` Visual Basic ( C#-Klausel in) verwendet, um nach Paaren von Mitarbeitern zu filtern, bei denen ein Mitarbeiter den anderen meldet und `City`in dem beide Mitarbeiter vom gleichen sind.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Visual Basic Beispiel wird nach allen Kunden und Bestellungen gesucht, es wird sichergestellt, dass die Bestellungen mit Kunden abgeglichen werden, und es wird sichergestellt, dass für jeden Kunden in dieser Liste ein Kontakt Name angegeben wird.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Tabellen explizit verknüpft, und die Ergebnisse aus beiden Tabellen werden projiziert.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden explizit drei Tabellen verknüpft, und Ergebnisse aus diesen werden projiziert.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Erreichen einer `LEFT OUTER JOIN` mithilfe von `DefaultIfEmpty()` veranschaulicht. Die `DefaultIfEmpty()`-Methode gibt NULL zurück, wenn es keine `Order` für den `Employee` gibt.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel projiziert einen `let`-Ausdruck, der sich aus einem Join ergibt.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein `join` mit einem zusammengesetzten Schlüssel gezeigt.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Konstruktion eines `join`, bei dem eine Seite auf NULL festgelegt werden kann und die andere nicht.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](query-examples.md)

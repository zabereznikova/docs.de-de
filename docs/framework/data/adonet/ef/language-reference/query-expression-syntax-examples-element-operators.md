---
title: 'Beispiele für die Abfrageausdruckssyntax: Elementoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 5736828a629368a5b9abea9e63f7df2d2de3ca8d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249522"
---
# <a name="query-expression-syntax-examples-element-operators"></a>Beispiele für die Abfrageausdruckssyntax: Elementoperatoren
In den Beispielen in diesem Thema wird gezeigt, wie <xref:System.Linq.Enumerable.First%2A> die-Methode verwendet wird, um das [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mithilfe der Abfrage Ausdruckssyntax abzufragen. Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.  
  
 In den Beispielen in diesem Thema werden die `using` folgenden / `Imports` -Anweisungen verwendet:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a>Erster  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet die <xref:System.Linq.Enumerable.First%2A>-Methode, um den ersten Kontakt zurückzugeben, dessen Vorname "Brooke" lautet.  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen in LINQ to Entities](queries-in-linq-to-entities.md)

---
title: "Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a3dae34f2b5904312fa3fcd994a01b2e024f1970
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="return-the-set-difference-between-two-sequences"></a>Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen
Verwenden Sie den <xref:System.Linq.Queryable.Except%2A>-Operator, um die Satzdifferenz zwischen zwei Sequenzen zurückzugeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird <xref:System.Linq.Queryable.Except%2A> verwendet, um eine Sequenz aller Länder zurückzugeben, in denen `Customers` (Kunden), aber keine `Employees` (Mitarbeiter) leben.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Except%2A>-Operation nur für Sätze gut definiert. Die Semantik für Multisets ist nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiele für Abfragen](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Standardabfrageoperatoren](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)

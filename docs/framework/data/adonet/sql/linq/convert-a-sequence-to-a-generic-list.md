---
title: Konvertieren einer Sequenz in eine generische Liste
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 43960d100cde7f746a56c023d305795e13bc04e7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247869"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Konvertieren einer Sequenz in eine generische Liste
Verwenden Sie <xref:System.Linq.Enumerable.ToList%2A>, um eine generische Liste aus einer Sequenz zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird <xref:System.Linq.Enumerable.ToList%2A> verwendet, um eine Abfrage sofort in eine generische <xref:System.Collections.Generic.List%601> zu evaluieren.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](query-examples.md)

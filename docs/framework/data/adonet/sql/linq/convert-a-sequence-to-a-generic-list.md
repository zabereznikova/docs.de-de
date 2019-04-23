---
title: Konvertieren einer Sequenz in eine generische Liste
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 2c83a744e26fabb6f3e6ddd0a31c7cdd0c7139a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140594"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Konvertieren einer Sequenz in eine generische Liste
Verwenden Sie <xref:System.Linq.Enumerable.ToList%2A>, um eine generische Liste aus einer Sequenz zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird <xref:System.Linq.Enumerable.ToList%2A> verwendet, um eine Abfrage sofort in eine generische <xref:System.Collections.Generic.List%601> zu evaluieren.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)

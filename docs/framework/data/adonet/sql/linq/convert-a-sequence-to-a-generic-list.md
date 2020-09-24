---
title: Konvertieren einer Sequenz in eine generische Liste
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 79e3ddaff0234dfb5f91e36bacd3279afa9ec265
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164388"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Konvertieren einer Sequenz in eine generische Liste

Verwenden Sie <xref:System.Linq.Enumerable.ToList%2A>, um eine generische Liste aus einer Sequenz zu erstellen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird <xref:System.Linq.Enumerable.ToList%2A> verwendet, um eine Abfrage sofort in eine generische <xref:System.Collections.Generic.List%601> zu evaluieren.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfrage Beispiele](query-examples.md)

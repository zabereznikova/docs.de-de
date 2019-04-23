---
title: 'Vorgehensweise: Behandeln von zusammengesetzten Schlüsseln in Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 2621ab4db207d1b868fbe3778c30c744201b0506
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135251"
---
# <a name="how-to-handle-composite-keys-in-queries"></a>Vorgehensweise: Behandeln von zusammengesetzten Schlüsseln in Abfragen
Einige Operatoren können nur ein Argument annehmen. Muss Ihr Argument mehrere Datenbankspalten aufnehmen, müssen Sie einen anonymen Typ erstellen, um die Kombination darzustellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Abfrage, die den `GroupBy`-Operator aufruft. Dieser kann nur ein `key`-Argument aufnehmen.  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a>Beispiel  
 Die gleiche Situation betrifft Joins wie im folgenden Beispiel:  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)

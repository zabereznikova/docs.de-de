---
title: 'Vorgehensweise: Behandeln von zusammengesetzten Schlüsseln in Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: a6c6e7d1c1d29a049b50f4ea9d70ef5cd9e89a44
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793581"
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

- [Abfragekonzepte](query-concepts.md)

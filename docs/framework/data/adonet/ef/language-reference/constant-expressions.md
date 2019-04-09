---
title: Konstante Ausdrücke
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 10c74ede8d490bf96a9d0855889669bdc2628b01
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209202"
---
# <a name="constant-expressions"></a>Konstante Ausdrücke
Ein konstanter Ausdruck besteht aus einem konstanten Wert. Konstante Werte werden sofort in konstante Befehlsstrukturausdrücke konvertiert. Es findet keine Übersetzung auf dem Client statt. Dazu gehören Ausdrücke, die einen konstanten Wert zurückgeben. Daher sollte Datenquellenverhalten für alle Ausdrücke erwartet werden, die Konstanten enthalten. Dies kann zu Verhalten führen, das sich von CLR-Verhalten unterscheidet.  
  
 Im folgenden Beispiel wird ein konstanter Ausdruck gezeigt, der auf dem Server ausgewertet wird.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] unterstützt keine Verwendung von Benutzerklassen als Konstante. Ein Eigenschaftsverweis in einer Benutzerklasse wird jedoch als konstant behandelt. Er wird in einen konstanten Ausdruck der Befehlsstruktur konvertiert und für die Datenquelle ausgeführt.  
  
## <a name="see-also"></a>Siehe auch

- [Ausdrücke in LINQ to Entities-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)

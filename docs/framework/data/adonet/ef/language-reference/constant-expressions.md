---
title: Konstante Ausdrücke
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 163f73a7682d444214caa213751cb35f8f0e8743
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153039"
---
# <a name="constant-expressions"></a>Konstante Ausdrücke

Ein konstanter Ausdruck besteht aus einem konstanten Wert. Konstante Werte werden sofort in konstante Befehlsstrukturausdrücke konvertiert. Es findet keine Übersetzung auf dem Client statt. Dazu gehören Ausdrücke, die einen konstanten Wert zurückgeben. Daher sollte Datenquellenverhalten für alle Ausdrücke erwartet werden, die Konstanten enthalten. Dies kann zu Verhalten führen, das sich von CLR-Verhalten unterscheidet.  
  
 Im folgenden Beispiel wird ein konstanter Ausdruck gezeigt, der auf dem Server ausgewertet wird.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 LINQ to Entities unterstützt nicht die Verwendung einer Benutzerklasse als Konstante. Ein Eigenschaftsverweis in einer Benutzerklasse wird jedoch als konstant behandelt. Er wird in einen konstanten Ausdruck der Befehlsstruktur konvertiert und für die Datenquelle ausgeführt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ausdrücke in LINQ to Entities-Abfragen](expressions-in-linq-to-entities-queries.md)

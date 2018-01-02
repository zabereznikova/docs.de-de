---
title: "Konstante Ausdrücke"
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
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ccc54df7a69db8186c653afb415a5679b65ab50d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="constant-expressions"></a>Konstante Ausdrücke
Ein konstanter Ausdruck besteht aus einem konstanten Wert. Konstante Werte werden sofort in konstante Befehlsstrukturausdrücke konvertiert. Es findet keine Übersetzung auf dem Client statt. Dazu gehören Ausdrücke, die einen konstanten Wert zurückgeben. Daher sollte Datenquellenverhalten für alle Ausdrücke erwartet werden, die Konstanten enthalten. Dies kann zu Verhalten führen, das sich von CLR-Verhalten unterscheidet.  
  
 Im folgenden Beispiel wird ein konstanter Ausdruck gezeigt, der auf dem Server ausgewertet wird.  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] unterstützt die Verwendung von Benutzerklassen als Konstanten nicht. Ein Eigenschaftsverweis in einer Benutzerklasse wird jedoch als konstant behandelt. Er wird in einen konstanten Ausdruck der Befehlsstruktur konvertiert und für die Datenquelle ausgeführt.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke in LINQ to Entities-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)

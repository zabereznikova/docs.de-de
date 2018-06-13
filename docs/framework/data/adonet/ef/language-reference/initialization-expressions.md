---
title: Initialisierungsausdrücke
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 352bda826c3b872d06252e168abfb1129f178bf8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762207"
---
# <a name="initialization-expressions"></a>Initialisierungsausdrücke
Ein Initialisierungsausdruck initialisiert ein neues Objekt. Die meisten Initialisierungsausdrücke werden unterstützt, einschließlich der meisten neuen C# 3.0- und Visual Basic 9.0-Initialisierungsausdrücke. Die folgenden Typen können von einer LINQ to Entities-Abfrage initialisiert und zurückgegeben werden:  
  
-   Eine Auflistung von 0 (null) oder mehreren typisierten Entitätsobjekten oder einer Projektion komplexer Typen, die im konzeptionellen Modell definiert sind.  
  
-   Von [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] unterstütze CLR-Typen.  
  
-   Inlineauflistungen  
  
-   Anonyme Typen  
  
 Im folgenden Beispiel wird die anonyme Typinitialisierung in der Abfrageausdruckssyntax dargestellt:  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 Im folgenden Beispiel methodenbasierter Abfragesyntax wird die anonyme Typinitialisierung veranschaulicht:  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 Die benutzerdefinierte Klasseninitialisierung wird ebenfalls unterstützt. Die Initialisierungsmuster von C# 3.0 und Visual Basic 9.0 werden unterstützt. Dabei wird angenommen, dass die Getter und Setter für die Eigenschaften symmetrisch sind. Das folgende Beispiel von Abfrageausdruckssyntax zeigt die Initialisierung einer benutzerdefinierten Klasse in einer Abfrage:  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 Das folgende Beispiel methodenbasierter Abfragesyntax zeigt die Initialisierung einer benutzerdefinierten Klasse in einer Abfrage:  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke in LINQ to Entities-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)

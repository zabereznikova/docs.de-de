---
title: "Out of string space (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID14"
dev_langs: 
  - "VB"
ms.assetid: 16681c75-a400-422d-9351-c691d3c7614e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Out of string space (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In Visual Basic können Sie sehr umfangreiche Zeichenfolgen verwenden.  Dieser Fehler kann jedoch weiterhin durch Anforderungen anderer Programme und die jeweilige Art der Zeichenfolgenbearbeitung verursacht werden.  
  
### So beheben Sie diesen Fehler  
  
1.  Prüfen Sie, ob ein Ausdruck, bei dem während der Auswertung temporäre Zeichen erstellt werden, den Fehler verursacht.  
  
2.  Entfernen Sie alle nicht benötigten Anwendungen aus dem Arbeitsspeicher, um Speicher freizugeben.  
  
## Siehe auch  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [String Manipulation Summary](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
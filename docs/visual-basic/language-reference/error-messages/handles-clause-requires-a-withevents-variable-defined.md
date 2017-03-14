---
title: "Handles clause requires a WithEvents variable defined in the containing type or one of its base types | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30506"
  - "bc30506"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30506"
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Handles clause requires a WithEvents variable defined in the containing type or one of its base types
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie haben in der `Handles`\-Klausel keine `WithEvents`\-Variable angegeben.  Verwenden Sie das `Handles`\-Schlüsselwort am Ende einer Prozedurdeklaration, damit es Ereignisse behandelt, die durch eine mit dem `WithEvents`\-Schlüsselwort deklarierte Objektvariable ausgelöst werden.  
  
 **Fehler\-ID:** BC30506  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie die erforderliche `WithEvents`\-Variable bereit.  
  
## Siehe auch  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
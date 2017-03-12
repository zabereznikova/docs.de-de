---
title: "&#39;Class&#39; statement must end with a matching &#39;End Class&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30481"
  - "bc30481"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30481"
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &#39;Class&#39; statement must end with a matching &#39;End Class&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

`Class` wird zum Einleiten eines `Class`\-Blocks verwendet und kann daher nur am Anfang des Blocks stehen. Der Block muss mit einer passenden `End Class`\-Anweisung beendet werden.  Entweder es existiert eine weitere `Class`\-Anweisung, oder der `Class`\-Block wurde nicht durch `End Class` beendet.  
  
 **Fehler\-ID:** BC30481  
  
### So beheben Sie diesen Fehler  
  
-   Suchen und entfernen Sie die nicht erforderliche `Class`\-Anweisung.  
  
-   Beenden Sie den `Class`\-Block mit einer entsprechenden `End Class`\-Anweisung.  
  
## Siehe auch  
 [End \<keyword\> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)
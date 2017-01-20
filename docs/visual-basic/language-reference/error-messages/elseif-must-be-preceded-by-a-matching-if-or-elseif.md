---
title: "&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39; | Microsoft Docs"
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
  - "vbc30014"
  - "bc30014"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30014"
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`#ElseIf` ist eine Direktive für die bedingte Kompilierung.  Einer `#ElseIf`\-Klausel muss eine entsprechende `#If`\-Klausel oder `#ElseIf`\-Klausel vorangehen.  
  
 **Fehler\-ID:** BC30014  
  
### So beheben Sie diesen Fehler  
  
1.  Eine vorausgehende `#If` \- oder `#ElseIf`\-Klausel darf nicht durch einen dazwischen liegenden Block zur bedingten Kompilierung oder eine falsch platzierte `#End If`\-Klausel von dieser `#ElseIf`\-Klausel getrennt sein.  
  
2.  Wenn der `#ElseIf`\-Klausel eine `#Else`\-Direktive vorangeht, entfernen Sie entweder die `#Else`\-Direktive oder ändern Sie sie in eine `#ElseIf`\-Klausel.  
  
3.  Falls der Code ansonsten in Ordnung ist, fügen Sie eine `#If`\-Direktive am Anfang des Blocks für die bedingte Kompilierung ein.  
  
## Siehe auch  
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
---
title: "Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times | Microsoft Docs"
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
  - "bc30663"
  - "vbc30663"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30663"
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Das Attribut kann nur einmal angewendet werden.  Durch das `AttributeUsage`\-Attribut wird bestimmt, ob ein Attribut mehr als einmal angewendet werden kann.  
  
 **Fehler\-ID:** BC30663  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass das Attribut nur einmal angewendet wird.  
  
2.  Wenn Sie selbst entwickelte, benutzerdefinierte Attribute verwenden, sollten Sie erwägen, deren `AttributeUsage`\-Attribut so zu ändern, dass die Mehrfachverwendung von Attributen zulässig ist. Beispiel:  
  
    ```  
    <AttributeUsage(AllowMultiple := True)>  
    ```  
  
## Siehe auch  
 <xref:System.AttributeUsageAttribute>   
 [Erstellen benutzerdefinierter Attribute](../Topic/Creating%20Custom%20Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [AttributeUsage](../Topic/AttributeUsage%20\(C%23%20and%20Visual%20Basic\).md)
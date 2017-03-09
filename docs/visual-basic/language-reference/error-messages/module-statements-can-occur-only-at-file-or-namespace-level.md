---
title: "&#39;Module&#39; statements can occur only at file or namespace level | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30617"
  - "vbc30617"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30617"
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# &#39;Module&#39; statements can occur only at file or namespace level
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

`Module`\-Anweisungen müssen am Anfang der Quelldatei direkt hinter den Anweisungen `Option` und `Imports` und hinter globalen Attributen und Namespacedeklarationen, jedoch vor allen anderen Deklarationen stehen.  
  
 **Fehler\-ID:** BC30617  
  
### So beheben Sie diesen Fehler  
  
-   Verschieben Sie die `Module`\-Anweisung an den Anfang der Namespacedeklaration oder der Quelldatei.  
  
## Siehe auch  
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)
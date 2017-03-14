---
title: "Property let procedure not defined and property get procedure did not return an object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID451"
dev_langs: 
  - "VB"
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Property let procedure not defined and property get procedure did not return an object
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bestimmte Eigenschaften, Methoden und Operationen sind nur auf `Collection`\-Objekte anwendbar.  Sie haben eine Operation oder Eigenschaft angegeben, die ausschließlich auf Auflistungen angewendet wird, das Objekt stellt jedoch keine Auflistung dar.  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Schreibweise des Objekt\- oder Eigenschaftennamens, oder stellen Sie sicher, dass es sich bei dem Objekt um ein `Collection`\-Objekt handelt.  
  
2.  Stellen Sie anhand der `Add`\-Methode, mit der das Objekt der Auflistung hinzugefügt wurde, sicher, dass die Syntax stimmt und alle Bezeichner richtig geschrieben wurden.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Collection>
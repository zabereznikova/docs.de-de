---
title: "Instance Encoding Option | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Instance Encoding Option
Mit der **Instance Encoding Option**\-Eigenschaft des SQL\-Workflowinstanzspeichers können Sie angeben, ob der SQL\-Persistenzanbieter die Zustandsinformationen zur Workflowinstanz mithilfe des GZip\-Algorithmus komprimieren soll, bevor die Informationen in die Persistenzdatenbank gespeichert werden.Die zulässigen Werte für diese Eigenschaft sind: GZIP und None.Der Standardwert ist None.In der folgenden Liste werden diese Optionen beschrieben.  
  
1.  **GZip**.Der Persistenzanbieter codiert die Zustandsinformationen mithilfe des GZip\-Algorithmus, bevor die Zustandsinformationen in der Persistenzdatenbank gespeichert werden.  
  
2.  **Kein**.Der Persistenzanbieter codiert die Zustandsinformationen nicht, bevor die Informationen in der Persistenzdatenbank gespeichert werden.  
  
 Durch die Codierung der Zustandsinformationen der Workflowinstanz mithilfe von GZip wird in der SQL\-Datenbank weniger Speicher und Netzwerkkapazität belegt, wenn sich die Datenbank auf einem anderen Computer im Netzwerk befindet als der Host des Workflowdiensts.Allgemein empfiehlt es sich, die **Instance Encoding Option**\-Eigenschaft auf **None** festzulegen, wenn der Workflowinstanzzustand klein ist.
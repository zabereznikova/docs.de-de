---
title: "&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly | Microsoft Docs"
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
  - "bc32022"
  - "vbc32022"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32022"
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

'\<`eventname`\>' ist ein Ereignis und kann daher nicht direkt aufgerufen werden.  Verwenden Sie eine `RaiseEvent`\-Anweisung, um ein Ereignis auszulösen.  
  
 Ein Prozeduraufruf gibt ein Ereignis für den Prozedurnamen an.  Ein Ereignishandler ist eine Prozedur, das Ereignis selbst ist jedoch eine Signalisierungseinrichtung, die ausgelöst und verarbeitet werden muss.  
  
 **Fehler\-ID:** BC32022  
  
### So beheben Sie diesen Fehler  
  
1.  Verwenden Sie eine `RaiseEvent`\-Anweisung zum Signalisieren eines Ereignisses und Aufrufen der Prozedur oder Prozeduren, die es verarbeiten.  
  
## Siehe auch  
 [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
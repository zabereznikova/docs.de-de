---
title: "How to: Declare Custom Events To Avoid Blocking (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaring events, custom"
  - "events [Visual Basic], custom"
  - "custom events"
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Declare Custom Events To Avoid Blocking (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn bestimmte Bedingungen vorliegen, darf ein Ereignishandler nachfolgende Ereignishandler nicht blockieren.  Benutzerdefinierte Ereignisse ermöglichen den asynchronen Aufruf der Ereignishandler durch das betreffende Ereignis.  
  
 Standardmäßig ist das Feld des Sicherungsspeichers für eine Ereignisdeklaration ein Multicastdelegat, in dem alle Ereignishandler nacheinander zusammengefasst werden.  Dies bedeutet, dass ein Handler, dessen Ausführung eine lange Zeitspanne erfordert, die anderen Handler blockiert, bis seine Ausführung beendet wurde.  \(Gut konzipierte Ereignishandler sollten niemals langwierige oder potenziell blockierende Operationen ausführen.\)  
  
 Statt der von Visual Basic bereitgestellten Standardimplementierung von Ereignissen können Sie ein benutzerdefiniertes Ereignis verwenden, um die Ereignishandler asynchron auszuführen.  
  
## Beispiel  
 In diesem Beispiel fügt der `AddHandler`\-Accessor einer im `EventHandlerList`\-Feld gespeicherten <xref:System.Collections.ArrayList> den Delegaten für jeden Handler des `Click`\-Ereignisses zu.  
  
 Wenn Code das `Click`\-Ereignis auslöst, ruft der `RaiseEvent`\-Accessor mit der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>\-Methode alle Ereignishandlerdelegaten asynchron auf.  Diese Methode ruft jeden Handler in einem Arbeitsthread auf und wird sofort beendet, sodass Handler sich nicht gegenseitig blockieren können.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/VbVbalrEvents/Class1.vb#27)]  
  
## Siehe auch  
 <xref:System.Collections.ArrayList>   
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>   
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [How to: Declare Custom Events To Conserve Memory](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
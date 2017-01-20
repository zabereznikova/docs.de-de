---
title: "RemoveHandler Statement | Microsoft Docs"
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
  - "vb.RemoveHandlerMethod"
  - "vb.RemoveHandler"
  - "RemoveHandler"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "RemoveHandler keyword"
  - "RemoveHandler statement"
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# RemoveHandler Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Hebt die Verknüpfung zwischen einem Ereignis und einem Ereignishandler auf.  
  
## Syntax  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`event`|Der Name des behandelten Ereignisses.|  
|`eventhandler`|Der Name der Prozedur, die das Ereignis derzeit behandelt.|  
  
## Hinweise  
 Mit den Anweisungen `AddHandler` und `RemoveHandler` können Sie die Ereignisbehandlung für ein bestimmtes Ereignis an einer beliebigen Stelle in der Programmausführung starten und anhalten.  
  
> [!NOTE]
>  Für benutzerdefinierte Ereignisse ruft die `RemoveHandler`\-Anweisung den `RemoveHandler`\-Accessor des Ereignisses auf.  Weitere Informationen über benutzerdefinierte Ereignisse finden Sie unter [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Beispiel  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/VbVbalrEvents/Class1.vb#17)]  
  
## Siehe auch  
 [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)
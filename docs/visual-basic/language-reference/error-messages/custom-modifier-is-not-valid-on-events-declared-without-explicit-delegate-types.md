---
title: "&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31122"
  - "bc31122"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31122"
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &#39;Custom&#39; modifier is not valid on events declared without explicit delegate types
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Im Unterschied zu Ereignissen, die nicht benutzerdefiniert sind, erfordert eine `Custom Event`\-Deklaration eine `As`\-Klausel nach dem Ereignisnamen, die den Delegattyp für das Ereignis explizit angibt.  
  
 Nicht benutzerdefinierte Ereignisse können entweder mit einer `As`\-Klausel und einem expliziten Delegattyp oder mit einer Parameterliste direkt nach dem Ereignisnamen definiert werden.  
  
 **Fehler\-ID:** BC31122  
  
### So beheben Sie diesen Fehler  
  
1.  Definieren Sie einen Delegaten mit der gleichen Parameterliste wie das benutzerdefinierte Ereignis.  
  
     Wenn z. B. das `Custom Event` mit `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` definiert wurde, lautet der entsprechende Delegat wie folgt.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/custom-modifier-is-not-v_1.vb)]  
  
2.  Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses durch eine `As`\-Klausel, die den Delegattyp angibt.  
  
     In der Fortsetzung des Beispiels wird die `Custom Event`\-Deklaration wie folgt umgeschrieben.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/custom-modifier-is-not-v_2.vb)]  
  
## Beispiel  
 In diesem Beispiel wird ein `Custom Event` deklariert und die erforderliche `As`\-Klausel mit einem Delegattyp angegeben.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/custom-modifier-is-not-v_3.vb)]  
  
## Siehe auch  
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)
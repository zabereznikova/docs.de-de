---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen zu vermeiden (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34b222bdbfdae0673b7150c220ca477b7e286dda
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)
Es gibt mehrere Umstände es ist wichtig, einen Ereignishandler nachfolgende Ereignishandler nicht blockiert. Benutzerdefinierte Ereignisse ermöglichen den zugehörigen Ereignishandler asynchron aufrufen.  
  
 Standardmäßig ist das Feld Sicherungsspeichers für eine Ereignisdeklaration Multicastdelegaten, der nacheinander alle Ereignishandler kombiniert. Dies bedeutet, dass wenn ein Ereignishandler eine lange Zeit in Anspruch nimmt, die anderen Handler blockiert, bis er abgeschlossen ist. (Gut konzipierte Ereignishandler sollten niemals langwierige oder potenziell blockierende Operationen ausführen.)  
  
 Statt die standardmäßige Implementierung der Ereignisse, die Visual Basic bietet, können Sie ein benutzerdefiniertes Ereignis, der die Ereignishandler asynchron ausgeführt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel die `AddHandler` Accessor fügt den Delegaten für jeden Handler des der `Click` Ereignis ein <xref:System.Collections.ArrayList>gespeichert, der `EventHandlerList` Feld.</xref:System.Collections.ArrayList>  
  
 Wenn code löst die `Click` -Ereignis, das `RaiseEvent` Accessor Ruft alle Ereignishandlerdelegaten, die asynchron mit der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>Methode.</xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> Diese Methode ruft jeden Handler in einem Arbeitsthread und wird sofort beendet, sodass Handler gegenseitig blockieren können.  
  
 [!code-vb[VbVbalrEvents&#27;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.ArrayList></xref:System.Collections.ArrayList>   
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>   
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)

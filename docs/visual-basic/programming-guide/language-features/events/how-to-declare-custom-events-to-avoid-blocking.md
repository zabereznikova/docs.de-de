---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a36c855efb67752674615a61f2fa701974ce5f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)
Es gibt mehrere Umstände es ist wichtig, einem Ereignishandler nicht nachfolgenden Ereignishandlern blockiert. Benutzerdefinierte Ereignisse ermöglichen das Ereignis, dessen Ereignishandler asynchron aufzurufen.  
  
 Standardmäßig wird der Sicherungsspeicher Feld für eine Ereignisdeklaration ein multicast-Delegat, der seriell alle Ereignishandler kombiniert. Dies bedeutet, dass wenn ein Ereignishandler eine lange Zeit in Anspruch nimmt, er die anderen Handler blockiert, bis er abgeschlossen wurde. (Gut konzipierte Ereignishandler sollten niemals langwierige oder potenziell blockierende Vorgänge ausführen.)  
  
 Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet zu verwenden, können Sie ein benutzerdefiniertes Ereignis, der die Ereignishandler asynchron ausgeführt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel die `AddHandler` Accessor fügt der Delegat für jeden Handler des der `Click` Ereignis, um eine <xref:System.Collections.ArrayList> gespeichert, der `EventHandlerList` Feld.  
  
 Wenn code löst die `Click` Ereignis, das `RaiseEvent` Accessor Ruft alle Ereignishandlerdelegaten, die asynchron mit der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> Methode. Diese Methode ruft jeden Handler in einem Arbeitsthread und sofort zurückgegeben werden, sodass Handler untereinander blockieren können.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)

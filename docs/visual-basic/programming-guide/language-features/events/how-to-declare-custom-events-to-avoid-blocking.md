---
title: 'Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen (Visual Basic) eine Blockierung zu vermeiden'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: fe8775a15ce5149cf307879ab31e2ec0a8ba8f47
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965175"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen (Visual Basic) eine Blockierung zu vermeiden
Es gibt verschiedenen Fällen bei der es ist wichtig, einem Ereignishandler nicht blockieren nachfolgenden Ereignishandlern. Benutzerdefinierte Ereignisse ermöglichen das Ereignis, dessen Ereignishandler asynchron aufzurufen.  
  
 Standardmäßig ist das Sicherungsspeicher Feld für eine Ereignisdeklaration ein multicast-Delegat, der seriell auf alle Ereignishandler kombiniert. Dies bedeutet, dass wenn ein Handler eine lange Zeit in Anspruch nimmt, es anderer Handler blockiert, bis es abgeschlossen ist. (Gut konzipierte Ereignishandler sollte nie langwierige oder potenziell blockierende Vorgänge ausführen.)  
  
 Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet, können Sie ein benutzerdefiniertes Ereignis aus, der die Ereignishandler asynchron ausgeführt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel die `AddHandler` Accessor fügt der Delegat für jeden Handler des der `Click` Ereignis, um eine <xref:System.Collections.ArrayList> gespeichert, der `EventHandlerList` Feld.  
  
 Wenn der code löst die `Click` -Ereignis, das `RaiseEvent` Accessor Ruft alle Ereignishandlerdelegaten, die asynchron mit der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> Methode. Diese Methode ruft jede Handler auf einem Arbeitsthread und gibt sofort zurück, sodass Handler gegenseitig blockieren können nicht.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)

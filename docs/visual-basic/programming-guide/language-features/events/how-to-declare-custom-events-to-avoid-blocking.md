---
title: 'Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen (Visual Basic) eine Blockierung zu vermeiden'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: e1fed68f4abffb0e20230f55b0ddeffc63f7c78d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691540"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen (Visual Basic) eine Blockierung zu vermeiden
Es gibt verschiedenen Fällen bei der es ist wichtig, einem Ereignishandler nicht blockieren nachfolgenden Ereignishandlern. Benutzerdefinierte Ereignisse ermöglichen das Ereignis, dessen Ereignishandler asynchron aufzurufen.  
  
 Standardmäßig ist das Sicherungsspeicher Feld für eine Ereignisdeklaration ein multicast-Delegat, der seriell auf alle Ereignishandler kombiniert. Dies bedeutet, dass wenn ein Handler eine lange Zeit in Anspruch nimmt, es anderer Handler blockiert, bis es abgeschlossen ist. (Gut konzipierte Ereignishandler sollte nie langwierige oder potenziell blockierende Vorgänge ausführen.)  
  
 Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet, können Sie ein benutzerdefiniertes Ereignis aus, der die Ereignishandler asynchron ausgeführt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel die `AddHandler` Accessor fügt der Delegat für jeden Handler des der `Click` Ereignis, um eine <xref:System.Collections.ArrayList> gespeichert, der `EventHandlerList` Feld.  
  
 Wenn der code löst die `Click` -Ereignis, das `RaiseEvent` Accessor Ruft alle Ereignishandlerdelegaten, die asynchron mit der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> Methode. Diese Methode ruft jede Handler auf einem Arbeitsthread und gibt sofort zurück, sodass Handler gegenseitig blockieren können nicht.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)

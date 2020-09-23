---
title: 'Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: a9350470836652f65532068402c78375b4c5495c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077097"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)

Es gibt mehrere Situationen, in denen es wichtig ist, dass ein Ereignishandler nachfolgende Ereignishandler nicht blockiert. Benutzerdefinierte Ereignisse ermöglichen es dem Ereignis, seine Ereignishandler asynchron aufzurufen.  
  
 Standardmäßig handelt es sich bei dem Feld für den Sicherungs Speicher einer Ereignis Deklaration um einen Multicast Delegat, der alle Ereignishandler serialisiert. Dies bedeutet, dass, wenn ein Handler lange Zeit benötigt, die anderen Handler blockiert werden, bis der Vorgang abgeschlossen ist. (Wohl verhaltene Ereignishandler sollten niemals lange oder potenziell blockierende Vorgänge ausführen.)  
  
 Anstatt die Standard Implementierung von Ereignissen zu verwenden, die Visual Basic bereitstellt, können Sie ein benutzerdefiniertes Ereignis verwenden, um die Ereignishandler asynchron auszuführen.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel fügt der- `AddHandler` Accessor den-Delegaten für jeden `Click` Ereignishandler zu einem <xref:System.Collections.ArrayList> im-Feld gespeicherten hinzu `EventHandlerList` .  
  
 Wenn Code das- `Click` Ereignis auslöst, `RaiseEvent` ruft der-Accessor alle Ereignishandlerdelegaten mithilfe der-Methode asynchron auf <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> . Diese Methode ruft jeden Handler auf einem Arbeits Thread auf und gibt sofort zurück, sodass Handler einander nicht blockieren können.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Ereignisse](index.md)
- [How to: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher](how-to-declare-custom-events-to-conserve-memory.md)

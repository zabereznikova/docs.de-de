---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 8d73d9c4590afb33e7176f647069cafcb3a9d7d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345149"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)
Es gibt mehrere Situationen, in denen es wichtig ist, dass ein Ereignishandler nachfolgende Ereignishandler nicht blockiert. Benutzerdefinierte Ereignisse ermöglichen es dem Ereignis, seine Ereignishandler asynchron aufzurufen.  
  
 Standardmäßig handelt es sich bei dem Feld für den Sicherungs Speicher einer Ereignis Deklaration um einen Multicast Delegat, der alle Ereignishandler serialisiert. Dies bedeutet, dass, wenn ein Handler lange Zeit benötigt, die anderen Handler blockiert werden, bis der Vorgang abgeschlossen ist. (Wohl verhaltene Ereignishandler sollten niemals lange oder potenziell blockierende Vorgänge ausführen.)  
  
 Anstatt die Standard Implementierung von Ereignissen zu verwenden, die Visual Basic bereitstellt, können Sie ein benutzerdefiniertes Ereignis verwenden, um die Ereignishandler asynchron auszuführen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel fügt der `AddHandler` Accessor den Delegaten für jeden Handler des `Click` Ereignisses einem <xref:System.Collections.ArrayList> hinzu, der im `EventHandlerList` Feld gespeichert ist.  
  
 Wenn Code das `Click`-Ereignis auslöst, ruft der `RaiseEvent`-Accessor alle Ereignishandlerdelegaten mithilfe der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>-Methode asynchron auf. Diese Methode ruft jeden Handler auf einem Arbeits Thread auf und gibt sofort zurück, sodass Handler einander nicht blockieren können.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)

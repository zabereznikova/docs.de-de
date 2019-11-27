---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3cc2d3ea57f1a8daf704c2c929baf3f2acf78c17
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345131"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)
Es gibt verschiedene Situationen, in denen es wichtig ist, dass eine Anwendung die Speicherauslastung niedrig hält. Benutzerdefinierte Ereignisse ermöglichen es der Anwendung, Arbeitsspeicher nur für die Ereignisse zu verwenden, die Sie verarbeitet.  
  
 Wenn eine Klasse ein Ereignis deklariert, ordnet der Compiler standardmäßig Speicher für ein Feld zu, um die Ereignis Informationen zu speichern. Wenn eine Klasse über viele nicht verwendete Ereignisse verfügt, nehmen Sie unnötigerweise Speicherplatz in Anspruch.  
  
 Anstatt die Standard Implementierung von Ereignissen zu verwenden, die Visual Basic bereitstellt, können Sie benutzerdefinierte Ereignisse verwenden, um die Speicherauslastung sorgfältiger zu verwalten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verwendet die-Klasse eine Instanz der <xref:System.ComponentModel.EventHandlerList>-Klasse, die im `Events` Feld gespeichert ist, um Informationen über die verwendeten Ereignisse zu speichern. Die <xref:System.ComponentModel.EventHandlerList>-Klasse ist eine optimierte Listen Klasse, die Delegaten enthalten soll.  
  
 Alle Ereignisse in der-Klasse verwenden das `Events` Feld, um nachzuverfolgen, welche Methoden die einzelnen Ereignisse verarbeiten.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.EventHandlerList>
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)

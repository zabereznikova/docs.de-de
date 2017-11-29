---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)'
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eec9a2fc687f481ab40313e35cbde81c25b81ae8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)
Es gibt mehrere Situationen können, ist es wichtig, dass eine Anwendung die speicherauslastung gering halten. Benutzerdefinierte Ereignisse können die Anwendung Speicher nur für die Ereignisse zu nutzen, die ihn verarbeitet.  
  
 Wenn eine Klasse ein Ereignis deklariert, reserviert der Compiler standardmäßig Speicher für ein Feld, um die Ereignisinformationen zu speichern. Wenn eine Klasse viele nicht verwendete Ereignisse aufweist, beanspruchen diese unnötigerweise Speicher.  
  
 Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet können Sie benutzerdefinierte Ereignisse verwenden, um die Auslastung des Speichers mehr sorgfältig verwalten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verwendet die Klasse eine Instanz von der <xref:System.ComponentModel.EventHandlerList> Klasse, die gespeichert, der `Events` Feld zum Speichern von Informationen zu den Ereignissen verwendet. Die <xref:System.ComponentModel.EventHandlerList> -Klasse ist eine optimierte Listenklasse zum Speichern von Delegaten.  
  
 Alle Ereignisse in der Klasse verwenden die `Events` Feld zum Nachverfolgen von welche Methoden jedes Ereignis behandeln.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.EventHandlerList>  
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)

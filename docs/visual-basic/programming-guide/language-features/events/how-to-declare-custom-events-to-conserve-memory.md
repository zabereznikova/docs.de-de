---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 4f8ce32a3b4da411a73010119283ce9661b82a6c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)
Es gibt mehrere Situationen, wenn es wichtig ist, dass eine Anwendung die Speicherverwendung gering halten. Benutzerdefinierte Ereignisse ermöglichen die Anwendung Speicher nur für die Ereignisse verwenden, die sie behandelt.  
  
 Wenn eine Klasse ein Ereignis deklariert, reserviert der Compiler standardmäßig Speicher für ein Feld zum Speichern von Informationen für das Ereignis. Wenn eine Klasse viele nicht verwendete Ereignisse aufweist, beanspruchen diese unnötigerweise Speicher.  
  
 Statt die standardmäßige Implementierung der Ereignisse, die Visual Basic bietet, können Sie benutzerdefinierte Ereignisse die Speicherverwendung sorgfältiger verwalten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verwendet die Klasse eine Instanz der <xref:System.ComponentModel.EventHandlerList>Klasse, die in gespeicherten der `Events` Feld zum Speichern von Informationen zu den Ereignissen verwendet.</xref:System.ComponentModel.EventHandlerList> Die <xref:System.ComponentModel.EventHandlerList>-Klasse ist eine optimierte Listenklasse zum Speichern von Delegaten.</xref:System.ComponentModel.EventHandlerList>  
  
 Alle Ereignisse in der Klasse verwenden das `Events` Feld zum Nachverfolgen von welche Methoden jedes Ereignis behandeln.  
  
 [!code-vb[VbVbalrEvents&#22;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.EventHandlerList></xref:System.ComponentModel.EventHandlerList>   
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)

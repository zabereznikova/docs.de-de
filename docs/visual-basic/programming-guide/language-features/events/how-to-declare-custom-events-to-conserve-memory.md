---
title: 'Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: e4132f51f4dd85ad964042d05f7c5bc0a2e6e3cd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826625"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher (Visual Basic)
Es gibt verschiedenen Fällen beim ist es wichtig, dass eine Anwendung die arbeitsspeicherauslastung gering halten. Benutzerdefinierte Ereignisse ermöglichen die Anwendung zur Verwendung von Speicher nur für die Ereignisse, die ihn verarbeitet.  
  
 Wenn eine Klasse ein Ereignis deklariert, weist der Compiler standardmäßig Speicher für ein Feld aus, um die Ereignisinformationen zu speichern. Verfügt eine Klasse über viele nicht verwendeten Ereignisse, beanspruchen diese unnötigerweise Arbeitsspeicher.  
  
 Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet, können Sie benutzerdefinierte Ereignisse genau die speicherauslastung zu verwalten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verwendet die Klasse eine Instanz der dem <xref:System.ComponentModel.EventHandlerList> Klasse, die gespeichert, der `Events` Feld zum Speichern von Informationen zu den Ereignissen verwendet. Die <xref:System.ComponentModel.EventHandlerList> -Klasse ist eine optimierte Listenklasse zum Speichern von Delegaten.  
  
 Alle Ereignisse in der Klasse verwenden die `Events` Feld zum Nachverfolgen jedes Ereignis welche Methoden behandeln.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.EventHandlerList>
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen, um die Blockierung zu vermeiden](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)

---
title: "Handles Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Handles"
  - "vb.Handles"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Handles keyword"
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Handles Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Deklariert, dass eine Prozedur ein angegebenes Ereignis behandelt.  
  
## Syntax  
  
```  
  
proceduredeclaration Handles eventlist  
```  
  
## Teile  
 `proceduredeclaration`  
 Die `Sub`\-Prozedurdeklaration für die Prozedur, die das Ereignis verarbeitet.  
  
 `eventlist`  
 Listet die Ereignisse für `proceduredeclaration` für die Verarbeitung auf, durch Kommas getrennt.  Die Ereignisse müssen durch die Basisklasse für die aktuelle Klasse oder durch ein mithilfe des Schlüsselworts `WithEvents` deklariertes Objekt ausgelöst werden.  
  
## Hinweise  
 Verwenden Sie das `Handles`\-Schlüsselwort am Ende der Prozedurdeklaration, damit sie Ereignisse verarbeitet, die durch eine mithilfe des Schlüsselworts `WithEvents` deklarierte Objektvariable ausgelöst wurden.  Das Schlüsselwort `Handles` kann zudem in einer abgeleiteten Klasse verwendet werden, um Ereignisse aus einer Basisklasse zu verarbeiten.  
  
 Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede.  Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet.   Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen.  Weitere Informationen finden Sie unter [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md).  
  
 Für benutzerdefinierte Ereignisse ruft die Anwendung den `AddHandler`\-Accessor des Ereignisses auf, wenn die Prozedur als ein Ereignishandler hinzugefügt wird.  Weitere Informationen über benutzerdefinierte Ereignisse finden Sie unter [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Beispiel  
 [!code-vb[VbVbalrEvents#2](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#2)]  
  
 Im folgenden Beispiel wird gezeigt, wie eine abgeleitete Klasse die `Handles`\-Anweisung zum Verarbeiten eines Ereignisses aus einer Basisklasse verwenden kann.  
  
 [!code-vb[VbVbalrEvents#3](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#3)]  
  
## Beispiel  
 Das folgende Beispiel enthält zwei Tastenereignishandler für ein Projekt für eine **WPF\-Anwendung**.  
  
 [!code-vb[VbVbalrEvents#41](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/class3.vb#41)]  
  
## Beispiel  
 Das folgende Beispiel entspricht dem vorherigen Beispiel.  Die `eventlist` in der `Handles`\-Klausel enthält die Ereignisse für beide Tasten.  
  
 [!code-vb[VbVbalrEvents#42](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/class3.vb#42)]  
  
## Siehe auch  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)
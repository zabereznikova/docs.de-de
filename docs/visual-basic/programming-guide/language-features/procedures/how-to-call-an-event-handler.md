---
title: "How to: Call an Event Handler in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, procedures"
  - "event handlers, calling"
  - "event handlers"
  - "procedures, event handlers"
  - "procedures, calling"
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Call an Event Handler in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*Ereignisse* sind Aktionen oder Vorkommnisse, z. B. ein Mausklick oder das Überschreiten eines Kreditrahmens, die von einem Objekt erkannt werden und für die Sie Code schreiben können, der darauf reagiert.  Ein *Ereignishandler* ist der Code, der auf diese Ereignisse reagiert.  
  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ist ein Ereignishandler eine `Sub`\-Prozedur.  Sie rufen Ereignishandler aber normalerweise nicht auf die gleiche Weise wie andere `Sub`\-Prozeduren auf.  Stattdessen identifizieren Sie die Prozedur als Handler für das Ereignis.  Sie können dies entweder mit einer [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md)\-Klausel und einer [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)\-Variablen oder mit einer [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) tun.  Standardmäßig werden in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Ereignishandler mit einer `Handles`\-Klausel deklariert.  Auf diese Weise werden Ereignishandler von den Designern geschrieben, wenn Sie in der integrierten Entwicklungsumgebung \(IDE\) programmieren.  Die `AddHandler`\-Anweisung eignet sich dazu, Ereignisse dynamisch zur Laufzeit auszulösen.  
  
 Wenn das Ereignis eintritt, ruft [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] automatisch die Ereignishandlerprozedur auf.  Jeglicher Code, der Zugriff auf das Ereignis hat, kann durch die Ausführung einer [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md) das Ereignis auslösen.  
  
 Sie können einem Ereignis mehrere Ereignishandler zuordnen.  In einigen Fällen können Sie die Zuordnung zwischen einem Handler und einem Ereignis aufheben.  Weitere Informationen hierzu finden Sie unter [Events](../../../../visual-basic/programming-guide/language-features/events/events.md).  
  
### So rufen Sie mit Handles und WithEvents einen Ereignishandler auf  
  
1.  Stellen Sie sicher, dass das Ereignis mit einer [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md) deklariert wird.  
  
2.  Deklarieren Sie mit dem [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)\-Schlüsselwort eine Objektvariable auf Modul\- oder Klassenebene.  Die `As`\-Klausel für diese Variable muss die Klasse angeben, die das Ereignis auslöst.  
  
3.  Fügen Sie der `Sub`\-Prozedur, die als Ereignishandler fungiert, eine [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md)\-Klausel ein, die die `WithEvents`\-Variable und den Ereignisnamen enthält.  
  
4.  Wenn das Ereignis eintritt, ruft [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] automatisch die `Sub`\-Prozedur auf.  Im Code kann eine `RaiseEvent`\-Anweisung zum Auslösen des Ereignisses verwendet werden.  
  
     Im folgenden Beispiel werden ein Ereignis und eine `WithEvents`\-Variable definiert, die auf die Klasse verweist, welche das Ereignis auslöst.  In der `Sub`\-Prozedur, die als Ereignishandler fungiert, wird eine `Handles`\-Klausel verwendet, um die Klasse und das Ereignis anzugeben, die verarbeitet werden.  
  
     [!code-vb[VbVbcnProcedures#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-call-an-event-handle_1.vb)]  
  
### So rufen Sie mit AddHandler einen Ereignishandler auf  
  
1.  Stellen Sie sicher, dass das Ereignis mit einer `Event`\-Anweisung deklariert wird.  
  
2.  Führen Sie eine [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) aus, um die ereignisbehandelnde `Sub`\-Prozedur dynamisch dem Ereignis zuzuordnen.  
  
3.  Wenn das Ereignis eintritt, ruft [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] automatisch die `Sub`\-Prozedur auf.  Im Code kann eine `RaiseEvent`\-Anweisung zum Auslösen des Ereignisses verwendet werden.  
  
     Im folgenden Beispiel wird eine `Sub`\-Prozedur definiert, die das <xref:System.Windows.Forms.Form.Closing>\-Ereignis eines Formulars behandelt.  Dann wird die `catchClose`\-Prozedur mithilfe der [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) als Ereignishandler für <xref:System.Windows.Forms.Form.Closing> zugeordnet.  
  
     [!code-vb[VbVbcnProcedures#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-call-an-event-handle_2.vb)]  
  
     Durch die Ausführung der [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md) kann die Zuordnung zwischen einem Ereignishandler und einem Ereignis aufgehoben werden.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [How to: Create a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [How to: Call a Procedure that Does Not Return a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)
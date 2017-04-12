---
title: 'Gewusst wie: Aufrufen von einem Ereignishandler in Visual Basic | Microsoft-Dokumentation'
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
- Visual Basic code, procedures
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: c5b300feca3415d1283d24179795a4ae92c61e52
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Gewusst wie: Aufrufen eines Ereignishandlers in Visual Basic
Ein *Ereignis* ist eine Aktion oder ein vorkommen, z. B. ein Mausklick klicken oder ein Kreditlimit überschritten –, durch eine Anwendungskomponente, und für die Sie Code schreiben können, reagieren erkannt. Ein *-Ereignishandler* ist der Code, der auf ein Ereignis reagieren.  
  
 Ein Ereignishandler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ist ein `Sub` Verfahren. Allerdings Sie normalerweise rufen ihn nicht die gleiche Weise wie andere `Sub` Verfahren. Stattdessen geben Sie die Prozedur als Handler für das Ereignis. Hierzu können Sie entweder mit einer [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) -Klausel und eine [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) Variable, oder mit einer [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Mithilfe einer `Handles` -Klausel ist die Standardmethode, deklarieren einen Ereignishandler in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Dies ist die Möglichkeit, die die Ereignishandler von Entwicklern geschrieben werden, wenn Sie in der integrierten Entwicklungsumgebung (IDE) programmieren. Die `AddHandler` -Anweisung eignet sich zum Auslösen von Ereignissen dynamisch zur Laufzeit.  
  
 Wenn das Ereignis eintritt, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ruft automatisch die Ereignis-Handler-Prozedur. Jeglicher Code, der Zugriff auf das Ereignis kann dazu führen, dass es durch die Ausführung einer [RaiseEvent-Anweisung](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Sie können das gleiche Ereignis mehrere Ereignishandler zuordnen. In einigen Fällen können Sie einen Ereignishandler aus einem Ereignis zu trennen. Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Mit Handles und WithEvents einen Ereignishandler aufrufen  
  
1.  Stellen Sie sicher, dass das Ereignis mit deklariert eine [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Deklarieren Sie eine Objektvariable auf Modul- oder Ebene, mit der [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) Schlüsselwort. Die `As` -Klausel für diese Variable muss die Klasse angeben, die das Ereignis auslöst.  
  
3.  In der Deklaration der Ereignisbehandlung `Sub` Verfahren Hinzufügen einer [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) -Klausel, in der `WithEvents` Variable und der Name des Ereignisses.  
  
4.  Wenn das Ereignis eintritt, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ruft automatisch die `Sub` Verfahren. Code können Sie eine `RaiseEvent` Anweisung, damit das Ereignis auftreten.  
  
     Im folgende Beispiel wird ein Ereignis definiert und ein `WithEvents` Variable, die auf die Klasse verweist, die das Ereignis auslöst. Die Ereignisbehandlung `Sub` Prozedur verwendet einen `Handles` -Klausel zur Angabe der Klasse und das Ereignis behandelt.  
  
     [!code-vb[VbVbcnProcedures&4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Mit AddHandler einen Ereignishandler aufrufen  
  
1.  Stellen Sie sicher, dass das Ereignis mit deklariert eine `Event` Anweisung.  
  
2.  Führen Sie eine [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) dynamisch die Ereignisbehandlung zu verknüpfen `Sub` Prozedur mit dem Ereignis.  
  
3.  Wenn das Ereignis eintritt, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ruft automatisch die `Sub` Verfahren. Code können Sie eine `RaiseEvent` Anweisung, damit das Ereignis auftreten.  
  
     Das folgende Beispiel definiert eine `Sub` Prozedur zum Behandeln der <xref:System.Windows.Forms.Form.Closing>-Ereignis eines Formulars.</xref:System.Windows.Forms.Form.Closing> Anschließend wird mithilfe der [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) Zuordnen der `catchClose` Prozedur als Ereignishandler für <xref:System.Windows.Forms.Form.Closing>.</xref:System.Windows.Forms.Form.Closing>  
  
     [!code-vb[VbVbcnProcedures&5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     Sie können einen Ereignishandler aus einem Ereignis trennen, durch Ausführen der [RemoveHandler-Anweisung](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Sub-Prozeduren](./sub-procedures.md)   
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Gewusst wie: Erstellen einer Prozedur](./how-to-create-a-procedure.md)   
 [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)

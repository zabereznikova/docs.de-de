---
title: 'Gewusst wie: Aufrufen eines Ereignishandlers in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52b4b6ca8b03d8301535d6aeedc3bd0190d8527f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Gewusst wie: Aufrufen eines Ereignishandlers in Visual Basic
Ein *Ereignis* ist eine Aktion oder ein Vorkommen – z. B. eine Maus klicken oder ein Kreditlimit überschritten –, wird von einigen Programmkomponente, und für die Sie Code schreiben können reagieren erkannt. Ein *Ereignishandler* ist der Code, die Sie schreiben, um auf ein Ereignis zu reagieren.  
  
 Ein Ereignishandler in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ist eine `Sub` Prozedur. Allerdings rufen Sie nicht normalerweise es die gleiche Weise wie andere `Sub` Prozeduren. Stattdessen geben Sie die Prozedur als Handler für das Ereignis. Hierzu können Sie entweder mit einer [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel und eine [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) Variablen, oder mit einer [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Mit einem `Handles` -Klausel ist die Standardmethode zum Deklarieren eines ereignishandlers in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Dies ist die Möglichkeit, die der Ereignishandler wird, die geschrieben werden, wenn Sie in der integrierten Entwicklungsumgebung (IDE) programmieren. Die `AddHandler` Anweisung eignet sich zum Auslösen von Ereignissen dynamisch zur Laufzeit.  
  
 Wenn das Ereignis auftritt, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatisch die Ereignis-Handler-Prozedur aufruft. Jeglicher Code, der Zugriff auf das Ereignis kann dazu führen, dass durch die Ausführung einer [RaiseEvent-Anweisung](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Sie können das gleiche Ereignis mehrere Ereignishandler zuordnen. In einigen Fällen können Sie einen Ereignishandler von einem Ereignis trennen. Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Einen Ereignishandler mithilfe von Handles und WithEvents aufrufen  
  
1.  Stellen Sie sicher, dass das Ereignis wird deklariert, wobei ein [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Deklarieren eine Objektvariablen auf Modul- oder Ebene, mit der [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) Schlüsselwort. Die `As` -Klausel für diese Variable muss die Klasse angeben, die das Ereignis auslöst.  
  
3.  In der Deklaration eines der Ereignisbehandlung `Sub` Prozedur, hinzufügen eine [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) -Klausel, der `WithEvents` Variable und den Namen des Ereignisses.  
  
4.  Wenn das Ereignis auftritt, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ruft automatisch den `Sub` Prozedur. Code können Sie eine `RaiseEvent` Anweisung, damit das Ereignis auftreten.  
  
     Im folgende Beispiel wird ein Ereignis definiert und eine `WithEvents` Variable, die auf die Klasse verweist, die das Ereignis auslöst. Der Ereignisbehandlung `Sub` Beispielprozedur verwendet eine `Handles` -Klausel zur Angabe der Klasse und das Ereignis verarbeitet.  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Einen Ereignishandler, die mit "AddHandler" aufrufen  
  
1.  Stellen Sie sicher, dass das Ereignis wird deklariert, wobei eine `Event` Anweisung.  
  
2.  Führen Sie eine [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) die Ereignisbehandlung dynamisch Verbindung `Sub` Prozedur mit dem Ereignis.  
  
3.  Wenn das Ereignis auftritt, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ruft automatisch den `Sub` Prozedur. Code können Sie eine `RaiseEvent` Anweisung, damit das Ereignis auftreten.  
  
     Das folgende Beispiel definiert eine `Sub` Prozedur zum Behandeln der <xref:System.Windows.Forms.Form.Closing> -Ereignis für ein Formular. Es verwendet dann die [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) zum Zuordnen der `catchClose` Prozedur als ein Ereignishandler für <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     Sie können einen Ereignishandler von einem Ereignis trennen, durch das Ausführen der [RemoveHandler-Anweisung](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Gewusst wie: Erstellen einer Prozedur](./how-to-create-a-procedure.md)  
 [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)

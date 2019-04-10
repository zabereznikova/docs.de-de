---
title: 'Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3690d1c2eb8ece9059b8b25b5a14bef2021bc8f6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320170"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic
Ein *Ereignis* ist eine Aktion oder ein Vorkommen – z. B. ein Mausklick auf oder ein Kreditlimit überschritten –, wird durch eine Programmkomponente und für die Sie Code schreiben können, reagieren erkannt. Ein *Ereignishandler* ist der Code, die Sie schreiben, um auf ein Ereignis reagieren.  
  
 Ein Ereignishandler in Visual Basic ist eine `Sub` Verfahren. Allerdings Sie normalerweise rufen ihn nicht die gleiche Weise wie andere `Sub` Verfahren. Stattdessen legen Sie die Prozedur als Handler für das Ereignis. Hierzu können Sie entweder mit einer [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel und eine [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) Variable oder mit einer [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Mit einem `Handles` -Klausel ist die Standardmethode zum Deklarieren eines ereignishandlers in Visual Basic. Dies ist die Möglichkeit, die die Ereignishandler von Entwicklern geschrieben werden, wenn Sie in der integrierten Entwicklungsumgebung (IDE) programmieren. Die `AddHandler` -Anweisung zum Auslösen von Ereignissen dynamisch zur Laufzeit geeignet ist.  
  
 Wenn das Ereignis eintritt, ruft Visual Basic automatisch die Ereignishandlerprozedur. Jeglicher Code, der Zugriff auf das Ereignis hat kann dazu führen, dass durch die Ausführung einer [RaiseEvent-Anweisung](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Sie können mehrere Ereignishandler dasselbe Ereignis zuordnen. In einigen Fällen können Sie einen Handler von einem Ereignis trennen. Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)definiert sind.  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Zum Aufrufen eines ereignishandlers mithilfe von Handles und WithEvents  
  
1. Stellen Sie sicher, dass das Ereignis wird mit deklariert eine [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2. Deklarieren eine Objektvariablen auf Modul- oder Ebene, mit der [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) Schlüsselwort. Die `As` -Klausel für diese Variable muss die Klasse angeben, die das Ereignis auslöst.  
  
3. In der Deklaration der Ereignisbehandlung `Sub` Verfahren Hinzufügen einer [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) -Klausel, in der `WithEvents` Variable und den Ereignisnamen.  
  
4. Wenn das Ereignis eintritt, ruft Visual Basic automatisch die `Sub` Verfahren. Kann Ihr Code verwendet ein `RaiseEvent` Anweisung, damit das Ereignis auftreten.  
  
     Das folgende Beispiel definiert ein Ereignis und einem `WithEvents` Variable, die auf die Klasse verweist, die das Ereignis auslöst. Die Ereignisbehandlung `Sub` Beispielprozedur verwendet eine `Handles` Klausel, um anzugeben, die Klasse und das Ereignis behandelt.  
  
     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Um einen Ereignishandler mit AddHandler aufrufen  
  
1. Stellen Sie sicher, dass das Ereignis wird mit deklariert eine `Event` Anweisung.  
  
2. Führen Sie eine [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) der zur Verarbeitung von Ereignissen dynamisch verknüpfen `Sub` Prozedur mit dem Ereignis.  
  
3. Wenn das Ereignis eintritt, ruft Visual Basic automatisch die `Sub` Verfahren. Kann Ihr Code verwendet ein `RaiseEvent` Anweisung, damit das Ereignis auftreten.  
  
     Das folgende Beispiel definiert eine `Sub` Prozedur zum Behandeln der <xref:System.Windows.Forms.Form.Closing> Ereignis eines Formulars. Anschließend wird mithilfe der [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) Zuordnen der `catchClose` Prozedur als ein Ereignishandler für <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]  
  
     Sie können einen Ereignishandler von einem Ereignis trennen, durch Ausführen der [RemoveHandler-Anweisung](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Vorgehensweise: Erstellen einer Prozedur](./how-to-create-a-procedure.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)

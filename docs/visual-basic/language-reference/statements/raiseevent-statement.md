---
title: RaiseEvent-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 19949fbdb1c1c54556876323d839b16fc01608f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605341"
---
# <a name="raiseevent-statement"></a>RaiseEvent-Anweisung
Trigger deklariert ein Ereignis auf Modulebene innerhalb einer Klasse, eine Form oder ein Dokument an.  
  
## <a name="syntax"></a>Syntax  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Teile  
 `eventname`  
 Erforderlich. Name des auszulösenden Ereignisses.  
  
 `argumentlist`  
 Dies ist optional. Durch Trennzeichen getrennte Liste von Variablen, Arrays oder Ausdrücke. Die `argumentlist` -Argument muss in Klammern eingeschlossen werden. Wenn keine Argumente vorhanden sind, müssen die Klammern weggelassen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die erforderliche `eventname` ist der Name eines Ereignisses innerhalb des Moduls deklariert. Es folgt eine Visual Basic-variablennamenskonventionen.  
  
 Wenn das Ereignis innerhalb des Moduls, in dem es ausgelöst wird, nicht deklariert wurde, tritt ein Fehler auf. Das folgende Codefragment veranschaulicht die Deklaration eines Ereignisses und einer Prozedur, in der das Ereignis ausgelöst wird.  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 Sie können keine `RaiseEvent` zum Auslösen von Ereignissen, die nicht explizit im Modul deklariert werden. Beispielsweise erben alle Formulare ein <xref:System.Windows.Forms.Control.Click> Ereignis <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, er kann nicht mit ausgelöst werden `RaiseEvent` in einem abgeleiteten Formular. Wenn Sie deklarieren eine `Click` Ereignis in das Formularmodul das, shadows sie des Formulars eigenen <xref:System.Windows.Forms.Control.Click> Ereignis. Sie können weiterhin Aufrufen des Formulars <xref:System.Windows.Forms.Control.Click> Ereignis durch Aufrufen der <xref:System.Windows.Forms.Control.OnClick%2A> Methode.  
  
 Standardmäßig löst ein Ereignis, die in Visual Basic definiert die Ereignishandler in der Reihenfolge, die Verbindungen hergestellt werden. Da Ereignisse verfügen können `ByRef` Parameter in ein Prozess, der später verbunden möglicherweise Parameter, die von einem früheren Ereignishandler geändert wurden. Nachdem die Ereignishandler ausgeführt wird, wird die Steuerung an die Unterroutine zurückgegeben, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
>  Nicht freigegebene Ereignisse sollte nicht in den Konstruktor der Klasse ausgelöst werden, in denen sie deklariert werden. Obwohl solche Ereignisse nicht zur Laufzeit Fehler verursachen, können diese nicht zugeordnete Ereignis-Handler abgefangen werden. Verwenden der `Shared` Modifizierer ein freigegebenes Ereignisses zu erstellen, wenn Sie zum Auslösen eines Ereignisses aus einem Konstruktor benötigen.  
  
> [!NOTE]
>  Sie können das Standardverhalten von Ereignissen ändern, indem Sie ein benutzerdefiniertes Ereignis definieren. Für benutzerdefinierte Ereignisse die `RaiseEvent` -Anweisung ruft des Ereignis `RaiseEvent` Accessor. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Ereignisse zum Herunterzählen der Sekunden von 10 bis 0 verwendet. Der Code veranschaulicht mehrere der ereignisbezogene Methoden, Eigenschaften und Anweisungen, z. B. die `RaiseEvent` Anweisung.  
  
 Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle, und die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler. Eine Ereignisquelle kann über mehrere Handler für die Ereignisse verfügen, die sie generiert. Wenn die Klasse das Ereignis auslöst, wird dieses Ereignis in jeder Klasse ausgelöst, die das Verarbeiten von Ereignissen für diese Instanz des Objekts ausgewählt hat.  
  
 Im Beispiel wird außerdem ein Formular (`Form1`) mit einer Schaltfläche (`Button1`) und einem Textfeld (`TextBox1`) verwendet. Wenn Sie auf die Schaltfläche klicken, zeigt das erste Textfeld einen Countdown von 10 bis 0 Sekunden an. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
 Der Code für `Form1` gibt die Anfangs- und Beendigungsstatus des Formulars an. Er enthält zudem den Code, der ausgeführt wird, wenn Ereignisse ausgelöst werden.  
  
 Um dieses Codebeispiel verwenden möchten, öffnen Sie ein neues Windows-Anwendungsprojekt, fügen Sie eine Schaltfläche mit dem Namen `Button1` und ein Textfeld mit dem Namen `TextBox1` dem Hauptformular mit dem Namen `Form1`. Klicken Sie dann mit der rechten Maustaste in des Formulars, und klicken Sie auf **Code anzeigen** im Code-Editor zu öffnen.  
  
 Hinzufügen einer `WithEvents` -Variable zum Deklarationsabschnitt der der `Form1` Klasse.  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Fügen Sie den folgenden Code zum Code für `Form1` hinzu. Ersetzen Sie ggf. vorhandene doppelte Prozeduren, die wie vorhanden ist `Form_Load`, oder `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Drücken Sie F5, um das vorherige Beispiel auszuführen, und klicken Sie auf die Schaltfläche "mit der Bezeichnung" **starten**. Im ersten Textfeld werden die Sekunden heruntergezählt. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
> [!NOTE]
>  Die `My.Application.DoEvents` -Methode verarbeitet Ereignisse nicht auf genau die gleiche Weise wie das Formular. Damit wird das Formular, um die Ereignisse direkt verarbeiten, können Sie multithreading. Weitere Informationen finden Sie unter [Threading](../../programming-guide/concepts/threading/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
 [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)

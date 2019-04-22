---
title: RaiseEvent-Anweisung (Visual Basic)
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
ms.openlocfilehash: 5d8fd6adf33c992341324e07bcd2ad12986bbdf2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821009"
---
# <a name="raiseevent-statement"></a>RaiseEvent-Anweisung
Trigger deklariert ein Ereignis auf Modulebene in einer Klasse, Formular oder Dokument.  
  
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
 Die erforderlichen `eventname` ist der Name eines Ereignisses, das innerhalb des Moduls. Daraus folgt variablennamenskonventionen Visual Basic.  
  
 Wenn das Ereignis innerhalb des Moduls, in dem es ausgelöst wird, nicht deklariert wurde, tritt ein Fehler auf. Das folgende Codefragment veranschaulicht eine Ereignisdeklaration und einer Prozedur, in der das Ereignis ausgelöst wird.  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 Sie können keine `RaiseEvent` zum Auslösen von Ereignissen, die nicht explizit im Modul deklariert werden. Beispielsweise erben alle Formulare ein <xref:System.Windows.Forms.Control.Click> Ereignis <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, er kann nicht mit ausgelöst werden `RaiseEvent` in einem abgeleiteten Formular. Wenn Sie deklarieren eine `Click` Ereignis im Modul Formulars, führt es Shadowing des Formulars eigenen <xref:System.Windows.Forms.Control.Click> Ereignis. Sie können weiterhin Aufrufen des Formulars <xref:System.Windows.Forms.Control.Click> Ereignis durch Aufrufen der <xref:System.Windows.Forms.Control.OnClick%2A> Methode.  
  
 Standardmäßig löst ein Ereignis aus, in Visual Basic definiert die Ereignishandler in der Reihenfolge, in der Verbindungen hergestellt werden. Da Ereignisse verfügen können `ByRef` Parameter in ein Prozess, der später verbunden möglicherweise Parameter, die von einem früheren Ereignishandler geändert wurden. Nachdem der Ereignishandler ausgeführt wird, wird die Steuerung an die Unterroutine zurückgegeben, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
>  Nicht freigegebene Ereignisse sollte nicht im Konstruktor der Klasse ausgelöst werden, in denen sie deklariert werden. Obwohl solche Ereignisse keine Laufzeitfehler verursachen, möglicherweise nicht zugeordnete Ereignis-Handler abgefangen werden. Verwenden der `Shared` Modifizierer zum Erstellen eines freigegebenen Ereignisses, wenn Sie ein Ereignis von einem Konstruktor auszulösen, müssen.  
  
> [!NOTE]
>  Sie können das Standardverhalten von Ereignissen ändern, indem Sie ein benutzerdefiniertes Ereignis definieren. Für benutzerdefinierte Ereignisse die `RaiseEvent` -Anweisung ruft des Ereignisses `RaiseEvent` Accessor. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Ereignisse zum Herunterzählen der Sekunden von 10 bis 0 verwendet. Der Code veranschaulicht mehrere der ereignisbezogene Methoden, Eigenschaften und Anweisungen, z. B. die `RaiseEvent` Anweisung.  
  
 Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle, und die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler. Eine Ereignisquelle kann über mehrere Handler für die Ereignisse verfügen, die sie generiert. Wenn die Klasse das Ereignis auslöst, wird dieses Ereignis in jeder Klasse ausgelöst, die das Verarbeiten von Ereignissen für diese Instanz des Objekts ausgewählt hat.  
  
 Im Beispiel wird außerdem ein Formular (`Form1`) mit einer Schaltfläche (`Button1`) und einem Textfeld (`TextBox1`) verwendet. Wenn Sie auf die Schaltfläche klicken, zeigt das erste Textfeld einen Countdown von 10 bis 0 Sekunden an. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
 Der Code für `Form1` gibt die Anfangs- und Beendigungsstatus des Formulars an. Er enthält zudem den Code, der ausgeführt wird, wenn Ereignisse ausgelöst werden.  
  
 Um dieses Beispiel verwenden möchten, öffnen Sie ein neues Windows-Anwendungsprojekt, fügen Sie eine Schaltfläche mit dem Namen `Button1` und ein Textfeld mit dem Namen `TextBox1` zum Hauptformular, mit dem Namen `Form1`. Klicken Sie dann mit der rechten Maustaste in des Formulars, und klicken Sie auf **Ansichtscode** Code-Editor zu öffnen.  
  
 Hinzufügen einer `WithEvents` -Variable zum Deklarationsabschnitt der der `Form1` Klasse.  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a>Beispiel  
 Fügen Sie den folgenden Code zum Code für `Form1` hinzu. Ersetzen Sie ggf. vorhandene doppelte Prozeduren, die wie vorhanden ist, können dies `Form_Load`, oder `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 Drücken Sie F5, um das vorherige Beispiel auszuführen, und klicken Sie auf die Schaltfläche **starten**. Im ersten Textfeld werden die Sekunden heruntergezählt. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
> [!NOTE]
>  Die `My.Application.DoEvents` -Methode verarbeitet Ereignisse nicht in die gleiche Weise wie das Formular. Damit das Formular, um die Ereignisse direkt verarbeiten kann, können Sie multithreading. Weitere Informationen finden Sie unter [Managed Threading](../../../standard/threading/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)

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
ms.openlocfilehash: e04f2bbaf57789f0bdaa07c1ebd68b22e3ae6178
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333055"
---
# <a name="raiseevent-statement"></a>RaiseEvent-Anweisung
Löst ein Ereignis aus, das auf Modulebene innerhalb einer Klasse, eines Formulars oder eines Dokuments deklariert ist.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>-Komponenten  
 `eventname`  
 Erforderlich Der Name des Ereignisses, das auslöst werden soll.  
  
 `argumentlist`  
 Optional. Eine durch Trennzeichen getrennte Liste von Variablen, Arrays oder Ausdrücken. Das `argumentlist`-Argument muss in Klammern eingeschlossen werden. Wenn keine Argumente vorhanden sind, müssen die Klammern ausgelassen werden.  
  
## <a name="remarks"></a>Hinweise  
 Der erforderliche `eventname` ist der Name eines Ereignisses, das im Modul deklariert ist. Es folgt Visual Basic Variablen Namenskonventionen.  
  
 Wenn das Ereignis nicht innerhalb des Moduls deklariert wurde, in dem es ausgelöst wird, tritt ein Fehler auf. Das folgende Code Fragment veranschaulicht eine Ereignis Deklaration und eine Prozedur, in der das-Ereignis ausgelöst wird.  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 `RaiseEvent` können nicht zum Auslassen von Ereignissen verwendet werden, die nicht explizit im Modul deklariert werden. Beispielsweise erben alle Formulare ein <xref:System.Windows.Forms.Control.Click> Ereignis von <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, es kann nicht mithilfe `RaiseEvent` in einem abgeleiteten Formular ausgelöst werden. Wenn Sie im Form-Modul ein `Click` Ereignis deklarieren, werden die eigenen <xref:System.Windows.Forms.Control.Click> Ereignisse des Formulars überschattet. Sie können das <xref:System.Windows.Forms.Control.Click> Ereignis des Formulars weiterhin aufrufen, indem Sie die <xref:System.Windows.Forms.Control.OnClick%2A>-Methode aufrufen.  
  
 Standardmäßig löst ein Ereignis, das in Visual Basic definiert ist, seine Ereignishandler in der Reihenfolge aus, in der die Verbindungen hergestellt werden. Da Ereignisse über `ByRef` Parameter verfügen können, empfängt ein Prozess, der spät eine Verbindung herstellt, möglicherweise Parameter, die von einem früheren Ereignishandler geändert wurden. Nachdem die Ereignishandler ausgeführt wurden, wird die Steuerung an die Unterroutine zurückgegeben, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
> Nicht freigegebene Ereignisse sollten nicht innerhalb des Konstruktors der Klasse ausgelöst werden, in der Sie deklariert werden. Obwohl solche Ereignisse keine Laufzeitfehler verursachen, werden Sie möglicherweise von zugeordneten Ereignis Handlern nicht abgefangen. Verwenden Sie den `Shared` Modifizierer, um ein frei gegebenes Ereignis zu erstellen, wenn Sie ein Ereignis aus einem Konstruktor erstellen müssen.  
  
> [!NOTE]
> Sie können das Standardverhalten von Ereignissen ändern, indem Sie ein benutzerdefiniertes Ereignis definieren. Für benutzerdefinierte Ereignisse ruft die `RaiseEvent`-Anweisung den `RaiseEvent` Accessor des Ereignisses auf. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Ereignisse zum Herunterzählen der Sekunden von 10 bis 0 verwendet. Der Code veranschaulicht einige der ereignisbezogenen Methoden, Eigenschaften und Anweisungen, einschließlich der `RaiseEvent` Anweisung.  
  
 Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle, und die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler. Eine Ereignisquelle kann über mehrere Handler für die Ereignisse verfügen, die sie generiert. Wenn die Klasse das Ereignis auslöst, wird dieses Ereignis in jeder Klasse ausgelöst, die das Verarbeiten von Ereignissen für diese Instanz des Objekts ausgewählt hat.  
  
 Im Beispiel wird außerdem ein Formular (`Form1`) mit einer Schaltfläche (`Button1`) und einem Textfeld (`TextBox1`) verwendet. Wenn Sie auf die Schaltfläche klicken, zeigt das erste Textfeld einen Countdown von 10 bis 0 Sekunden an. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
 Der Code für `Form1` gibt die Anfangs- und Beendigungsstatus des Formulars an. Er enthält zudem den Code, der ausgeführt wird, wenn Ereignisse ausgelöst werden.  
  
 Um dieses Beispiel zu verwenden, öffnen Sie ein neues Windows-Anwendungsprojekt, und fügen Sie eine Schaltfläche mit dem Namen `Button1` und ein Textfeld mit dem Namen `TextBox1` zum Hauptformular namens `Form1`hinzu. Klicken Sie dann mit der rechten Maustaste auf das Formular und dann auf **Code anzeigen** , um den Code-Editor zu öffnen  
  
 Fügen Sie dem Deklarations Abschnitt der `Form1` Klasse eine `WithEvents` Variable hinzu.  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a>Beispiel  
 Fügen Sie den folgenden Code zum Code für `Form1` hinzu. Ersetzen Sie alle möglicherweise vorhandenen doppelten Prozeduren, z. b. `Form_Load`oder `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 Drücken Sie F5, um das vorherige Beispiel auszuführen, und klicken Sie auf die Schaltfläche **Start**. Im ersten Textfeld werden die Sekunden heruntergezählt. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
> [!NOTE]
> Die `My.Application.DoEvents`-Methode verarbeitet Ereignisse nicht exakt auf die gleiche Weise wie das Formular. Um dem Formular das direkte behandeln der Ereignisse zu ermöglichen, können Sie Multithreading verwenden. Weitere Informationen finden Sie unter [verwaltetes Threading](../../../standard/threading/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)

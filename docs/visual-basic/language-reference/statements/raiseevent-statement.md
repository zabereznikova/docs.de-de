---
title: RaiseEvent-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
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
ms.openlocfilehash: 059b1347c4a35b896f5aa19cadb28fbceb8b25c9
ms.lasthandoff: 03/13/2017

---
# <a name="raiseevent-statement"></a>RaiseEvent-Anweisung
Trigger, die ein Ereignis auf Modulebene in einer Klasse, einem Formular oder einem Dokument deklariert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Teile  
 `eventname`  
 Erforderlich. Name des auszulösenden Ereignisses.  
  
 `argumentlist`  
 Optional. Durch Trennzeichen getrennte Liste von Variablen, Arrays oder Ausdrücke. Die `argumentlist` -Argument muss in Klammern eingeschlossen werden. Wenn keine Argumente vorhanden sind, müssen die Klammern weggelassen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die erforderlichen `eventname` ist der Name eines Ereignisses innerhalb des Moduls deklariert. Daraus folgt Visual Basic Namenskonventionen Variable.  
  
 Wenn das Ereignis innerhalb des Moduls, in dem es ausgelöst wird, nicht deklariert wurde, tritt ein Fehler auf. Das folgende Codefragment zeigt eine Ereignisdeklaration und eine Prozedur, in der das Ereignis ausgelöst wird.  
  
 [!code-vb[VbVbalrEvents&#37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 Sie können keine `RaiseEvent` zum Auslösen von Ereignissen, die nicht explizit im Modul deklariert wurden. Beispielsweise erben alle Formulare ein <xref:System.Windows.Forms.Control.Click>Ereignis <xref:System.Windows.Forms.Form?displayProperty=fullName>, es kann nicht mit ausgelöst werden `RaiseEvent` in einem abgeleiteten Formular.</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click> Wenn Sie deklarieren eine `Click` Ereignis im Modul Formulars shadows sie des Formulars eigene <xref:System.Windows.Forms.Control.Click>Ereignis.</xref:System.Windows.Forms.Control.Click> Rufen Sie immer noch des Formulars <xref:System.Windows.Forms.Control.Click>-Ereignis durch das Aufrufen der <xref:System.Windows.Forms.Control.OnClick%2A>-Methode.</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click>  
  
 Standardmäßig löst ein Ereignis, die in Visual Basic definiert die Ereignishandler in der Reihenfolge, die Verbindungen hergestellt werden. Da Ereignisse besitzen können `ByRef` Parameter in ein Prozess, der später verbunden möglicherweise Parameter, die von einem vorherigen Ereignishandler geändert wurden. Nachdem die Ereignishandler ausgeführt wurden, wird die Steuerung an die Unterroutine zurückgegeben, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
>  Nicht freigegebene Ereignisse sollte nicht im Konstruktor der Klasse ausgelöst werden, in denen sie deklariert werden. Obwohl solche Ereignisse keine Laufzeitfehler verursachen, können sie keine zugeordneten Ereignishandler abgefangen werden. Verwenden der `Shared` Modifizierer, um ein freigegebenes Ereignis zu erstellen, wenn Sie ein Ereignis von einem Konstruktor auslösen müssen.  
  
> [!NOTE]
>  Sie können das Standardverhalten von Ereignissen ändern, indem Sie ein benutzerdefiniertes Ereignis definieren. Für benutzerdefinierte Ereignisse die `RaiseEvent` -Anweisung ruft des Ereignis `RaiseEvent` Accessor. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Ereignisse zum Herunterzählen der Sekunden von 10 bis 0 verwendet. Der Code veranschaulicht einige der Ereignisse, Methoden, Eigenschaften und Anweisungen, z. B. die `RaiseEvent` Anweisung.  
  
 Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle, und die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler. Eine Ereignisquelle kann über mehrere Handler für die Ereignisse verfügen, die sie generiert. Wenn die Klasse das Ereignis auslöst, wird dieses Ereignis in jeder Klasse ausgelöst, die das Verarbeiten von Ereignissen für diese Instanz des Objekts ausgewählt hat.  
  
 Im Beispiel wird außerdem ein Formular (`Form1`) mit einer Schaltfläche (`Button1`) und einem Textfeld (`TextBox1`) verwendet. Wenn Sie auf die Schaltfläche klicken, zeigt das erste Textfeld einen Countdown von 10 bis 0 Sekunden an. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
 Der Code für `Form1` gibt die Anfangs- und Beendigungsstatus des Formulars an. Er enthält zudem den Code, der ausgeführt wird, wenn Ereignisse ausgelöst werden.  
  
 Um dieses Codebeispiel zu verwenden, öffnen Sie ein neues Windows-Anwendungsprojekt, fügen Sie eine Schaltfläche mit dem Namen `Button1` und ein Textfeld mit dem Namen `TextBox1` auf das Hauptformular mit dem Namen `Form1`. Klicken Sie dann mit der rechten Maustaste in des Formulars, und klicken Sie auf **Anzeigecode** Code-Editor zu öffnen.  
  
 Hinzufügen einer `WithEvents` Abschnitt Deklarationen der Variablen der `Form1` Klasse.  
  
 [!code-vb[VbVbalrEvents&14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Fügen Sie den folgenden Code zum Code für `Form1` hinzu. Ersetzen Sie ggf. doppelte Prozeduren, z. B. möglicherweise `Form_Load`, oder `Button_Click`.  
  
 [!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Drücken Sie F5, um das vorherige Beispiel auszuführen, und klicken Sie auf die Schaltfläche **Start**. Im ersten Textfeld werden die Sekunden heruntergezählt. Nach Ablauf der vollständigen Zeitspanne (10 Sekunden) wird im ersten Textfeld „Fertig“ angezeigt.  
  
> [!NOTE]
>  Die `My.Application.DoEvents` -Methode verarbeitet Ereignisse nicht auf genau die gleiche Weise wie das Formular. Um das Formular die Ereignisse direkt behandeln kann, können Sie multithreading. Weitere Informationen finden Sie unter [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)   
 [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)

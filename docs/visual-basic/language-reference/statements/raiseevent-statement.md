---
title: "RaiseEvent Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.RaiseEventMethod"
  - "vb.RaiseEvent"
  - "RaiseEvent"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "raising events, RaiseEvent statement"
  - "RaiseEvent statement"
  - "event handlers, connecting events to"
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# RaiseEvent Statement
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Löst ein Ereignis aus, das auf Modulebene in einer Klasse, einem Formular oder einem Dokument deklariert wurde.  
  
## Syntax  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## Teile  
 `eventname`  
 Erforderlich.  Name des auszulösenden Ereignisses.  
  
 `argumentlist`  
 Optional.  Durch Komma getrennte Liste von Variablen, Arrays und Ausdrücken.  Das `argumentlist`\-Argument muss in Klammern eingeschlossen werden.  Wenn keine Argumente vorhanden sind, müssen die Klammern weggelassen werden.  
  
## Hinweise  
 Der erforderliche `eventname` ist der Name eines im Modul deklarierten Ereignisses.  Der Wert muss der Visual Basic\-Namenskonvention für Variablen entsprechen.  
  
 Wenn das Ereignis nicht in dem Modul deklariert wurde, in dem es ausgelöst wird, tritt ein Fehler auf.  Im folgenden Codefragment werden eine Ereignisdeklaration und eine Prozedur veranschaulicht, in der das Ereignis ausgelöst wird.  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 Mit `RaiseEvent` können keine Ereignisse ausgelöst werden, die nicht explizit im Modul deklariert wurden.  Beispielsweise erben alle Formulare ein <xref:System.Windows.Forms.Control.Click>\-Ereignis von <xref:System.Windows.Forms.Form?displayProperty=fullName>, und es kann nicht mit `RaiseEvent` in einem abgeleiteten Formular ausgelöst werden  Wenn Sie ein `Click`\-Ereignis im Modul des Formulars deklarieren, führt es für das <xref:System.Windows.Forms.Control.Click>\-Ereignis des Formulars Shadowing aus.  Sie können dennoch das <xref:System.Windows.Forms.Control.Click>\-Ereignis des Formulars aufrufen, indem Sie die <xref:System.Windows.Forms.Control.OnClick%2A>\-Methode aufrufen.  
  
 Ein in Visual Basic definiertes Ereignis löst standardmäßig seine Ereignishandler in der Reihenfolge aus, in der die Verbindungen erstellt werden.  Da Ereignisse `ByRef`\-Parameter besitzen können, kann ein Prozess, der später verbunden wird, unter Umständen Parameter erhalten, die von einem vorherigen Ereignishandler geändert wurden.  Nachdem die Ereignishandler ausgeführt wurden, wird die Steuerung an die Unterroutine zurückgegeben, die das Ereignis ausgelöst hat.  
  
> [!NOTE]
>  Nicht freigegebene Ereignisse sollten nicht im Konstruktor der Klasse ausgelöst werden, in der sie deklariert sind.  Zwar generieren solche Ereignisse keine Laufzeitfehler, aber sie werden u. U. von zugeordneten Ereignishandlern nicht abgefangen.  Verwenden Sie den `Shared`\-Modifizierer, um ein freigegebenes Ereignis zu erstellen, wenn Sie ein Ereignis in einem Konstruktor auslösen müssen.  
  
> [!NOTE]
>  Sie können das Standardverhalten von Ereignissen ändern, indem Sie ein benutzerdefiniertes Ereignis definieren.  Für benutzerdefinierte Ereignisse ruft die `RaiseEvent`\-Anweisung den `RaiseEvent`\-Accessor des Ereignisses auf.  Weitere Informationen über benutzerdefinierte Ereignisse finden Sie unter [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Beispiel  
 Im folgenden Beispiel dienen Ereignisse zum Herunterzählen von Sekunden von 10 bis 0.  Im Code werden mehrere der ereignisbezogenen Methoden, Eigenschaften und Anweisungen, einschließlich der `RaiseEvent`\-Anweisung, veranschaulicht.  
  
 Die Klasse, die ein Ereignis auslöst, ist die Ereignisquelle; die Methoden, die das Ereignis verarbeiten, sind die Ereignishandler.  Eine Ereignisquelle kann mehrere Handler für die generierten Ereignisse haben.  Löst die Klasse das Ereignis aus, so wird dieses Ereignis für jede Klasse ausgelöst, die Ereignisse für diese Instanz des Objekts verarbeitet.  
  
 Im Beispiel wird außerdem ein Formular \(`Form1`\) mit einer Schaltfläche \(`Button1`\) und einem Textfeld \(`TextBox1`\) verwendet.  Wenn Sie auf die Schaltfläche klicken, wird im ersten Textfeld ein Countdown von 10 bis 0 Sekunden angezeigt.  Nach Ablauf der vollständigen Zeitspanne \(10 Sekunden\) wird im ersten Textfeld "Done" angezeigt.  
  
 Der Code für `Form1` gibt den Anfangs\- und Endstatus des Formulars an.  Darüber hinaus enthält er den Code, der beim Auslösen von Ereignissen ausgeführt wird.  
  
 Zum Anwenden dieses Beispiels öffnen Sie ein neues Windows\-Anwendungsprojekt und fügen dem Hauptformular `Form1` die Schaltfläche `Button1` und das Textfeld `TextBox1` hinzu.  Klicken Sie anschließend mit der rechten Maustaste auf das Formular, und klicken Sie auf **Code anzeigen**, um den Code\-Editor zu öffnen.  
  
 Fügen Sie dem Deklarationsabschnitt der `Form1`\-Klasse eine `WithEvents`\-Variable hinzu.  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## Beispiel  
 Fügen Sie dem Code für `Form1` den folgenden Code hinzu:  Ersetzen Sie eventuelle doppelte Prozeduren, wie `Form_Load` oder `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Drücken Sie F5, um das vorherige Beispiel auszuführen, und klicken Sie auf die Schaltfläche **Starten**.  Im ersten Textfeld wird der Countdown der Sekunden gestartet.  Nach Ablauf der vollständigen Zeitspanne \(10 Sekunden\) wird im ersten Textfeld "Done" angezeigt.  
  
> [!NOTE]
>  Die `My.Application.DoEvents`\-Methode verarbeitet Ereignisse nicht genau auf die gleiche Weise wie das Formular.  Damit das Formular die Ereignisse direkt behandeln kann, können Sie Multithreading verwenden.  Weitere Informationen finden Sie unter [Threading](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Siehe auch  
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
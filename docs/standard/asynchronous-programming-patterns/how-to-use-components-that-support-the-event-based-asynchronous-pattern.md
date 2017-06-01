---
title: "How to: Use Components That Support the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Use Components That Support the Event-based Asynchronous Pattern
Viele Komponenten bieten die Möglichkeit der asynchronen Aufgabenausführung.  Mit der <xref:System.Media.SoundPlayer>\-Komponente und der <xref:System.Windows.Forms.PictureBox>\-Komponente können Sie beispielsweise Sounds und Bilder "im Hintergrund" laden, während der Hauptthread weiterhin ohne Unterbrechung ausgeführt wird.  
  
 Das Verwenden asynchroner Methoden für eine Klasse, die [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) unterstützt, ist z, einen Ereignishandler an das *MethodName*`Completed`\-Ereignis der Komponente nicht so einfach sein, ebenso wie für jedes andere Ereignis wurden.  Wenn Sie die *MethodName*`Async` aufrufen, wird die Anwendung ohne Unterbrechung weiter ausgeführt, bis das *MethodName*`Completed`\-Ereignis ausgelöst wird.  Sie können im Ereignishandler den <xref:System.ComponentModel.AsyncCompletedEventArgs>\-Parameter auf den erfolgreichen Abschluss der Operation oder deren Abbruch hin überprüfen.  
  
 Weitere Informationen zum Verwenden von Ereignishandlern finden Sie unter [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 In der folgenden Prozedur wird gezeigt, wie die asynchrone Bildladefunktion eines <xref:System.Windows.Forms.PictureBox>\-Steuerelements verwendet wird.  
  
### So aktivieren Sie ein PictureBox\-Steuerelement, um asynchron ein Bild zu laden  
  
1.  Erstellen Sie im Formular eine Instanz der <xref:System.Windows.Forms.PictureBox>\-Komponente.  
  
2.  Ordnen Sie dem <xref:System.Windows.Forms.PictureBox.LoadCompleted>\-Ereignis einen Ereignishandler zu.  
  
     Prüfen Sie, ob während des asynchronen Downloads Fehler aufgetreten sind.  Prüfen Sie ebenfalls, ob der Download ggf. abgebrochen wurde.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Fügen Sie dem Formular zwei Schaltflächen hinzu, die `loadButton`\-Schaltfläche und die `cancelLoadButton`\-Schaltfläche.  Fügen Sie anschließend die <xref:System.Windows.Forms.Control.Click>\-Ereignishandler hinzu, um den Download zu starten und abzubrechen.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Führen Sie die Anwendung aus.  
  
     Sie können das Formular während des Bilddownloads ungehindert verschieben und nach Belieben vergrößern oder verkleinern.  
  
## Siehe auch  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/de-de/c731a50c-09c1-4468-9646-54c86b75d269)
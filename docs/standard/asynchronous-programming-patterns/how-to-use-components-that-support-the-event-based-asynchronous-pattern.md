---
title: "Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49e03a8d886ccd4ed6e4b2a19692c1874f5928ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen
Viele Komponenten bieten Ihnen die Möglichkeit, ihre Arbeit asynchron ausführen. Die <xref:System.Media.SoundPlayer> und <xref:System.Windows.Forms.PictureBox> Komponenten, z. B. aktivieren, die Sie laden sounds und Bilder "im Hintergrund", während der Hauptthread weiterhin ohne Unterbrechung ausgeführt wird.  
  
 Verwenden von asynchronen Methoden auf eine Klasse, unterstützt die [Übersicht über ereignisbasierte asynchrone Muster](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) kann so einfach wie einen Ereignishandler für der Komponente Anfügen *MethodName* `Completed` -Ereignis wie für jedes andere Ereignis. Beim Aufrufen der *MethodName* `Async` -Methode, Ihre Anwendung weiterhin ohne Unterbrechung bis ausgeführt der *MethodName* `Completed` Ereignis wird ausgelöst. Im Ereignishandler, untersuchen Sie die <xref:System.ComponentModel.AsyncCompletedEventArgs> Parameter, um festzustellen, ob der asynchrone Vorgang erfolgreich abgeschlossen wurde oder wenn er abgebrochen wurde.  
  
 Weitere Informationen zur Verwendung von Ereignishandlern finden Sie unter [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Das folgende Verfahren zeigt, wie die asynchronen Laden von Images-Funktion von einem <xref:System.Windows.Forms.PictureBox> Steuerelement.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>So aktivieren Sie ein PictureBox-Steuerelement zum asynchronen Laden eines Bilds  
  
1.  Erstellen Sie eine Instanz von der <xref:System.Windows.Forms.PictureBox> -Komponente in das Formular.  
  
2.  Weisen Sie einen Ereignishandler an das <xref:System.Windows.Forms.PictureBox.LoadCompleted> Ereignis.  
  
     Überprüfen Sie nach Fehlern, die möglicherweise während der asynchronen Download hier ausgegeben wurden. Dies ist auch, wo Sie nach einem Abbruch gesucht.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Fügen Sie zwei Schaltflächen, `loadButton` und `cancelLoadButton`, um das Formular. Hinzufügen <xref:System.Windows.Forms.Control.Click> Ereignishandler zum Starten und Abbrechen des Downloads.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Führen Sie die Anwendung aus.  
  
     Wie die Bilddownloads können Sie das Formular frei verschieben, minimieren und maximieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [NICHT im BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)

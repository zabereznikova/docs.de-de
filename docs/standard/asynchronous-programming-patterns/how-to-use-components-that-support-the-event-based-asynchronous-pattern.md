---
title: 'Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 466c01dd44d217e466c520efba43a3a1d7bbf4c7
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen
Viele Komponenten bieten Ihnen die Möglichkeit, ihre Arbeit asynchron auszuführen. Mit den Komponenten <xref:System.Media.SoundPlayer> und <xref:System.Windows.Forms.PictureBox> können Sie beispielsweise Sounds und Bilder „im Hintergrund“ laden, während Ihr Hauptthread ohne Unterbrechung weiterläuft.  
  
 Die Verwendung von asynchronen Methoden in einer Klasse, die die [Übersicht für ereignisbasierte asynchrone Muster](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) unterstützt, kann so einfach sein, indem Sie einen Ereignishandler an das Ereignis *MethodName***Completed** der Komponente wie bei jedem anderen Ereignis anhängen. Beim Aufrufen der *MethodName***Async**-Methode wird Ihre Anwendung weiterhin ohne Unterbrechung ausgeführt, bis das *MethodName***Completed**-Ereignis ausgelöst wird. In Ihrem Ereignishandler können Sie anhand des Parameters <xref:System.ComponentModel.AsyncCompletedEventArgs> festzustellen, ob der asynchrone Vorgang erfolgreich beendet oder abgebrochen wurde.  
  
 Weitere Informationen zur Verwendung von Ereignishandlern finden Sie unter [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Die folgende Prozedur zeigt, wie die Funktion zum asynchronen Laden von Images eines <xref:System.Windows.Forms.PictureBox>-Steuerelements verwendet wird.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>So aktivieren Sie ein PictureBox-Steuerelement zum asynchronen Laden eines Images  
  
1.  Erstellen Sie eine Instanz der <xref:System.Windows.Forms.PictureBox>-Komponente in Ihrem Formular.  
  
2.  Weisen Sie dem <xref:System.Windows.Forms.PictureBox.LoadCompleted>-Ereignis einen Ereignishandler zu.  
  
     Ob während des asynchronen Downloads Fehler aufgetreten sind, prüfen Sie hier. Hier sehen Sie auch, falls es zu einem Abbruch kam.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Fügen Sie zwei Schaltflächen, `loadButton` und `cancelLoadButton`, zu Ihrem Formular hinzu. Fügen Sie <xref:System.Windows.Forms.Control.Click>-Ereignishandler zum Starten und Abbrechen des Downloads hinzu.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Führen Sie die Anwendung aus.  
  
     Während der Imagedownload voranschreitet, können Sie das Formular frei verschieben, minimieren und maximieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [NICHT IM BUILD: Multithreading in Visual Basic](https://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)

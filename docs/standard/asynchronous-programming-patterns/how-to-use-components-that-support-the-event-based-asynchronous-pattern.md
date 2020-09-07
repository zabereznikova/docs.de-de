---
title: 'Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: e23a9b28cff9428cbc8896515ce71db85c832243
ms.sourcegitcommit: b78018c850590dfc0348301e1748b779c28604cc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "89379147"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen
Viele Komponenten bieten Ihnen die Möglichkeit, ihre Arbeit asynchron auszuführen. Mit den Komponenten <xref:System.Media.SoundPlayer> und <xref:System.Windows.Forms.PictureBox> können Sie beispielsweise Sounds und Bilder „im Hintergrund“ laden, während Ihr Hauptthread ohne Unterbrechung weiterläuft.  
  
 Die Verwendung von asynchronen Methoden in einer Klasse, die die [Übersicht für ereignisbasierte asynchrone Muster](event-based-asynchronous-pattern-overview.md) unterstützt, kann so einfach sein, indem Sie einen Ereignishandler an das Ereignis _MethodName_**Completed** der Komponente wie bei jedem anderen Ereignis anhängen. Beim Aufrufen der _MethodName_**Async**-Methode wird Ihre Anwendung weiterhin ohne Unterbrechung ausgeführt, bis das _MethodName_**Completed**-Ereignis ausgelöst wird. In Ihrem Ereignishandler können Sie anhand des Parameters <xref:System.ComponentModel.AsyncCompletedEventArgs> festzustellen, ob der asynchrone Vorgang erfolgreich beendet oder abgebrochen wurde.  
  
 Weitere Informationen zur Verwendung von Ereignishandlern finden Sie unter [Übersicht über Ereignishandler](../../framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Die folgende Prozedur zeigt, wie die Funktion zum asynchronen Laden von Images eines <xref:System.Windows.Forms.PictureBox>-Steuerelements verwendet wird.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>So aktivieren Sie ein PictureBox-Steuerelement zum asynchronen Laden eines Images  
  
1. Erstellen Sie eine Instanz der <xref:System.Windows.Forms.PictureBox>-Komponente in Ihrem Formular.  
  
2. Weisen Sie dem <xref:System.Windows.Forms.PictureBox.LoadCompleted>-Ereignis einen Ereignishandler zu.  
  
     Ob während des asynchronen Downloads Fehler aufgetreten sind, prüfen Sie hier. Hier sehen Sie auch, falls es zu einem Abbruch kam.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#5)]  
  
3. Fügen Sie zwei Schaltflächen, `loadButton` und `cancelLoadButton`, zu Ihrem Formular hinzu. Fügen Sie <xref:System.Windows.Forms.Control.Click>-Ereignishandler zum Starten und Abbrechen des Downloads hinzu.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#4)]  
  
4. Führen Sie die Anwendung aus.  
  
     Während der Imagedownload voranschreitet, können Sie das Formular frei verschieben, minimieren und maximieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](event-based-asynchronous-pattern-overview.md)

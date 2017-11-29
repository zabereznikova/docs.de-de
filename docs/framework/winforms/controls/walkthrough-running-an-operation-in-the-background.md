---
title: "Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de485eb0b9c67ee9c3c897b6521971f50aaf751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund
Gibt es einen Vorgang, der bis zu seinem Abschluss eine lange Zeit in Anspruch nimmt, und Sie möchten keine Verzögerungen in der Benutzeroberfläche verursachen, können Sie die <xref:System.ComponentModel.BackgroundWorker>-Klasse dazu verwenden, den Vorgang über einen anderen Thread auszuführen.  
  
 Eine vollständige Liste des Codes in diesem Beispiel verwendet, finden Sie unter [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-run-an-operation-in-the-background"></a>Um einen Vorgang im Hintergrund ausgeführt werden.  
  
1.  Mit dem Formular in Windows Forms-Designer aktiv ist, ziehen Sie zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular, und legen Sie anschließend die `Name` und <xref:System.Windows.Forms.Control.Text%2A> Eigenschaften der Schaltflächen entsprechend der folgenden Tabelle.  
  
    |Schaltfläche|Name|Text|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|**Start**|  
    |`button2`|`cancelBtn`|**Abbrechen**|  
  
2.  Öffnen der **Toolbox**, klicken Sie auf die **Komponenten** Registerkarte, und ziehen Sie dann die <xref:System.ComponentModel.BackgroundWorker> -Komponente auf das Formular.  
  
     Die `backgroundWorker1` Komponente angezeigt wird, der **Komponentenleiste**.  
  
3.  In der **Eigenschaften** legen die <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> Eigenschaft `true`.  
  
4.  In der **Eigenschaften** Fenster, klicken Sie auf die **Ereignisse** aus, und doppelklicken Sie dann auf die <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignisse, um Ereignishandler zu erstellen.  
  
5.  Fügen Sie den zeitaufwendigen Code in der <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignishandler.  
  
6.  Extrahieren Sie alle Parameter erforderlich, die für den Vorgang mithilfe der <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> Eigenschaft von der <xref:System.ComponentModel.DoWorkEventArgs> Parameter.  
  
7.  Weisen Sie das Ergebnis der Berechnung auf der <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> Eigenschaft von der <xref:System.ComponentModel.DoWorkEventArgs>.  
  
     Dies wird zur Verfügung, die <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  Fügen Sie Code zum Abrufen von das Ergebnis des Vorgangs in der <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. Implementieren Sie die `TimeConsumingOperation`-Methode.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. Doppelklicken Sie in Windows Forms-Designer auf `startButton` zum Erstellen der <xref:System.Windows.Forms.Control.Click> -Ereignishandler.  
  
11. Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> Methode in der <xref:System.Windows.Forms.Control.Click> -Ereignishandler für `startButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. Doppelklicken Sie in Windows Forms-Designer auf `cancelButton` zum Erstellen der <xref:System.Windows.Forms.Control.Click> -Ereignishandler.  
  
13. Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> Methode in der <xref:System.Windows.Forms.Control.Click> -Ereignishandler für `cancelButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. Importieren Sie am Anfang der Datei die System.ComponentModel-Namespace und System.Threading-Namespaces ein.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. Drücken Sie F6, um die Projektmappe zu erstellen, und drücken Sie STRG + F5, um die Anwendung außerhalb des Debuggers ausgeführt werden.  
  
> [!NOTE]
>  Wenn Sie F5, um die Anwendung im Debugger auszuführen drücken, wird die Ausnahme ausgelöst, der `TimeConsumingOperation` Methode abgefangen und vom Debugger angezeigt wird. Beim Ausführen der Anwendung außerhalb des Debuggers die <xref:System.ComponentModel.BackgroundWorker> Ausnahmen behandelt, und speichert es in der <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> Eigenschaft von der <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.  
  
1.  Klicken Sie auf die **starten** Schaltfläche, um einen asynchronen Vorgang auszuführen, und klicken Sie dann auf die **"Abbrechen"** Schaltfläche, um einen laufenden asynchronen Vorgang zu beenden.  
  
     Das Ergebnis jedes Vorgangs wird in einem <xref:System.Windows.Forms.MessageBox>-Steuerelement angezeigt.  
  
## <a name="next-steps"></a>Nächste Schritte  
  
-   Implementieren eines Formulars, das Fortschrittsberichte, während ein asynchroner Vorgang durchführt. Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
-   Implementieren Sie eine Klasse, die das asynchrone Muster für Komponenten unterstützt. Weitere Informationen finden Sie unter [das ereignisbasierte asynchrone Muster implementieren](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [BackgroundWorker-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md)

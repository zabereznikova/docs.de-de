---
title: "Exemplarische Vorgehensweise: Ausf&#252;hren eines Vorgangs im Hintergrund | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Hintergrundvorgänge"
  - "Hintergrundaufgaben"
  - "Hintergrundthreads"
  - "BackgroundWorker-Klasse, Beispiele"
  - "Formulare, Hintergrundvorgänge"
  - "Formulare, Multithreading"
  - "Threading [Windows Forms], Hintergrundvorgänge"
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Exemplarische Vorgehensweise: Ausf&#252;hren eines Vorgangs im Hintergrund
Wenn die Ausführung eines Vorgangs sehr lange dauert und Sie Verzögerungen in der Benutzeroberfläche vermeiden möchten, können Sie den Vorgang mithilfe der <xref:System.ComponentModel.BackgroundWorker>\-Klasse in einem anderen Thread ausführen.  
  
 Eine vollständige Liste des in diesem Beispiel verwendeten Codes finden Sie unter [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So führen Sie einen Vorgang im Hintergrund aus  
  
1.  Ziehen Sie, während das Formular im Windows Forms\-Designer aktiv ist, zwei <xref:System.Windows.Forms.Button>\-Steuerelemente aus der **Toolbox** auf das Formular, und legen Sie dann die `Name`\-Eigenschaft und die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft der Schaltflächen entsprechend der folgenden Tabelle fest.  
  
    |Button|Name|Text|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|Start|  
    |`button2`|`cancelBtn`|Abbrechen|  
  
2.  Öffnen Sie die **Toolbox**, klicken Sie auf die Registerkarte **Komponenten**, und ziehen Sie dann die <xref:System.ComponentModel.BackgroundWorker>\-Komponente auf das Formular.  
  
     Die `backgroundWorker1`\-Komponente wird auf der **Komponentenleiste** angezeigt.  
  
3.  Legen Sie im **Eigenschaftenfenster** die <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>\-Eigenschaft auf `true` fest.  
  
4.  Klicken Sie im **Eigenschaftenfenster** auf die Schaltfläche **Ereignisse**, und doppelklicken Sie dann auf das <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignis und das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignis, um Ereignishandler zu erstellen.  
  
5.  Fügen Sie den zeitaufwendigen Code in den <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler ein.  
  
6.  Extrahieren Sie alle vom Vorgang benötigten Parameter aus der <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>\-Eigenschaft des <xref:System.ComponentModel.DoWorkEventArgs>\-Parameters.  
  
7.  Weisen Sie der <xref:System.ComponentModel.DoWorkEventArgs.Result%2A>\-Eigenschaft von <xref:System.ComponentModel.DoWorkEventArgs> das Ergebnis der Berechnung zu.  
  
     Dieses Ergebnis steht dem <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignishandler zur Verfügung.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  Fügen Sie Code ein, durch den das Ergebnis des Vorgangs im <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignishandler abgerufen wird.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. Implementieren Sie die `TimeConsumingOperation`\-Methode.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. Doppelklicken Sie im Windows Forms\-Designer auf `startButton`, um den <xref:System.Windows.Forms.Control.Click>\-Ereignishandler zu erstellen.  
  
11. Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>\-Methode im <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für `startButton` auf.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. Doppelklicken Sie im Windows Forms\-Designer auf `cancelButton`, um den <xref:System.Windows.Forms.Control.Click>\-Ereignishandler zu erstellen.  
  
13. Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>\-Methode im <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für `cancelButton` auf.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. Importieren Sie oben in der Datei den System.ComponentModel\-Namespace und den System.Threading\-Namespace.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. Drücken Sie F6, um die Projektmappe zu erstellen, und dann STRG\+F5, um die Anwendung außerhalb des Debuggers auszuführen.  
  
> [!NOTE]
>  Wenn Sie F5 drücken, um die Anwendung im Debugger auszuführen, wird die in der `TimeConsumingOperation`\-Methode ausgelöste Ausnahme abgefangen und vom Debugger angezeigt.  Wenn Sie die Anwendung außerhalb des Debuggers ausführen, behandelt <xref:System.ComponentModel.BackgroundWorker> die Ausnahme und fängt sie in der <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>\-Eigenschaft von <xref:System.ComponentModel.RunWorkerCompletedEventArgs> ab.  
  
1.  Klicken Sie auf die Schaltfläche **Start**, um einen asynchronen Vorgang auszuführen, und dann auf die Schaltfläche **Cancel**, um einen laufenden asynchronen Vorgang anzuhalten.  
  
     Das Ergebnis jedes Vorgangs wird in <xref:System.Windows.Forms.MessageBox> angezeigt.  
  
## Nächste Schritte  
  
-   Implementieren Sie ein Formular, durch das der Status eines asynchronen Vorgangs während der Ausführung gemeldet wird.  Weitere Informationen finden Sie unter [Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
-   Implementieren Sie eine Klasse, die das asynchrone Muster für Komponenten unterstützt.  Weitere Informationen finden Sie unter [Implementing the Event\-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## Siehe auch  
 <xref:System.ComponentModel.BackgroundWorker>   
 <xref:System.ComponentModel.DoWorkEventArgs>   
 [Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [BackgroundWorker\-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
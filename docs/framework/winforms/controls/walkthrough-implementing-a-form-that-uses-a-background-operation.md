---
title: "Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet | Microsoft Docs"
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
  - "BackgroundWorker-Komponente"
  - "Formulare, Hintergrundvorgänge"
  - "Formulare, Multithreading"
  - "Threading [Windows Forms], Hintergrundvorgänge"
  - "Threading [Windows Forms], Formulare"
  - "Threading [Windows Forms], Exemplarische Vorgehensweisen"
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet
Wenn die Ausführung einer Operation sehr lange dauert und Sie verhindern möchten, dass die Benutzeroberfläche \(UI\) nicht mehr reagiert oder sich "aufhängt", können Sie mit der <xref:System.ComponentModel.BackgroundWorker>\-Klasse die Operation mit einem anderen Thread ausführen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie die <xref:System.ComponentModel.BackgroundWorker>\-Klasse zur Durchführung zeitintensiver Berechnungen "im Hintergrund" verwendet wird, während die Benutzeroberfläche weiterhin reagiert.  Anschließend verfügen Sie über eine Anwendung, die Fibonacci\-Zahlen asynchron berechnet.  Auch wenn die Berechnung einer großen Fibonacci\-Zahl recht lange dauern kann, wird der primäre UI\-Thread von dieser Verzögerung nicht unterbrochen, sodass das Formular auch während der Berechnung auf Eingaben reagiert.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen einer Windows\-basierten Anwendung  
  
-   Erstellen eines <xref:System.ComponentModel.BackgroundWorker> im Formular  
  
-   Hinzufügen von asynchronen Ereignishandlern  
  
-   Hinzufügen von Fortschrittsberichterstellung und Abbruchunterstützung  
  
 Eine vollständige Liste des in diesem Beispiel verwendeten Codes finden Sie unter [Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Zunächst wird das Projekt erstellt und das Formular eingerichtet.  
  
#### So erstellen Sie ein Formular, das eine Hintergrundoperation verwendet  
  
1.  Erstellen Sie ein Windows\-basiertes Anwendungsprojekt mit dem Namen `BackgroundWorkerExample`.  Ausführliche Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **Form1** und dann im Kontextmenü auf **Umbenennen**.  Ändern Sie den Dateinamen in `FibonacciCalculator`.  Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob Sie alle Verweise auf das Codeelement '`Form1`' umbenennen möchten.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.NumericUpDown>\-Steuerelement aus der **Toolbox** auf das Formular.  Legen Sie die <xref:System.Windows.Forms.NumericUpDown.Minimum%2A>\-Eigenschaft auf `1` und die <xref:System.Windows.Forms.NumericUpDown.Maximum%2A>\-Eigenschaft auf `91` fest.  
  
4.  Fügen Sie dem Formular zwei <xref:System.Windows.Forms.Button>\-Steuerelemente hinzu.  
  
5.  Benennen Sie das erste <xref:System.Windows.Forms.Button>\-Steuerelement in `startAsyncButton` um, und legen Sie die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft auf `Start Async` fest.  Benennen Sie das zweite <xref:System.Windows.Forms.Button>\-Steuerelement in `cancelAsyncButton` um, und legen Sie die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft auf `Cancel Async` fest.  Legen Sie die entsprechende <xref:System.Windows.Forms.Control.Enabled%2A>\-Eigenschaft auf `false` fest.  
  
6.  Erstellen Sie einen Ereignishandler für beide <xref:System.Windows.Forms.Control.Click>\-Ereignisse des <xref:System.Windows.Forms.Button>\-Steuerelements.  Ausführliche Informationen finden Sie unter [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/de-de/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
7.  Ziehen Sie ein <xref:System.Windows.Forms.Label>\-Steuerelement aus der **Toolbox** auf das Formular, und benennen Sie es in `resultLabel` um.  
  
8.  Ziehen Sie ein <xref:System.Windows.Forms.ProgressBar>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
## Erstellen eines BackgroundWorker im Formular  
 Sie können den <xref:System.ComponentModel.BackgroundWorker> für die asynchrone Operation mit dem **Windows** **Forms\-Designer** erstellen.  
  
#### So erstellen Sie einen BackgroundWorker mithilfe des Designers  
  
-   Ziehen Sie von der Registerkarte **Komponenten** der **Toolbox** einen <xref:System.ComponentModel.BackgroundWorker> auf das Formular.  
  
## Hinzufügen von asynchronen Ereignishandlern  
 Sie sind nun bereit, Ereignishandler für die asynchronen Ereignisse der <xref:System.ComponentModel.BackgroundWorker>\-Komponente hinzuzufügen.  Die zeitintensive Operation, die im Hintergrund ausgeführt wird und Fibonacci\-Zahlen berechnet, wird von einem dieser Ereignishandler aufgerufen.  
  
#### So implementieren Sie asynchrone Ereignishandler  
  
1.  Klicken Sie im **Eigenschaftenfenster** bei ausgewählter <xref:System.ComponentModel.BackgroundWorker>\-Komponente auf die Schaltfläche **Ereignisse**.  Doppelklicken Sie auf das <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignis und das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignis, um Ereignishandler zu erstellen.  Weitere Informationen zur Verwendung von Ereignishandlern finden Sie unter [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/de-de/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
2.  Erstellen Sie im Formular eine neue Methode mit dem Namen `ComputeFibonacci`.  Diese Methode erledigt die eigentliche Arbeit und wird im Hintergrund ausgeführt.  Dieser Code veranschaulicht die rekursive Umsetzung des Fibonacci\-Algorithmus, der deutlich ineffizient und bei großen Zahlen exponentiell langsamer ist.  Er wird hier verwendet, um eine Operation zu zeigen, die Ihre Anwendung deutlich verlangsamen kann.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  Fügen Sie im <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler der `ComputeFibonacci`\-Methode einen Aufruf hinzu.  Übernehmen Sie den ersten Parameter für `ComputeFibonacci` von der <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>\-Eigenschaft des <xref:System.ComponentModel.DoWorkEventArgs>.  Der <xref:System.ComponentModel.BackgroundWorker>\-Parameter und der <xref:System.ComponentModel.DoWorkEventArgs>\-Parameter werden später zur Fortschrittsberichterstellung und Abbruchunterstützung verwendet.  Weisen Sie der <xref:System.ComponentModel.DoWorkEventArgs.Result%2A>\-Eigenschaft von <xref:System.ComponentModel.DoWorkEventArgs> den Rückgabewert von `ComputeFibonacci` zu.  Dieses Ergebnis steht dem <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignishandler zur Verfügung.  
  
    > [!NOTE]
    >  Der <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler verweist nicht direkt auf die `backgroundWorker1`\-Instanzvariable, da dieser Ereignishandler ansonsten mit einer spezifischen Instanz von <xref:System.ComponentModel.BackgroundWorker> gekoppelt wird.  Stattdessen wird ein Verweis auf den <xref:System.ComponentModel.BackgroundWorker>, der dieses Ereignis ausgelöst hat, vom `sender`\-Parameter wiederhergestellt.  Dies ist wichtig, wenn das Formular mehr als einen <xref:System.ComponentModel.BackgroundWorker> hostet.  Beachten Sie weiterhin, dass im <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler keine Benutzeroberflächenobjekte bearbeitet werden dürfen.  Verwenden Sie stattdessen zum Kommunizieren mit der Benutzeroberfläche die <xref:System.ComponentModel.BackgroundWorker>\-Ereignisse.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  Fügen Sie im <xref:System.Windows.Forms.Control.Click>\-Ereignishandler des `startAsyncButton`\-Steuerelements den Code hinzu, mit dem die asynchrone Operation gestartet wird.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  Weisen Sie im <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignishandler das Ergebnis der Berechnung dem `resultLabel`\-Steuerelement zu.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## Hinzufügen von Fortschrittsberichterstellung und Abbruchunterstützung  
 Bei asynchronen Operationen, die lange dauern, ist es häufig wünschenswert, dem Benutzer den Fortschritt mitzuteilen und es ihm zu ermöglichen, die Operation abzubrechen.  Die <xref:System.ComponentModel.BackgroundWorker>\-Klasse stellt ein Ereignis bereit, mit dem Sie den Fortschritt aufzeichnen können, während die Operation im Hintergrund ausgeführt wird.  Darüber hinaus verfügt sie über ein Flag, mit dem der Workercode einen Aufruf an <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> erkennen und sich selbst unterbrechen kann.  
  
#### So implementieren Sie die Fortschrittsberichterstellung  
  
1.  Wählen Sie im **Eigenschaftenfenster** `backgroundWorker1` aus.  Legen Sie die <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A>\-Eigenschaft und die <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>\-Eigenschaft auf `true` fest.  
  
2.  Deklarieren Sie zwei Variablen im `FibonacciCalculator`\-Formular.  Diese werden verwendet, um den Fortschritt zu verfolgen.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  Fügen Sie einen Ereignishandler für das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignis hinzu.  Aktualisieren Sie im <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignishandler die <xref:System.Windows.Forms.ProgressBar> mit der <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A>\-Eigenschaft des <xref:System.ComponentModel.ProgressChangedEventArgs>\-Parameters.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### So implementieren Sie die Abbruchunterstützung  
  
1.  Fügen Sie im <xref:System.Windows.Forms.Control.Click>\-Ereignishandler des `cancelAsyncButton`\-Steuerelements den Code hinzu, mit dem die asynchrone Operation abgebrochen wird.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]  
  
2.  Die folgenden Codefragmente in der `ComputeFibonacci`\-Methode dienen zur Fortschrittsberichterstellung und Abbruchunterstützung.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]  
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]  
  
## Checkpoint  
 An diesem Punkt können Sie die Fibonacci\-Berechnung kompilieren und ausführen.  
  
#### So testen Sie das Projekt  
  
-   Drücken Sie F5, um die Anwendung zu kompilieren und auszuführen.  
  
     Während die Berechnung ausgeführt wird, wird in der <xref:System.Windows.Forms.ProgressBar> der Fortschritt der Berechnung angezeigt.  Sie können die anstehende Operation auch abbrechen.  
  
     Bei kleinen Zahlen sollte die Berechnung sehr schnell gehen, während bei großen Zahlen eine deutliche Verzögerung erkennbar ist.  Wenn Sie einen Wert von 30 oder höher eingeben, sollten Sie je nach Geschwindigkeit des Computers eine Verzögerung von mehreren Sekunden bemerken.  Bei Werten über 40 dauert die Berechnung möglicherweise Minuten oder Stunden.  Beachten Sie, dass Sie während der Berechnung einer großen Fibonacci\-Zahl das Formular dennoch beliebig verschieben, minimieren, maximieren oder sogar schließen können.  Der Grund dafür ist, dass der primäre UI\-Thread nicht auf die Fertigstellung der Berechnung wartet.  
  
## Nächste Schritte  
 Nachdem Sie ein Formular implementiert haben, dass eine <xref:System.ComponentModel.BackgroundWorker>\-Komponente für eine Berechnung im Hintergrund verwendet, können Sie weitere Möglichkeiten für asynchrone Operationen ausprobieren:  
  
-   Verwenden Sie mehrere <xref:System.ComponentModel.BackgroundWorker>\-Objekte für mehrere gleichzeitige Operationen.  
  
-   Informationen zum Debuggen der Multithreadanwendung finden Sie unter [Gewusst wie: Verwenden des Fensters Threads](../Topic/How%20to:%20Use%20the%20Threads%20Window.md).  
  
-   Implementieren Sie Ihre eigene Komponente, die das asynchrone Programmiermodell unterstützt.  Weitere Informationen finden Sie unter [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
    > [!CAUTION]
    >  Wenn Sie Multithreading verwenden, setzen Sie sich möglicherweise sehr ernsten und komplexen Problemen aus.  Schlagen Sie unter [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) nach, bevor Sie eine Projektmappe implementieren, die Multithreading verwendet.  
  
## Siehe auch  
 <xref:System.ComponentModel.BackgroundWorker>   
 [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md)   
 [Multithreading in Components](../Topic/Multithreading%20in%20Components.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/de-de/c731a50c-09c1-4468-9646-54c86b75d269)   
 [Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)   
 [BackgroundWorker\-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
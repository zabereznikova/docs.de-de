---
title: "Gewusst wie: Threadsicheres Aufrufen von Windows Forms-Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHInvalidOperation.WinForms.IllegalCrossThreadCall"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Threadsicherheit, Aufrufen von Steuerelementen [Windows Forms]"
  - "Aufrufen von Steuerelementen, Threadsicherheit [Windows Forms]"
  - "CheckForIllegalCrossThreadCalls-Eigenschaft [Windows Forms]"
  - "Steuerelemente für Windows Forms, Multithreading"
  - "BackgroundWorker-Klasse, Beispiele"
  - "Threading [Windows Forms], threadübergreifende Aufrufe"
  - "Steuerelemente [Windows Forms], Multithreading"
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Threadsicheres Aufrufen von Windows Forms-Steuerelementen
Bei Verwendung von Multithreading zur Verbesserung der Leistung von Windows Forms\-Anwendungen müssen Sie sicherstellen, dass Sie die Steuerelemente auf threadsichere Weise aufrufen.  
  
 Zugriff auf Windows Forms\-Steuerelemente ist nicht grundsätzlich threadsicher. Wenn Sie mit zwei oder mehr Threads den Zustand eines Steuerelements verändern, ist es möglich, das Steuerelement in eine inkonsistenten Zustand zu versetzen. Andere Fehler in Bezug auf Threads sind möglich, z. B. Racebedingungen und Deadlocks. Es ist wichtig, sicherzustellen, dass der Zugriff auf die Steuerelemente auf threadsichere Weise erfolgt.  
  
 Es ist unsicher, ein Steuerelement von einem anderen Thread als dem aufzurufen, der das Steuerelement erstellt hat, ohne die <xref:System.Windows.Forms.Control.Invoke%2A>\-Methode zu verwenden. Es folgt ein Beispiel für einen Aufruf, der nicht threadsicher ist.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#6)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#6)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#6)]  
  
 Mit [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] können Sie feststellen, wann Sie auf die Steuerelemente auf nicht threadsichere Weise zugreifen. Wenn Sie die Anwendung im Debugger ausführen und ein anderer Thread als der, der ein Steuerelement erstellt hat, versucht, das Steuerelement aufzurufen, löst der Debugger eine <xref:System.InvalidOperationException> mit einer Meldung wie "Zugriff auf Steuerelement *Steuerelementname* von einem anderen Thread als dem Erstellungsthread" aus.  
  
 Diese Ausnahme tritt zuverlässig beim Debuggen und unter bestimmten Bedingungen zur Laufzeit auf. Diese Ausnahme wird möglicherweise angezeigt, wenn Sie Anwendungen debuggen, die Sie mit [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] vor [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] geschrieben haben. Es wird dringend empfohlen, dieses Problem ggf. zu beheben. Sie können es aber deaktivieren, indem Sie die <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A>\-Eigenschaft auf `false` festlegen. Dies bewirkt, dass das Steuerelement wie unter Visual Studio .NET 2003 und [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)] ausgeführt wird.  
  
> [!NOTE]
>  Wenn Sie ActiveX\-Steuerelemente in einem Formular verwenden, erhalten Sie möglicherweise die threadübergreifende <xref:System.InvalidOperationException> beim Ausführen im Debugger. In diesem Fall unterstützt das ActiveX\-Steuerelement kein Multithreading. Weitere Informationen zum Verwenden von ActiveX\-Steuerelementen mit Windows Forms finden Sie unter [Windows Forms und nicht verwaltete Anwendungen](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md). Wenn Sie Visual Studio verwenden, können Sie diese Ausnahme verhindern, indem Sie den Visual Studio\-Hostprozess deaktivieren. Informationen hierzu finden Sie unter [Gewusst wie: Deaktivieren des Hostprozesses](../Topic/How%20to:%20Disable%20the%20Hosting%20Process.md).  
  
## Threadsichere Aufrufe von Windows Forms\-Steuerelementen  
  
#### So führen Sie einen threadsicheren Aufruf des Windows Forms\-Steuerelements aus  
  
1.  Fragen Sie die <xref:System.Windows.Forms.Control.InvokeRequired%2A>\-Eigenschaft des Steuerelements ab.  
  
2.  Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A>`true` zurückgibt, rufen Sie <xref:System.Windows.Forms.Control.Invoke%2A> mit einem Delegaten auf, der den eigentlichen Aufruf des Steuerelements übernimmt.  
  
3.  Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A>`false` zurückgibt, rufen Sie das Steuerelement direkt auf.  
  
 Im folgenden Codebeispiel wird ein threadsicherer Aufruf in der `ThreadProcSafe`\-Methode implementiert, die vom Hintergrundthread ausgeführt wird. Wenn das <xref:System.Windows.Forms.TextBox> des <xref:System.Windows.Forms.Control.InvokeRequired%2A>\-Steuerelements `true` zurückgibt, erstellt die `ThreadProcSafe`\-Methode eine Instanz von `SetTextCallback` und übergibt sie an die <xref:System.Windows.Forms.Control.Invoke%2A>\-Methode des Formulars. Dies bewirkt, dass die `SetText`\-Methode in dem Thread aufgerufen wird, der das <xref:System.Windows.Forms.TextBox>\-Steuerelement erstellt hat, und in diesem Threadkontext wird die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft direkt festgelegt.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#7)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#7)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#3)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#8)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#8)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#8)]  
  
## threadsichere Aufrufe mit BackgroundWorker  
 Das bevorzugte Verfahren zum Implementieren von Multithreading in der Anwendung ist die Verwendung der <xref:System.ComponentModel.BackgroundWorker>\-Komponente. Die <xref:System.ComponentModel.BackgroundWorker>\-Komponente verwendet ein ereignisgesteuertes Modell für Multithreading. Der Hintergrundthread führt den <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler aus, und der Thread, der die Steuerelemente erstellt, führt die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\- und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignishandler aus. Sie können die Steuerelemente von den <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\- und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignishandlern aus aufrufen.  
  
#### So führen Sie threadsichere Aufrufe mit BackgroundWorker durch  
  
1.  Erstellen Sie eine Methode zur Ausführung der Arbeit, die im Hintergrundthread ausgeführt werden soll. Rufen Sie keine Steuerelemente auf, die vom Hauptthread in dieser Methode erstellt wurden.  
  
2.  Erstellen Sie eine Methode, um die Ergebnisse der Hintergrundverarbeitung nach Abschluss zu melden. Sie können durch den Hauptthread in dieser Methode erstellte Steuerelemente aufrufen.  
  
3.  Binden Sie die in Schritt 1 erstellte Methode an das <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignis einer Instanz von <xref:System.ComponentModel.BackgroundWorker>, und binden Sie die in Schritt 2 erstellte Methode an das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignis der gleichen Instanz.  
  
4.  Um den Hintergrundthread zu starten, rufen Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>\-Methode der <xref:System.ComponentModel.BackgroundWorker>\-Instanz auf.  
  
 Im folgenden Codebeispiel verwendet der <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler <xref:System.Threading.Thread.Sleep%2A>, um Arbeit zu simulieren, die einige Zeit dauert. Das <xref:System.Windows.Forms.TextBox>\-Steuerelement des Formulars wird nicht aufgerufen. Die <xref:System.Windows.Forms.TextBox>\-Eigenschaft des <xref:System.Windows.Forms.Control.Text%2A>\-Steuerelements wird direkt im <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignishandler festgelegt.  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#5)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#5)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#5)]  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#9)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#9)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#9)]  
  
 Sie können auch den Fortschritt einer Hintergrundaufgabe mithilfe des <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignisses melden. Ein Beispiel, das das Ereignis enthält, finden Sie unter <xref:System.ComponentModel.BackgroundWorker>.  
  
## Beispiel  
 Das folgende Codebeispiel stellt eine vollständige Windows Forms\-Anwendung dar, die aus einem Formular mit drei Schaltflächen und einem Textfeld besteht. Die erste Schaltfläche zeigt den unsicheren threadübergreifenden Zugriff, die zweite Schaltfläche zeigt den sicheren Zugriff mithilfe von <xref:System.Windows.Forms.Control.Invoke%2A>, und die dritte Schaltfläche zeigt den sicheren Zugriff mithilfe von <xref:System.ComponentModel.BackgroundWorker>.  
  
> [!NOTE]
>  Anweisungen zum Ausführen des Beispiels finden Sie unter [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/de-de/cc447f7e-4c3b-4397-9d05-aeba3ca49416). Dieses Beispiel erfordert Verweise auf die Assemblys "System.Drawing" und "System.Windows.Forms".  
  
 [!code-cpp[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CrossThreadCalls#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CrossThreadCalls/VB/Form1.vb#1)]  
  
 Wenn Sie die Anwendung ausführen und auf die Schaltfläche **Unsafe Call** klicken, wird sofort "Written by the main thread" im Textfeld angezeigt. Wenn zwei Sekunden später der unsichere Aufruf versucht wird, gibt der Visual Studio\-Debugger an, dass eine Ausnahme aufgetreten ist. Der Debugger hält bei der Zeile im Hintergrundthread an, die versucht hat, direkt in das Textfeld zu schreiben. Sie müssen die Anwendung neu starten, um die anderen zwei Schaltflächen zu testen. Wenn Sie auf die Schaltfläche **Safe Call** klicken, wird "Written by the main thread" im Textfeld angezeigt. Zwei Sekunden später wird das Textfeld auf "Written by the background thread \(Invoke\)" festgelegt. Dadurch wird angegeben, dass die <xref:System.Windows.Forms.Control.Invoke%2A>\-Methode aufgerufen wurde. Wenn Sie auf die Schaltfläche **Safe BW Call** klicken, wird "Written by the main thread" im Textfeld angezeigt. Zwei Sekunden später wird das Textfeld auf "Written by the main thread after the background thread completed" festgelegt, Dadurch wird angegeben, dass der Handler für das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignis von <xref:System.ComponentModel.BackgroundWorker> aufgerufen wurde.  
  
## Robuste Programmierung  
  
> [!CAUTION]
>  Wenn Sie eine beliebige Art von Multithreading verwenden, kann Ihr Code sehr ernsthaften und komplexen Fehlern ausgesetzt sein. Weitere Informationen finden Sie unter [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md), bevor Sie eine Lösung implementieren, die Multithreading verwendet.  
  
## Siehe auch  
 <xref:System.ComponentModel.BackgroundWorker>   
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Entwickeln benutzerdefinierter Windows Forms\-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Windows Forms und nicht verwaltete Anwendungen](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)
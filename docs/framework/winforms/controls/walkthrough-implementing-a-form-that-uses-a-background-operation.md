---
title: 'Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
ms.openlocfilehash: 435bc1c04bfd2f9b8a94ff8151369b5ef2fae6f8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385871"
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a>Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet
Wenn Sie einen Vorgang, der viel Zeit in Anspruch nehmen wird, und Sie nicht Ihre Benutzeroberfläche (UI) nicht mehr reagiert möchten oder "hängen", Sie können die <xref:System.ComponentModel.BackgroundWorker> Klasse, um den Vorgang in einem anderen Thread auszuführen.  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit der <xref:System.ComponentModel.BackgroundWorker> -Klasse Ausführen zeitintensiver Berechnungen "im Hintergrund", während die Benutzeroberfläche reaktionsfähig bleibt.  Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, verfügen Sie über eine Anwendung, die Fibonacci-Zahlen asynchron berechnet. Obwohl das Berechnen einer großen Fibonacci-Zahl merklich Zeit in Anspruch nimmt, wird der Haupt-UI-Thread nicht von dieser Verzögerung unterbrochen, und das Formular behält während der Berechnung seine Reaktionsfähigkeit.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen einer Windows-basierten Anwendung  
  
-   Erstellen einer <xref:System.ComponentModel.BackgroundWorker> in Ihrem Formular  
  
-   Hinzufügen Asynchroner Ereignishandler  
  
-   Hinzufügen von Statusberichterstellung und Abbruchunterstützung  
  
 Eine vollständige Liste des in diesem Beispiel verwendeten Codes finden Sie unter [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-a-form-that-uses-a-background-operation"></a>So erstellen Sie ein Formular, das eine Hintergrundoperation verwendet  
  
1.  Erstellen Sie ein Windows-basierten Anwendung mit dem Namen `BackgroundWorkerExample` (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).  
  
2.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Form1**, und wählen Sie im Kontextmenü **Umbenennen** aus. Ändern Sie den Dateinamen in `FibonacciCalculator`. Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement `Form1` umbenannt werden sollen.  
  
3.  Ziehen Sie eine <xref:System.Windows.Forms.NumericUpDown> -Steuerelement aus der **Toolbox** auf das Formular. Legen Sie die <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> Eigenschaft `1` und die <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> Eigenschaft `91`.  
  
4.  Hinzufügen von zwei <xref:System.Windows.Forms.Button> Steuerelemente im Formular.  
  
5.  Benennen Sie das erste <xref:System.Windows.Forms.Button> Steuerelement `startAsyncButton` und legen Sie die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft `Start Async`. Benennen Sie das zweite <xref:System.Windows.Forms.Button> Steuerelement `cancelAsyncButton`, und legen Sie die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft `Cancel Async`. Legen Sie dessen <xref:System.Windows.Forms.Control.Enabled%2A> Eigenschaft `false`.  
  
6.  Erstellen Sie einen Ereignishandler für beide die <xref:System.Windows.Forms.Button> Steuerelemente <xref:System.Windows.Forms.Control.Click> Ereignisse. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern mithilfe des Designers](https://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
7.  Ziehen Sie eine <xref:System.Windows.Forms.Label> -Steuerelement aus der **Toolbox** auf das Formular und benennen Sie sie `resultLabel`.  
  
8.  Ziehen Sie eine <xref:System.Windows.Forms.ProgressBar> -Steuerelement aus der **Toolbox** auf das Formular.  
  
## <a name="creating-a-backgroundworker-in-your-form"></a>Erstellen von „BackgroundWorker“ in Ihrem Formular  
 Sie erstellen die <xref:System.ComponentModel.BackgroundWorker> für asynchrone Vorgänge mithilfe der **Windows** **Formulardesigner**.  
  
#### <a name="to-create-a-backgroundworker-with-the-designer"></a>So erstellen Sie „BackgroundWorker“ mithilfe des Designers  
  
-   Von der **Komponenten** Registerkarte die **Toolbox**, ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker> auf das Formular.  
  
## <a name="adding-asynchronous-event-handlers"></a>Hinzufügen Asynchroner Ereignishandler  
 Sie sind jetzt bereit zum Hinzufügen der Ereignishandler für die <xref:System.ComponentModel.BackgroundWorker> asynchrone Ereignisse der Komponente. Der zeitaufwändige Vorgang im Hintergrund, der die Fibonacci-Zahlen berechnet, wird von einem dieser Ereignishandler aufgerufen.  
  
#### <a name="to-implement-asynchronous-event-handlers"></a>So implementieren Sie asynchrone Ereignishandler  
  
1.  In der **Eigenschaften** Fenster mit den <xref:System.ComponentModel.BackgroundWorker> -Komponente noch ausgewählt ist, klicken Sie auf die **Ereignisse** Schaltfläche. Doppelklicken Sie auf die <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignisse an den Ereignishandler zu erstellen. Informationen zur Verwendung von Ereignishandlern finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern mithilfe des Designers](https://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
2.  Erstellen Sie im Formular eine neue Methode namens `ComputeFibonacci`. Diese Methode führt die eigentliche Arbeit aus und wird im Hintergrund ausgeführt. Dieser Code veranschaulicht die rekursive Umsetzung des Fibonacci-Algorithmus, der deutlich ineffizient ist und wesentlich mehr Zeit in Anspruch nimmt, große Zahlen abzuschließen. Er wird hier verwendet, um einen Vorgang zu veranschaulichen, der lange Verzögerungen in der Anwendung verursachen kann.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  In der <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignishandler einen Aufruf von der `ComputeFibonacci` Methode. Übernehmen Sie den ersten Parameter für `ComputeFibonacci` aus der <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> Eigenschaft der <xref:System.ComponentModel.DoWorkEventArgs>. Die <xref:System.ComponentModel.BackgroundWorker> und <xref:System.ComponentModel.DoWorkEventArgs> Parameter werden später für statusberichterstellung und abbruchunterstützung verwendet werden zu unterstützen. Weisen Sie den Rückgabewert von `ComputeFibonacci` auf die <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> Eigenschaft der <xref:System.ComponentModel.DoWorkEventArgs>. Dieses Ergebnis stehen die <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.  
  
    > [!NOTE]
    >  Die <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignishandler verweist nicht auf die `backgroundWorker1` auf die Instanzvariable direkt, da dieser Ereignishandler mit einer bestimmten Instanz des gekoppelt wird <xref:System.ComponentModel.BackgroundWorker>. Stattdessen einen Verweis auf die <xref:System.ComponentModel.BackgroundWorker> , ausgelöst hat dies Ereignis wiederhergestellt wird, aus der `sender` Parameter. Dies ist wichtig, wenn das Formular mehr als eine hostet <xref:System.ComponentModel.BackgroundWorker>. Es ist auch wichtig, nicht zum Bearbeiten von UI-Objekte in Ihrem <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignishandler. Kommunizieren Sie stattdessen mit der Benutzeroberfläche, über die <xref:System.ComponentModel.BackgroundWorker> Ereignisse.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  In der `startAsyncButton` des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignishandler, fügen Sie den Code, der den asynchronen Vorgang startet.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  In der <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignishandler, weisen Sie das Ergebnis dieser Berechnung der `resultLabel` Steuerelement.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## <a name="adding-progress-reporting-and-support-for-cancellation"></a>Hinzufügen von Statusberichterstellung und Abbruchunterstützung  
 Bei asynchronen Vorgängen, die viel Zeit in Anspruch nehmen, ist es oft ratsam, dem Benutzer den Fortschritt zu berichten und die Möglichkeit zu geben, den Vorgang abzubrechen. Die <xref:System.ComponentModel.BackgroundWorker> -Klasse stellt ein Ereignis, das Ihnen ermöglicht, Posten Fortschritt als Ihre Hintergrundvorgang ausgeführt wird. Es stellt auch ein Flag, das von Ihrem Code einen Aufruf von erkennen <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> zu identifizieren und selbst.  
  
#### <a name="to-implement-progress-reporting"></a>So implementieren Sie Statusberichterstellung  
  
1.  Wählen Sie im Fenster **Eigenschaften** `backgroundWorker1` aus. Legen Sie für die Eigenschaften <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> (Breite) und <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> (Höhe) den Wert `true` fest.  
  
2.  Deklarieren Sie zwei Variablen im Formular `FibonacciCalculator`. Diese werden verwendet, um den Fortschritt nachzuverfolgen.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  Fügen Sie einen Ereignishandler für das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignis hinzu. In der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> -Ereignishandler, Aktualisieren der <xref:System.Windows.Forms.ProgressBar> mit der <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> Eigenschaft der <xref:System.ComponentModel.ProgressChangedEventArgs> Parameter.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### <a name="to-implement-support-for-cancellation"></a>So implementieren Sie die Abbruchunterstützung  
  
1.  In der `cancelAsyncButton` des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignishandler, fügen Sie den Code, der den asynchronen Vorgang abbricht.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]  
  
2.  Die folgenden Codefragmente in der Methode `ComputeFibonacci` berichten Fortschritt und Abbruchunterstützung.  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]  
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]  
  
## <a name="checkpoint"></a>Checkpoint  
 An diesem Punkt können Sie die Anwendung Fibonacci Calculator kompilieren.  
  
#### <a name="to-test-your-project"></a>So testen Sie Ihr Projekt  
  
-   Drücken Sie F5, um die Anwendung zu kompilieren und auszuführen.  
  
     Während die Berechnung im Hintergrund ausgeführt wird, wird Ihnen die <xref:System.Windows.Forms.ProgressBar> nun der Status angezeigt, der Berechnung bis zum Abschluss. Sie können auch ausstehenden Vorgang auch abbrechen.  
  
     Bei kleinen Zahlen sollte die Berechnung sehr schnell sein, aber bei größeren Zahlen sollten Sie eine merkliche Verzögerung feststellen. Wenn Sie einen Wert von 30 oder höher eingeben, sollten Sie, abhängig von Ihrem Computer, eine Verzögerung von mehreren Sekunden feststellen. Bei Werten, die höher als 40 sind, kann es Minuten oder Stunden dauern, die Berechnung abzuschließen. Beachten Sie, dass Sie das Formular frei verschieben, minimieren, maximieren und sogar schließen, während der Rechner eine hohe Fibonacci-Zahl berechnet. Dies liegt daran, dass der Haupt-UI-Thread nicht wartet, bis die Berechnung abgeschlossen ist.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Nun, da Sie ein Formular implementiert haben, die verwendet eine <xref:System.ComponentModel.BackgroundWorker> Komponente, um eine Berechnung im Hintergrund ausführen können Sie andere Möglichkeiten für asynchrone Vorgänge untersuchen:  
  
-   Verwenden Sie mehrere <xref:System.ComponentModel.BackgroundWorker> Objekte für mehrere gleichzeitige Vorgänge.  
  
-   Informationen zum Debuggen Ihrer Multithreadanwendung finden Sie unter [Vorgehensweise: Verwenden des Fensters „Threads“](/visualstudio/debugger/how-to-use-the-threads-window).  
  
-   Implementieren Sie eine eigene Komponente, die das asynchrone Programmiermodell unterstützt. Weitere Informationen finden Sie unter [Übersicht über ereignisbasierte asynchrone Muster](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
    > [!CAUTION]
    >  Wenn Sie Multithreading verwenden, setzen Sie sich möglicherweise sehr ernsten und komplexen Problemen aus. Beachten Sie die Informationen unter [Empfohlene Vorgehensweise für das verwaltete Threading](../../../../docs/standard/threading/managed-threading-best-practices.md), bevor Sie eine Projektmappe implementieren, die Multithreading verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Empfohlene Vorgehensweise für das verwaltete Threading](../../../../docs/standard/threading/managed-threading-best-practices.md)  
 [Multithreading in Komponenten](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [NICHT IM BUILD: Multithreading in Visual Basic](https://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 [BackgroundWorker-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md)

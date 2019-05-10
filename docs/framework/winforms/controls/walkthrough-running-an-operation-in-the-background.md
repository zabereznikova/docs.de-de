---
title: 'Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund'
ms.date: 03/30/2017
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
ms.openlocfilehash: 6c705c6d6ff9bbd233bbddc3a73acf8aca13a547
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211526"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund

Gibt es einen Vorgang, der bis zu seinem Abschluss eine lange Zeit in Anspruch nimmt, und Sie möchten keine Verzögerungen in der Benutzeroberfläche verursachen, können Sie die <xref:System.ComponentModel.BackgroundWorker>-Klasse dazu verwenden, den Vorgang über einen anderen Thread auszuführen.

Eine vollständige Liste des Codes in diesem Beispiel verwendet, finden Sie unter [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md).

## <a name="run-an-operation-in-the-background"></a>Ausführen eines Vorgangs im Hintergrund

1. Mit dem Formular in Windows Forms-Designer in Visual Studio aktiv ist, ziehen Sie zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular, und legen Sie dann die `Name` und <xref:System.Windows.Forms.Control.Text%2A> Eigenschaften der Schaltflächen gemäß der in der folgenden Tabelle.

    |Schaltfläche|Name|Text|
    |------------|----------|----------|
    |`button1`|`startBtn`|**Starten**|
    |`button2`|`cancelBtn`|**Kündigung**|

2. Öffnen der **Toolbox**, klicken Sie auf die **Komponenten** Registerkarte, und ziehen Sie dann die <xref:System.ComponentModel.BackgroundWorker> -Komponente auf das Formular.

     Die `backgroundWorker1` Komponente angezeigt wird, der **Komponentenleiste**.

3. Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> auf `true`fest.

4. In der **Eigenschaften** Fenster, klicken Sie auf die **Ereignisse** Schaltfläche, und doppelklicken Sie dann auf die <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignisse an den Ereignishandler zu erstellen.

5. Fügen Sie den zeitaufwendigen Code in die <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignishandler.

6. Extrahieren Sie alle Parameter, die erforderlich sind, durch den Vorgang aus der <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> Eigenschaft der <xref:System.ComponentModel.DoWorkEventArgs> Parameter.

7. Weisen Sie das Ergebnis der Berechnung, die <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> Eigenschaft der <xref:System.ComponentModel.DoWorkEventArgs>.

     Dies wird zur Verfügung, die <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. Fügen Sie Code für das Ergebnis des Vorgangs im Abrufen der <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. Implementieren Sie die `TimeConsumingOperation`-Methode.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. Doppelklicken Sie in der Windows Forms-Designer auf `startButton` zum Erstellen der <xref:System.Windows.Forms.Control.Click> -Ereignishandler.

11. Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> -Methode in der die <xref:System.Windows.Forms.Control.Click> -Ereignishandler für `startButton`.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. Doppelklicken Sie in der Windows Forms-Designer auf `cancelButton` zum Erstellen der <xref:System.Windows.Forms.Control.Click> -Ereignishandler.

13. Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> -Methode in der die <xref:System.Windows.Forms.Control.Click> -Ereignishandler für `cancelButton`.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. Importieren Sie am Anfang der Datei die System.ComponentModel-Namespace und den System.Threading-Namespaces.

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. Drücken Sie die **F6** zum Erstellen der Projektmappe, und drücken dann die **STRG**+**F5** zum Ausführen der Anwendung außerhalb des Debuggers.

    > [!NOTE]
    > Wenn Sie drücken **F5** um die Anwendung im Debugger ausführen, die Ausnahme ausgelöst hat, der `TimeConsumingOperation` Methode abgefangen und vom Debugger angezeigt wird. Beim Ausführen der Anwendung außerhalb des Debuggers der <xref:System.ComponentModel.BackgroundWorker> wird die Ausnahme behandelt und speichert Sie in der <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> Eigenschaft der <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.

16. Klicken Sie auf die **starten** Schaltfläche, um einen asynchronen Vorgang auszuführen, und klicken Sie dann auf die **Abbrechen** Schaltfläche, um einen aktiven asynchronen Vorgang zu beenden.

     Das Ergebnis jedes Vorgangs wird in einem <xref:System.Windows.Forms.MessageBox>-Steuerelement angezeigt.

## <a name="next-steps"></a>Nächste Schritte

- Implementieren eines Formulars, das einen Status meldet, wie ein asynchroner Vorgang wird fortgesetzt. Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](how-to-implement-a-form-that-uses-a-background-operation.md).

- Implementieren Sie eine Klasse, die das asynchrone Muster für Komponenten unterstützt. Weitere Informationen finden Sie unter [Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md)
- [BackgroundWorker-Komponente](backgroundworker-component.md)

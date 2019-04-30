---
title: 'Vorgehensweise: Threadsichere Aufrufe von Windows Forms-Steuerelementen'
ms.date: 02/19/2019
dev_langs:
- csharp
- vb
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: 3211df1f0e585780039471b80b5b913613ad9bbd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913795"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Vorgehensweise: Threadsichere Aufrufe von Windows Forms-Steuerelementen

Multithreading kann die Leistung von Windows Forms-Anwendungen verbessern, aber den Zugriff auf Windows Forms-Steuerelemente nicht grundsätzlich threadsicher ist. Multithreading kann Ihr Code sehr ernsthaften und komplexen Fehlern verfügbar machen. Zwei oder mehr Threads, die ein Steuerelement bearbeiten können erzwingen, dass das Steuerelement in einem inkonsistenten Zustand und dazu führen, dass Racebedingungen, Deadlocks und Einfrieren oder hängt. Wenn Sie implementieren multithreading in Ihrer app werden Sie sicher, dass threadübergreifenden-Steuerelemente auf threadsichere Weise aufrufen. Weitere Informationen finden Sie unter [Managed threading best Practices](../../../standard/threading/managed-threading-best-practices.md). 

Es gibt zwei Möglichkeiten, ein Windows Forms-Steuerelement sicher von einem anderen Thread aufrufen können, die das Steuerelement erstellt haben. Sie können die <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> Methode zum Aufrufen eines Delegaten erstellt im Hauptthread, das wiederum das Steuerelement aufruft. Oder Implementieren einer <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, die ein ereignisgesteuertes Modell verwendet, um Arbeit, die von der berichterstellung für die Ergebnisse im Hintergrundthread zu trennen. 

## <a name="unsafe-cross-thread-calls"></a>Unsichere threadübergreifende Aufrufe

Es ist unsicher, ein Steuerelement direkt von einem anderen Thread aufrufen, die sie erstellt haben. Der folgende Codeausschnitt veranschaulicht einen unsichere Aufruf der <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> Steuerelement. Die `Button1_Click` -Ereignishandler erstellt ein neues `WriteTextUnsafe` Thread, der des Hauptthread des legt <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> -Eigenschaft direkt. 

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

Visual Studio-Debugger erkennt diese threadaufrufe unsichere durch Auslösen einer <xref:System.InvalidOperationException> mit der Meldung **threadübergreifender Vorgang ungültig. Steuerelement "" zugegriffen werden, von einem anderen Thread als dem Thread, der es erstellt wurde.** Die <xref:System.InvalidOperationException> immer tritt bei unsicheren threadübergreifende Aufrufe, während des Debuggens von Visual Studio, und zur app-Laufzeit auftreten. Sie sollten das Problem beheben, aber Sie können die Ausnahme deaktivieren, durch Festlegen der <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> Eigenschaft `false`.

## <a name="safe-cross-thread-calls"></a>Sichere threadübergreifende Aufrufe 

Die folgenden Codebeispiele veranschaulichen zwei Möglichkeiten, ein Windows Forms-Steuerelement sicher von einem anderen Thread aufrufen können, die sie erstellt haben: 
1. Die <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> -Methode, die einen Delegaten, über den Hauptthread aufruft, das Steuerelement aufzurufen. 
2. Ein <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> -Komponente, die ein ereignisgesteuertes Modell bietet. 

In beiden Beispielen funktioniert der Background Thread ruht für eine Sekunde, um zu simulieren, in diesem Thread ausgeführt wird. 

Können Sie erstellen und Ausführen dieser Beispiele als .NET Framework-apps aus dem C# oder Visual Basic über die Befehlszeile. Weitere Informationen finden Sie unter [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [erstellen über die Befehlszeile (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

Ab .NET Core 3.0, Sie können auch erstellen und Ausführen der Beispiele als Windows .NET Core-apps aus einem Ordner, die eine .NET Core Windows Forms  *\<Ordnername > .csproj* Projektdatei. 

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Beispiel: Verwenden Sie die Invoke-Methode mit einem Delegaten

Das folgende Beispiel zeigt ein Muster zum Sicherstellen der threadsichere Aufrufe an eine Windows Forms-Steuerelement. Fragt die <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> -Eigenschaft, die das Steuerelement vergleicht die Thread-ID an den aufrufenden Thread-ID erstellen Wenn der Thread-IDs identisch sind, werden das Steuerelement direkt aufruft. Wenn der Thread-IDs unterscheiden, ruft es die <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> Methode mit einem Delegaten über den Hauptthread, der den eigentlichen Aufruf an das Steuerelement übernimmt.

Die `SafeCallDelegate` Einstellung ermöglicht die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft. Die `WriteTextSafe` Methodenabfragen <xref:System.Windows.Forms.Control.InvokeRequired%2A>. Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A> gibt `true`, `WriteTextSafe` übergibt die `SafeCallDelegate` auf die <xref:System.Windows.Forms.Control.Invoke%2A> Methode, um den eigentlichen Aufruf des Steuerelements. Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A> gibt `false`, `WriteTextSafe` legt die <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> direkt. Die `Button1_Click` -Ereignishandler erstellt dann den neuen Thread und führt die `WriteTextSafe` Methode. 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Beispiel: Verwenden Sie einen BackgroundWorker-Ereignishandler

Eine einfache Möglichkeit zum Implementieren von multithreading ist mit der <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> Komponente, die ein ereignisgesteuertes Modell verwendet. Der Hintergrundthread führt den <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> -Ereignis, das den Hauptthread interagieren nicht. Im Hauptthread ausgeführt wird. die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> Ereignishandler, die Steuerelemente für den Hauptthread aufgerufen werden können.

Um einen threadsicheren Aufruf durch den Einsatz, <xref:System.ComponentModel.BackgroundWorker>, erstellen Sie eine Methode im Hintergrundthread für die Arbeit, und binden Sie es an der <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignis. Erstellen Sie eine andere Methode im Hauptthread melden die Ergebnisse der Hintergrundarbeit und binden Sie es an der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> oder <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignis. Rufen Sie zum Starten des Hintergrundthreads <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>. 

Im Beispiel wird die <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler zum Festlegen der <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft. Ein Beispiel mit der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis finden Sie unter <xref:System.ComponentModel.BackgroundWorker>. 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.BackgroundWorker>
- [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md)
- [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Entwickeln Sie benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)

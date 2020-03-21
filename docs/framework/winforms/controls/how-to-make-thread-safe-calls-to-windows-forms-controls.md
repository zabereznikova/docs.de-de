---
title: Threadsichere Aufrufe von Steuerelementen
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
ms.openlocfilehash: 365b1acb693b9ff2be603a3e659ed8d846a7696a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142003"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Gewusst wie: Threadsichere Aufrufe von Windows Forms-Steuerelementen durchführen

Multithreading kann die Leistung von Windows Forms-Apps verbessern, aber der Zugriff auf Windows Forms-Steuerelemente ist nicht von Natur aus threadsicher. Multithreading kann Ihren Code sehr ernsten und komplexen Fehlern aussetzen. Zwei oder mehr Threads, die ein Steuerelement manipulieren, können die Steuerung in einen inkonsistenten Zustand zwingen und zu Racebedingungen, Deadlocks und Einfrieren oder Hängen führen. Wenn Sie Multithreading in Ihrer App implementieren, stellen Sie sicher, dass Sie Threadübergreifende Steuerelemente threadsicher aufeine Threadsichere Weise aufrufen. Weitere Informationen finden Sie unter [Bewährte Methoden für verwaltetes Threading](../../../standard/threading/managed-threading-best-practices.md).

Es gibt zwei Möglichkeiten, ein Windows Forms-Steuerelement sicher von einem Thread aufzurufen, der dieses Steuerelement nicht erstellt hat. Sie können <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> die Methode verwenden, um einen im Hauptthread erstellten Delegaten aufzurufen, der wiederum das Steuerelement aufruft. Sie können auch <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>eine implementieren, die ein ereignisgesteuertes Modell verwendet, um die im Hintergrundthread ausgeführte Arbeit von der Berichterstattung über die Ergebnisse zu trennen.

## <a name="unsafe-cross-thread-calls"></a>Unsichere Crossthreadaufrufe

Es ist unsicher, ein Steuerelement direkt aus einem Thread aufzurufen, der es nicht erstellt hat. Der folgende Codeausschnitt veranschaulicht einen unsicheren Aufruf <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> des Steuerelements. Der `Button1_Click` Ereignishandler erstellt `WriteTextUnsafe` einen neuen Thread, der <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> die Eigenschaft des Hauptthreads direkt festlegt.

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

Der Visual Studio-Debugger erkennt diese unsicheren <xref:System.InvalidOperationException> Threadaufrufe, indem er eine mit der Nachricht, **Cross-Thread-Vorgang ungültig. Steuern Sie "" von einem anderen Thread als dem Thread, auf dem sie erstellt wurde.** Der <xref:System.InvalidOperationException> tritt immer bei unsicheren Threadübergreifenden Aufrufen während des Visual Studio-Debuggings auf und kann zur App-Laufzeit auftreten. Sie sollten das Problem beheben, aber Sie <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> können `false`die Ausnahme deaktivieren, indem Sie die Eigenschaft auf festlegen.

## <a name="safe-cross-thread-calls"></a>Sichere Cross-Thread-Aufrufe

Die folgenden Codebeispiele veranschaulichen zwei Möglichkeiten zum sicheren Aufrufen eines Windows Forms-Steuerelements aus einem Thread, der es nicht erstellt hat:

1. Die <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> Methode, die einen Delegaten aus dem Hauptthread aufruft, um das Steuerelement aufzurufen.
2. Eine <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> Komponente, die ein ereignisgesteuertes Modell bietet.

In beiden Beispielen schläft der Hintergrundthread eine Sekunde lang, um die in diesem Thread ausgeführte Arbeit zu simulieren.

Sie können diese Beispiele als .NET Framework-Apps über die Befehlszeile "C" oder "Visual Basic" erstellen und ausführen. Weitere Informationen finden Sie unter [Befehlszeilenerstellung mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Build über die Befehlszeile (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

Ab .NET Core 3.0 können Sie die Beispiele auch als Windows .NET Core-Apps aus einem Ordner mit dem Ordnernamen .NET Core Windows Forms * \<>.csproj-Projektdatei* erstellen und ausführen.

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Beispiel: Verwenden der Invoke-Methode mit einem Delegaten

Im folgenden Beispiel wird ein Muster zum Sicherstellen von threadsicheren Aufrufen eines Windows Forms-Steuerelements veranschaulicht. Es fragt <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> die Eigenschaft ab, die die Erstellen von Thread-ID des Steuerelements mit der aufrufenden Thread-ID vergleicht. Wenn die Thread-IDs identisch sind, ruft sie das Steuerelement direkt auf. Wenn die Thread-IDs unterschiedlich <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> sind, ruft sie die Methode mit einem Delegaten aus dem Hauptthread auf, wodurch der eigentliche Aufruf des Steuerelements ausgeführt wird.

Der `SafeCallDelegate` aktiviert <xref:System.Windows.Forms.TextBox> das Festlegen <xref:System.Windows.Forms.TextBox.Text%2A> der Eigenschaft des Steuerelements. Die `WriteTextSafe` Methodenabfragen <xref:System.Windows.Forms.Control.InvokeRequired%2A>. Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A> `true`zurückgegeben `WriteTextSafe` wird, wird die `SafeCallDelegate` an die <xref:System.Windows.Forms.Control.Invoke%2A> Methode zurückgegeben, um den tatsächlichen Aufruf des Steuerelements zu tätigen. Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A> `false`zurückgegeben `WriteTextSafe` wird, wird die <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> direkt festgelegt. Der `Button1_Click` Ereignishandler erstellt den neuen `WriteTextSafe` Thread und führt die Methode aus.

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Beispiel: Verwenden eines BackgroundWorker-Ereignishandlers

Eine einfache Möglichkeit, Multithreading <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> zu implementieren, ist mit der Komponente, die ein ereignisgesteuertes Modell verwendet. Der Hintergrundthread <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> führt das Ereignis aus, das nicht mit dem Hauptthread interagiert. Der Hauptthread <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> führt <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> die und-Ereignishandler aus, die die Steuerelemente des Hauptthreads aufrufen können.

Um einen threadsicheren Aufruf <xref:System.ComponentModel.BackgroundWorker>mithilfe von zu tätigen, erstellen Sie eine Methode im <xref:System.ComponentModel.BackgroundWorker.DoWork> Hintergrundthread, um die Arbeit zu erledigen, und binden Sie sie an das Ereignis. Erstellen Sie eine andere Methode im Hauptthread, um die Ergebnisse <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> der Hintergrundarbeit zu melden und an das oder-Ereignis zu binden. Um den Hintergrundthread <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>zu starten, rufen Sie auf .

Im Beispiel <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> wird der Ereignishandler verwendet, um die <xref:System.Windows.Forms.TextBox> Eigenschaft des Steuerelements <xref:System.Windows.Forms.TextBox.Text%2A> festzulegen. Ein Beispiel für <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> die <xref:System.ComponentModel.BackgroundWorker>Verwendung des Ereignisses finden Sie unter .

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ComponentModel.BackgroundWorker>
- [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md)
- [Gewusst wie: Implementieren eines Formulars, das einen Hintergrundvorgang verwendet](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)

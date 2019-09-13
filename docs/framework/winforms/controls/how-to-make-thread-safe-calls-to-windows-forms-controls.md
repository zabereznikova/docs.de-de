---
title: 'Vorgehensweise: Thread sichere Aufrufe an Windows Forms Steuerelemente erstellen'
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
ms.openlocfilehash: 78ad7b16d5220972a61848c0c80cd884afa842d9
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928619"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Vorgehensweise: Thread sichere Aufrufe an Windows Forms Steuerelemente erstellen

Multithreading kann die Leistung von Windows Forms-apps verbessern, aber der Zugriff auf Windows Forms-Steuerelemente ist nicht grundsätzlich Thread sicher. Multithreading kann Ihren Code für sehr ernste und komplexe Fehler verfügbar machen. Zwei oder mehr Threads, die ein Steuerelement bearbeiten, können das Steuerelement in einen inkonsistenten Zustand versetzen und zu Racebedingungen, Deadlocks und einfriert bzw. hängen. Wenn Sie Multithreading in der APP implementieren, stellen Sie sicher, dass Thread übergreifende Steuerelemente auf Thread sichere Weise aufgerufen werden. Weitere Informationen finden Sie unter [bewährte Methoden für das verwaltete Threading](../../../standard/threading/managed-threading-best-practices.md). 

Es gibt zwei Möglichkeiten, um ein Windows Forms-Steuerelement aus einem Thread, der dieses Steuerelement nicht erstellt hat, sicher aufzurufen. Sie können die <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> -Methode verwenden, um einen im Haupt Thread erstellten Delegaten aufzurufen, der wiederum das-Steuerelement aufruft. Sie können auch einen <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>implementieren, bei dem ein ereignisgesteuerte Modell verwendet wird, um im Hintergrund Thread durchgeführte Arbeiten von der Berichterstellung für die Ergebnisse zu trennen. 

## <a name="unsafe-cross-thread-calls"></a>Unsichere Thread übergreifende Aufrufe

Es ist unsicher, ein Steuerelement direkt von einem Thread aufzurufen, der ihn nicht erstellt hat. Der folgende Code Ausschnitt veranschaulicht einen unsicheren-Befehl für das <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> -Steuerelement. Der `Button1_Click` -Ereignishandler erstellt einen `WriteTextUnsafe` neuen Thread, der die- <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> Eigenschaft des Haupt Threads direkt festlegt. 

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

Der Visual Studio-Debugger erkennt diese unsicheren Thread Aufrufe, <xref:System.InvalidOperationException> **indem er mit der Meldung "Thread übergreifender Vorgang ungültig" aufruft. Das Steuerelement "", auf das von einem anderen Thread als dem erstellten Thread zugegriffen wird.** Der <xref:System.InvalidOperationException> tritt immer für unsichere Thread übergreifende Aufrufe während des Debuggens von Visual Studio auf und kann zur Laufzeit der app auftreten. Sie sollten das Problem beheben, aber Sie können die Ausnahme deaktivieren, indem Sie <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> die- `false`Eigenschaft auf festlegen.

## <a name="safe-cross-thread-calls"></a>Sichere Thread übergreifende Aufrufe 

Die folgenden Codebeispiele veranschaulichen zwei Möglichkeiten, um ein Windows Forms-Steuerelement aus einem Thread, der ihn nicht erstellt hat, sicher aufzurufen: 

1. Die <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> -Methode, die einen Delegaten vom Haupt Thread aufruft, um das-Steuerelement aufzurufen. 
2. Eine <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> Komponente, die ein ereignisgesteuerte Modell bietet. 

In beiden Beispielen wird der Hintergrund Thread für eine Sekunde in den Ruhezustand versetzt, um die Arbeit in diesem Thread zu simulieren. 

Sie können diese Beispiele als .NET Framework-Apps über die C# Befehlszeile oder Visual Basic erstellen und ausführen. Weitere Informationen finden Sie unter Erstellen über die [Befehlszeile mit csc. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Erstellen über die Befehlszeile (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

Ab .net Core 3,0 können Sie die Beispiele auch als Windows .net Core-Apps aus einem Ordner erstellen und ausführen, der über einen .net Core-Windows Forms  *\<Ordnername > csproj* -Projektdatei verfügt. 

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Beispiel: Verwenden der Aufruf Methode mit einem Delegaten

Im folgenden Beispiel wird ein Muster zum Sicherstellen von Thread sicheren Aufrufen eines Windows Forms-Steuer Elements veranschaulicht. Er fragt die <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> -Eigenschaft ab, die die Erstellungsthread-ID des Steuer Elements mit der aufrufenden Thread-ID vergleicht. Wenn die Thread-IDs identisch sind, wird das-Steuerelement direkt aufgerufen. Wenn sich die Thread-IDs unterscheiden, ruft <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> Sie die-Methode mit einem Delegaten aus dem Haupt Thread auf, der den eigentlichen Aufruf des Steuer Elements übernimmt.

Ermöglicht das Festlegen der <xref:System.Windows.Forms.TextBox> - <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft des Steuer Elements. `SafeCallDelegate` Die `WriteTextSafe` Methoden Abfragen <xref:System.Windows.Forms.Control.InvokeRequired%2A>. Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A> zurück `true`gibt ,`WriteTextSafe` übergibt das`SafeCallDelegate` an die<xref:System.Windows.Forms.Control.Invoke%2A> -Methode, um den eigentlichen-Befehl an das-Steuerelement zu senden. Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A> zurück `false`gibt ,`WriteTextSafe` legt den<xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> direkt fest. Der `Button1_Click` -Ereignishandler erstellt den neuen Thread und führt `WriteTextSafe` die-Methode aus. 

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Beispiel: Verwenden eines BackgroundWorker-Ereignis Handlers

Eine einfache Möglichkeit zum Implementieren von Multithreading ist die <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> -Komponente, die ein Ereignis gesteuerter Modell verwendet. Der Hintergrund Thread führt das <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> -Ereignis aus, das nicht mit dem Haupt Thread interagiert. Der Haupt Thread führt den <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> - <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> Ereignishandler und den-Ereignishandler aus, der die Steuerelemente des Haupt Threads abrufen kann.

Erstellen Sie zum Ausführen eines Thread sicheren Aufrufes mithilfe <xref:System.ComponentModel.BackgroundWorker>von eine Methode im Hintergrund Thread, um die Arbeit durchzuführen, und binden Sie Sie an das <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignis. Erstellen Sie eine weitere Methode im Haupt Thread, um die Ergebnisse der Hintergrundarbeit zu melden und Sie an das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> - <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignis oder das-Ereignis zu binden. Um den Hintergrund Thread zu starten, <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>wird aufgerufen. 

Das Beispiel verwendet den <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler, um <xref:System.Windows.Forms.TextBox> die- <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft des-Steuer Elements festzulegen. Ein Beispiel für die Verwendung <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> des-Ereignisses <xref:System.ComponentModel.BackgroundWorker>finden Sie unter. 

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.BackgroundWorker>
- [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md)
- [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrund Operation verwendet](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Entwickeln Sie benutzerdefinierte Windows Forms Steuerelemente mit dem .NET Framework](developing-custom-windows-forms-controls.md)

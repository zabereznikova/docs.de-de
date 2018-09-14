---
title: 'Gewusst wie: Downloaden einer Datei im Hintergrund'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
ms.openlocfilehash: 2396516a0e6c9aeb9b2d64a0bf6e3974d64a5cc5
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45519483"
---
# <a name="how-to-download-a-file-in-the-background"></a>Gewusst wie: Downloaden einer Datei im Hintergrund
Das Herunterladen von Dateien ist eine häufige Aufgabe, und es ist oft sinnvoll, diesen potenziell zeitaufwendigen Vorgang in einem separaten Thread auszuführen. Mithilfe der <xref:System.ComponentModel.BackgroundWorker>-Komponente können Sie diese Aufgabe mit nur wenigen Codezeilen ausführen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Verwendung einer <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Laden einer XML-Datei über eine URL veranschaulicht. Klickt der Benutzer die **herunterladen** Schaltfläche der <xref:System.Windows.Forms.Control.Click> -Ereignishandler ruft die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> Methode eine <xref:System.ComponentModel.BackgroundWorker> Komponente, um den Download zu starten. Während des Downloads ist die Schaltfläche deaktiviert, und nach Abschluss des Downloads wird sie wieder aktiviert. Ein <xref:System.Windows.Forms.MessageBox> zeigt den Inhalt der Datei an.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 **Herunterladen der Datei**  
  
 Die Datei wird im Arbeitsthread der <xref:System.ComponentModel.BackgroundWorker>-Komponente heruntergeladen, der den <xref:System.ComponentModel.BackgroundWorker.DoWork>-Ereignishandler ausführt. Dieser Thread startet, wenn vom Code die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>-Methode aufgerufen wird.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 **Warten auf die Beendigung von „BackgroundWorker“**  
  
 Der `downloadButton_Click`-Ereignishandler veranschaulicht, wie auf den Abschluss der asynchronen Aufgabe einer <xref:System.ComponentModel.BackgroundWorker>-Komponente gewartet wird.  
  
 Wenn die Anwendung nur auf Ereignisse reagieren soll und im Hauptthread keine Vorgänge ausgeführt werden sollen, während auf den Abschluss des Hintergrundthreads gewartet wird, können Sie den Handler einfach beenden.  
  
 Wenn Sie im Hauptthread weitere Schritte ausführen möchten, verwenden Sie die <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A>-Eigenschaft, um zu ermitteln, ob der <xref:System.ComponentModel.BackgroundWorker>-Thread noch ausgeführt wird. Im Beispiel wird eine Statusanzeige aktualisiert, während der Download verarbeitet wird. Sie müssen die <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>-Methode aufrufen, damit die Benutzeroberfläche weiterhin auf Aktionen reagiert.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 **Anzeigen des Ergebnisses**  
  
 Die `backgroundWorker1_RunWorkerCompleted`-Methode behandelt das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>-Ereignis und wird aufgerufen, wenn der Hintergrundvorgang abgeschlossen ist. Diese Methode überprüft zuerst die <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>-Eigenschaft. Wenn <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> den Wert `null` aufweist, zeigt die Methode den Inhalt der Datei an. Anschließend wird die Schaltfläche "Herunterladen" wieder aktiviert, die zu Beginn des Downloads deaktiviert wurde, und die Statusanzeige wird zurückgesetzt.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Drawing", "System.Windows.Forms" und "System.XML".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Überprüfen Sie immer die <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>-Eigenschaft im <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>-Ereignishandler, bevor Sie auf die <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType>-Eigenschaft oder auf ein anderes Objekt zugreifen, auf das der <xref:System.ComponentModel.BackgroundWorker.DoWork>-Ereignishandler Einfluss haben kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)

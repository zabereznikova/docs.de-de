---
title: Festlegen des vom ProgressBar-Steuerelement angezeigten Werts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 79ce1e576652d00b323d31dfc6551e168ea0a9a0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743798"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Gewusst wie: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts
> [!IMPORTANT]
> Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Der .NET Framework bietet verschiedene Möglichkeiten, einen bestimmten Wert innerhalb des <xref:System.Windows.Forms.ProgressBar> Steuer Elements anzuzeigen. Welche Methode Sie auswählen, hängt von der Aufgabe oder dem Problem ab, das Sie lösen. In der folgenden Tabelle werden die Ansätze angezeigt, die Sie auswählen können.  
  
|Ansatz|Beschreibung|  
|--------------|-----------------|  
|Legen Sie den Wert des <xref:System.Windows.Forms.ProgressBar> Steuer Elements direkt fest.|Diese Vorgehensweise eignet sich für Aufgaben, bei denen Sie wissen, wie viel von dem Element gemessen werden muss, z. b. das Lesen von Datensätzen aus einer Datenquelle. Wenn Sie den Wert nur einmal oder zweimal festlegen müssen, ist dies eine einfache Möglichkeit. Verwenden Sie abschließend diesen Prozess, wenn Sie den von der Statusanzeige angezeigten Wert verringern müssen.|  
|Vergrößern Sie die <xref:System.Windows.Forms.ProgressBar> Anzeige durch einen Fixed-Wert.|Diese Vorgehensweise ist nützlich, wenn Sie eine einfache Anzahl zwischen dem minimal-und Maximalwert anzeigen, z. b. der verstrichenen Zeit oder der Anzahl der Dateien, die aus einem bekannten Gesamtwert verarbeitet wurden.|  
|Vergrößern Sie die <xref:System.Windows.Forms.ProgressBar> Anzeige durch einen Wert, der variiert.|Diese Vorgehensweise ist hilfreich, wenn Sie den angezeigten Wert in unterschiedlichen Mengen mehrmals ändern müssen. Ein Beispiel wäre die Anzeige der Menge an Festplattenspeicher, die beim Schreiben einer Reihe von Dateien auf den Datenträger verbraucht wird.|  
  
 Die direkteste Möglichkeit zum Festlegen des Werts, der von einer Statusanzeige angezeigt wird, besteht darin, die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft festzulegen. Dies kann entweder zur Entwurfszeit oder zur Laufzeit erfolgen.  
  
### <a name="to-set-the-progressbar-value-directly"></a>So legen Sie den Wert "ProgressBar" direkt fest  
  
1. Legen Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A>-und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte des <xref:System.Windows.Forms.ProgressBar>-Steuer Elements fest.  
  
2. Legen Sie im Code die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft des Steuer Elements auf einen ganzzahligen Wert zwischen den minimalen und maximalen Werten fest, die Sie festgelegt haben.  
  
    > [!NOTE]
    > Wenn Sie die <xref:System.Windows.Forms.ProgressBar.Value%2A>-Eigenschaft außerhalb der Grenzen festlegen, die durch die Eigenschaften <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> festgelegt wurden, löst das Steuerelement eine <xref:System.ArgumentException> Ausnahme aus.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie der <xref:System.Windows.Forms.ProgressBar> Wert direkt festgelegt wird. Der Code liest Datensätze aus einer Datenquelle und aktualisiert die Statusanzeige und die Bezeichnung jedes Mal, wenn ein Datensatz gelesen wird. Für dieses Beispiel ist es erforderlich, dass das Formular über ein <xref:System.Windows.Forms.Label>-Steuerelement, ein <xref:System.Windows.Forms.ProgressBar>-Steuerelement und eine Datentabelle mit einer Zeile namens `CustomerRow` mit `FirstName` und `LastName` Feldern verfügt.  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     Wenn Sie den Fortschritt in einem festgelegten Intervall anzeigen, können Sie den Wert festlegen und dann eine Methode aufzurufen, die den Wert des <xref:System.Windows.Forms.ProgressBar> Steuer Elements um dieses Intervall erhöht. Dies ist nützlich für Timer und andere Szenarien, in denen der Fortschritt nicht als Prozentsatz des ganzen gemessen wird.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>So erhöhen Sie die Statusanzeige durch einen Fixed-Wert  
  
1. Legen Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A>-und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte des <xref:System.Windows.Forms.ProgressBar>-Steuer Elements fest.  
  
2. Legen Sie die <xref:System.Windows.Forms.ProgressBar.Step%2A>-Eigenschaft des Steuer Elements auf eine ganze Zahl fest, die den Betrag angibt, um den angezeigten Wert der Statusanzeige zu erhöhen  
  
3. Wenden Sie die <xref:System.Windows.Forms.ProgressBar.PerformStep%2A>-Methode an, um den Wert zu ändern, der von dem in der <xref:System.Windows.Forms.ProgressBar.Step%2A>-Eigenschaft festgelegten Betrag  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie eine Statusanzeige die Anzahl der Dateien in einem Kopiervorgang beibehalten kann.  
  
     Im folgenden Beispiel werden beim Lesen der einzelnen Dateien in den Arbeitsspeicher die Statusanzeige und die Bezeichnung aktualisiert, um die insgesamt gelesenen Dateien widerzuspiegeln. Dieses Beispiel erfordert, dass das Formular über ein <xref:System.Windows.Forms.Label>-Steuerelement und ein <xref:System.Windows.Forms.ProgressBar>-Steuerelement verfügt.  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     Schließlich können Sie den Wert erhöhen, der von einer Statusanzeige angezeigt wird, sodass jede Erhöhung eine eindeutige Menge ist. Dies ist hilfreich, wenn Sie eine Reihe von eindeutigen Vorgängen nachverfolgen, wie z. b. das Schreiben von Dateien mit unterschiedlichen Größen auf eine Festplatte oder das Messen des Fortschritts als Prozentsatz des ganzen.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>So erhöhen Sie die Statusanzeige durch einen dynamischen Wert  
  
1. Legen Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A>-und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte des <xref:System.Windows.Forms.ProgressBar>-Steuer Elements fest.  
  
2. Ruft die <xref:System.Windows.Forms.ProgressBar.Increment%2A>-Methode auf, um den Wert zu ändern, der von einer angegebenen Ganzzahl angezeigt wird.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie eine Statusanzeige berechnen kann, wie viel Speicherplatz während eines Kopiervorgangs verwendet wurde.  
  
     Im folgenden Beispiel werden beim Schreiben der einzelnen Dateien auf die Festplatte die Statusanzeige und die Bezeichnung aktualisiert, um den verfügbaren Festplatten Speicherplatz widerzuspiegeln. Dieses Beispiel erfordert, dass das Formular über ein <xref:System.Windows.Forms.Label>-Steuerelement und ein <xref:System.Windows.Forms.ProgressBar>-Steuerelement verfügt.  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number   
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number   
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example   
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of   
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_   
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number   
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and   
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number   
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example   
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of   
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [Übersicht über das ProgressBar-Steuerelement](progressbar-control-overview-windows-forms.md)
- [ProgressBar-Steuerelement](progressbar-control-windows-forms.md)

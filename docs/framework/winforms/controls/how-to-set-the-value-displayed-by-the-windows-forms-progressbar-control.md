---
title: Festlegen des von ProgressBar Control angezeigten Werts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: d295079a96ca19a4e4c98e113a3f3051c6403182
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141810"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Gewusst wie: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts
> [!IMPORTANT]
> Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Mit .NET Framework können Sie verschiedene Möglichkeiten zum <xref:System.Windows.Forms.ProgressBar> Anzeigen eines bestimmten Werts innerhalb des Steuerelements bieten. Welchen Ansatz Sie wählen, hängt von der anstehenden Aufgabe oder dem Problem ab, das Sie lösen. Die folgende Tabelle zeigt die Ansätze, die Sie auswählen können.  
  
|Vorgehensweise|Beschreibung|  
|--------------|-----------------|  
|Legen Sie den <xref:System.Windows.Forms.ProgressBar> Wert des Steuerelements direkt fest.|Dieser Ansatz ist nützlich für Aufgaben, bei denen Sie die Summe des gemessenen Elements kennen, z. B. das Lesen von Datensätzen aus einer Datenquelle. Wenn Sie den Wert nur ein- oder zweimal festlegen müssen, ist dies eine einfache Möglichkeit. Verwenden Sie diesen Prozess schließlich, wenn Sie den wert verringern müssen, der im Fortschrittsbalken angezeigt wird.|  
|Erhöhen <xref:System.Windows.Forms.ProgressBar> Sie die Anzeige um einen festen Wert.|Dieser Ansatz ist nützlich, wenn Sie eine einfache Anzahl zwischen dem Minimum und dem Maximum anzeigen, z. B. die verstrichene Zeit oder die Anzahl der Dateien, die aus einer bekannten Summe verarbeitet wurden.|  
|Erhöhen <xref:System.Windows.Forms.ProgressBar> Sie die Anzeige um einen Wert, der variiert.|Dieser Ansatz ist nützlich, wenn Sie den angezeigten Wert mehrmals in verschiedenen Beträgen ändern müssen. Ein Beispiel wäre das Anzeigen des Speicherplatzes, der beim Schreiben einer Reihe von Dateien auf die Festplatte verbraucht wird.|  
  
 Die direkteste Möglichkeit, den von einem Fortschrittsbalken <xref:System.Windows.Forms.ProgressBar.Value%2A> angezeigten Wert festzulegen, besteht darin, die Eigenschaft festzulegen. Dies kann entweder zur Entwurfszeit oder zur Laufzeit erfolgen.  
  
### <a name="to-set-the-progressbar-value-directly"></a>So legen Sie den ProgressBar-Wert direkt fest  
  
1. Legen <xref:System.Windows.Forms.ProgressBar> Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte und Werte des Steuerelements fest.  
  
2. Legen Sie im Code <xref:System.Windows.Forms.ProgressBar.Value%2A> die Eigenschaft des Steuerelements auf einen Ganzzahlwert zwischen den von Ihnen festgelegten minimalen und maximalen Werten fest.  
  
    > [!NOTE]
    > Wenn Sie <xref:System.Windows.Forms.ProgressBar.Value%2A> die Eigenschaft außerhalb der <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> grenzen festlegen, die <xref:System.ArgumentException> durch die und Eigenschaften festgelegt wurden, löst das Steuerelement eine Ausnahme aus.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie der Wert direkt festgelegt wird. <xref:System.Windows.Forms.ProgressBar> Der Code liest Datensätze aus einer Datenquelle und aktualisiert die Statusleiste und Beschriftung jedes Mal, wenn ein Datensatz gelesen wird. In diesem Beispiel muss <xref:System.Windows.Forms.Label> das Formular <xref:System.Windows.Forms.ProgressBar> über ein Steuerelement, ein `CustomerRow` Steuerelement `FirstName` `LastName` und eine Datentabelle mit einer Zeile mit und Feldern verfügen.  
  
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
  
     Wenn Sie den Fortschritt anzeigen, der nach einem festen Intervall verläuft, können <xref:System.Windows.Forms.ProgressBar> Sie den Wert festlegen und dann eine Methode aufrufen, die den Wert des Steuerelements um dieses Intervall erhöht. Dies ist nützlich für Timer und andere Szenarien, in denen Sie den Fortschritt nicht als Prozentsatz des Ganzen messen.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>So erhöhen Sie den Fortschrittsbalken um einen festen Wert  
  
1. Legen <xref:System.Windows.Forms.ProgressBar> Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte und Werte des Steuerelements fest.  
  
2. Legen Sie die <xref:System.Windows.Forms.ProgressBar.Step%2A> Eigenschaft des Steuerelements auf eine ganze Zahl fest, die den Betrag darstellt, um den angezeigten Wert des Fortschrittsbalkens zu erhöhen.  
  
3. Rufen <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> Sie die Methode auf, um den <xref:System.Windows.Forms.ProgressBar.Step%2A> Wert zu ändern, der durch den in der Eigenschaft festgelegten Betrag angezeigt wird.  
  
     Das folgende Codebeispiel veranschaulicht, wie eine Fortschrittsleiste die Anzahl der Dateien in einem Kopiervorgang verwalten kann.  
  
     Im folgenden Beispiel werden die Statusanzeige und die Bezeichnung aktualisiert, wenn jede Datei in den Arbeitsspeicher eingelesen wird, um die gelesenen Gesamtdateien widerzuspiegeln. In diesem Beispiel muss <xref:System.Windows.Forms.Label> das Formular <xref:System.Windows.Forms.ProgressBar> über ein Steuerelement und ein Steuerelement verfügen.  
  
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
  
     Schließlich können Sie den Wert erhöhen, der durch einen Fortschrittsbalken angezeigt wird, sodass jede Erhöhung ein eindeutiger Betrag ist. Dies ist nützlich, wenn Sie eine Reihe von eindeutigen Vorgängen nachverfolgen, z. B. das Schreiben von Dateien unterschiedlicher Größe auf eine Festplatte oder das Messen des Fortschritts als Prozentsatz des Ganzen.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>So erhöhen Sie den Fortschrittsbalken um einen dynamischen Wert  
  
1. Legen <xref:System.Windows.Forms.ProgressBar> Sie die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte und Werte des Steuerelements fest.  
  
2. Rufen <xref:System.Windows.Forms.ProgressBar.Increment%2A> Sie die Methode auf, um den Wert zu ändern, der von einer von Ihnen angegebenen Ganzzahl angezeigt wird.  
  
     Das folgende Codebeispiel veranschaulicht, wie ein Fortschrittsbalken berechnen kann, wie viel Speicherplatz während eines Kopiervorgangs verwendet wurde.  
  
     Im folgenden Beispiel werden die Statusanzeige und die Bezeichnung aktualisiert, um den verfügbaren Festplattenspeicher widerzuspiegeln, wenn jede Datei auf die Festplatte geschrieben wird. In diesem Beispiel muss <xref:System.Windows.Forms.Label> das Formular <xref:System.Windows.Forms.ProgressBar> über ein Steuerelement und ein Steuerelement verfügen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [Übersicht über das ProgressBar-Steuerelement](progressbar-control-overview-windows-forms.md)
- [ProgressBar-Steuerung](progressbar-control-windows-forms.md)

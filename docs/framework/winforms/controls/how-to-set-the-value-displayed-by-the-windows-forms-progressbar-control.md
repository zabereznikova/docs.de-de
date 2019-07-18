---
title: 'Vorgehensweise: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 10e864ccfeb22113e5704a4063f903d7a91fedcd
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591577"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>Vorgehensweise: Festlegen des vom ProgressBar-Steuerelement für Windows Forms angezeigten Werts
> [!IMPORTANT]
>  Obwohl das <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelement das <xref:System.Windows.Forms.ProgressBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ProgressBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 .NET Framework bietet Ihnen mehrere Möglichkeiten zum Anzeigen eines angegebenen Werts innerhalb der <xref:System.Windows.Forms.ProgressBar> Steuerelement. Welchen Ansatz Sie wählen, hängt die aktuelle Aufgabe oder das Problem, das Sie lösen. Die folgende Tabelle zeigt die Ansätze, dass Sie auswählen können.  
  
|Ansatz|Beschreibung|  
|--------------|-----------------|  
|Legen Sie den Wert, der die <xref:System.Windows.Forms.ProgressBar> direkt steuern.|Dieser Ansatz eignet sich für Aufgaben, in denen Sie die Summe des gemessenen Elements, die z. B. beim Lesen von Datensätzen aus einer Datenquelle beteiligt sein wird, wissen. Wenn Sie nur den Wert ein-oder zweimal festlegen müssen, ist dies eine einfache Möglichkeit dafür. Abschließend verwenden Sie diesen Prozess, verringern Sie den Wert, der von der Statusanzeige angezeigt werden sollen.|  
|Erhöhen Sie die <xref:System.Windows.Forms.ProgressBar> anzeigen, indem Sie einen festen Wert.|Dieser Ansatz ist hilfreich, wenn Sie einen einfachen Zähler zwischen der minimalen und maximalen, z. B. die verstrichene Zeit oder die Anzahl der Dateien, die von einer bekannten insgesamt verarbeitet wurden anzeigen.|  
|Erhöhen Sie die <xref:System.Windows.Forms.ProgressBar> anzeigen, indem Sie einen Wert, der davon unterscheidet.|Dieser Ansatz ist nützlich, wenn Sie zum Ändern des angezeigten Werts eine Anzahl von Malen in unterschiedliche Mengen müssen. Ein Beispiel würde zeigen die Menge an Festplattenspeicher, die beim Schreiben einer Reihe von Dateien auf dem Datenträger verarbeitet werden.|  
  
 Die direkteste Möglichkeit zum Festlegen des Werts von einer Statusanzeige angezeigt wird, durch Festlegen der <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft. Dies kann entweder zur Entwurfszeit oder zur Laufzeit erfolgen.  
  
### <a name="to-set-the-progressbar-value-directly"></a>Den Wert "ProgressBar" direkt festgelegt.  
  
1. Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.  
  
2. Legen Sie im Code des Steuerelements <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft, um eine ganze Zahl zwischen der minimalen und maximalen Werte, die Sie eingerichtet haben.  
  
    > [!NOTE]
    >  Setzen Sie die <xref:System.Windows.Forms.ProgressBar.Value%2A> Eigenschaft außerhalb der Grenzen hergestellt, indem die <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Eigenschaften, löst das Steuerelement eine <xref:System.ArgumentException> Ausnahme.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie zum Festlegen der <xref:System.Windows.Forms.ProgressBar> Wert direkt. Der Code liest Datensätze aus einer Datenquelle und aktualisiert die Statusanzeige und eine Bezeichnung, jedes Mal, wenn ein Datensatz gelesen wird. Dieses Beispiel erfordert, dass das Formular enthält ein <xref:System.Windows.Forms.Label> -Steuerelement, ein <xref:System.Windows.Forms.ProgressBar> -Steuerelement, und eine Datentabelle mit einer Zeile `CustomerRow` mit `FirstName` und `LastName` Felder.  
  
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
  
     Wenn Sie Fortschritt, die nach einem festen Intervall fortgesetzt wird anzeigen, können Sie legen Sie den Wert und rufen Sie dann auf eine Methode, die erhöht die <xref:System.Windows.Forms.ProgressBar> Wert des Steuerelements nach diesem Intervall. Dies ist nützlich für Zeitgeber und andere Szenarien, in dem Sie Fortschritt nicht als Prozentsatz des ganzen messen.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>Um die Statusanzeige durch einen festen Wert zu erhöhen.  
  
1. Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.  
  
2. Legen Sie die <xref:System.Windows.Forms.ProgressBar.Step%2A> -Eigenschaft eine ganze Zahl fest, die Menge der Statusanzeige erhöht der angezeigte Wert.  
  
3. Rufen Sie die <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> Methode zum Ändern des Werts angezeigt wird, um den Betrag an, legen Sie in der <xref:System.Windows.Forms.ProgressBar.Step%2A> Eigenschaft.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie eine Statusanzeige Anzahl der Dateien in einem Kopiervorgang verwalten kann.  
  
     Im folgenden Beispiel wie jede Datei in den Arbeitsspeicher zu lesen ist sind die Statusanzeige und eine Bezeichnung entsprechend aktualisiert, dass die gesamte Dateien lesen. Dieses Beispiel erfordert, dass das Formular enthält ein <xref:System.Windows.Forms.Label> Steuerelement und ein <xref:System.Windows.Forms.ProgressBar> Steuerelement.  
  
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
  
     Schließlich können Sie den Wert, der durch eine Statusanzeige angezeigt wird, sodass jede Erhöhung einer eindeutigen Menge ist, erhöhen. Dies ist nützlich, wenn Sie nachverfolgt eine Reihe von eindeutigen Vorgänge, z. B. das Schreiben von Dateien mit verschiedenen Größen auf einer Festplatte oder als Prozentsatz des ganzen messen werden.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>Die Statusanzeige um einen dynamischen Wert zu erhöhen.  
  
1. Legen Sie die <xref:System.Windows.Forms.ProgressBar> des Steuerelements <xref:System.Windows.Forms.ProgressBar.Minimum%2A> und <xref:System.Windows.Forms.ProgressBar.Maximum%2A> Werte.  
  
2. Rufen Sie die <xref:System.Windows.Forms.ProgressBar.Increment%2A> Methode so ändern Sie den Wert, der durch eine ganze Zahl, die Sie angeben, angezeigt.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie eine Statusanzeige berechnen kann wie viel Speicherplatz während eines Kopiervorgangs verwendet wurde.  
  
     Im folgenden Beispiel wenn jede Datei auf die Festplatte geschrieben werden sind die Statusanzeige und eine Bezeichnung entsprechend aktualisiert die Menge an Festplattenspeicher zur Verfügung. Dieses Beispiel erfordert, dass das Formular enthält ein <xref:System.Windows.Forms.Label> Steuerelement und ein <xref:System.Windows.Forms.ProgressBar> Steuerelement.  
  
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
